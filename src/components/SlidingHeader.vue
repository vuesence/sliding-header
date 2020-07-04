<template>
	<header
		class="sliding-header"
		:class="{
			'first-header': scrollY < median,
			'second-header': scrollY >= median,
			'hidden': scrollY > tresholdHide && scrollY < tresholdOpen
		}"
	>
		<slot name="first-header" v-if="scrollY < median"></slot>
		<slot name="second-header" v-else></slot>
	</header>
</template>

<script>
export default {
	name: "SlidingHeader",
	data() {
		return {
			scrollY: 0
		};
	},
	props: {
		tresholdHide: Number,
		tresholdOpen: Number
	},
	computed: {
		median() {
			return (this.tresholdHide + this.tresholdOpen) / 2;
		}
	},
	created() {
		window.addEventListener("scroll", () => {
			this.scrollY = window.scrollY;
		});
	}
};
</script>

<style>
.sliding-header {
	position: fixed;
	z-index: 1;
	top: 0;
	left: 0;
	width: 100%;
	transition: 0.3s;
}
</style>
