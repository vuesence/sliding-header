<template>
	<header class="sliding-header">
		<slot v-if="defaultSlot"></slot>
		<slot name="scrolledHeader" v-else></slot>
	</header>
</template>

<script>
export default {
	name: "SlidingHeader",
	data() {
		return {
			defaultSlot: true
		};
	},
	props: {
		msg: String,
		tresholdHide: Number,
		tresholdOpen: Number,
		twoHeaders: Boolean
	},
	mounted() {
		window.addEventListener("scroll", () => {
			let y = window.scrollY;
			console.log(y);

			if (y > this.tresholdHide && y < this.tresholdOpen) {
				// hidden
				if (this.twoHeaders && !this.defaultSlot) {
					setTimeout(() => {
						this.defaultSlot = true;
					}, 400);
				}
				this.$el.classList.add("hidden");
				this.$el.classList.remove("scrolled");
			} else if (y > this.tresholdOpen) {
				if (this.twoHeaders) {
					this.defaultSlot = false;
				}
				this.$el.classList.add("scrolled");
				this.$el.classList.remove("hidden");
			} else {
				this.defaultSlot = true;
				this.$el.classList.remove("hidden");
				this.$el.classList.remove("scrolled");
			}
		});
	}
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.sliding-header {
	display: flex;
	width: 100%;
	position: fixed;
	z-index: 1;
	top: 0;
	left: 0;
	transition: 0.3s;
}
/* .sliding-header.scrolled {
} */
.sliding-header.hidden {
	top: -80px;
}
</style>
