<template>
	<div id="app">
		<SlidingHeader
			treshold-hide="100"
			treshold-open="500"
			two-headers="false"
		>
			<p>Initial header</p>

			<template v-slot:scrolledHeader>
				<p>Scrolled header</p>
			</template>
		</SlidingHeader>
		<DummyContent />
	</div>
</template>

<script>
import DummyContent from "./components/DummyContent.vue";
import SlidingHeader from "./components/SlidingHeader.vue";

export default {
	name: "App",
	components: {
		DummyContent,
		SlidingHeader
	}
};
</script>

<style>
.sliding-header {
	display: flex;
	justify-content: center;
	align-items: center;
	background-color: rgb(135, 241, 188);
	transition: 0.3s;
	height: 70px;
}
.sliding-header.scrolled {
	background-color: rgb(250, 181, 181);
	height: 100px;
}
.sliding-header.hidden {
	top: -80px;
}

#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
}
</style>
