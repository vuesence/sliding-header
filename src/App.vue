<template>
	<div id="app">
		<sliding-header :treshold-hide="200" :treshold-open="400">
			<template v-slot:first-header>
				<p>The first header</p>
			</template>

			<template v-slot:second-header>
				<p>The second header</p>
			</template>
		</sliding-header>

		<p v-for="n in 25" v-bind:key="n">
			{{ n }}. Lorem ipsum dolor sit amet, consectetur adipiscing elit,
			sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
			Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris
			nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in
			reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
			pariatur. Excepteur sint occaecat cupidatat non proident, sunt in
			culpa qui officia deserunt mollit anim id est laborum.
		</p>
	</div>
</template>

<script>
import SlidingHeader from "./components/SlidingHeader.vue";

export default {
	name: "App",
	components: {
		SlidingHeader
	}
};
</script>

<style>
.sliding-header {
	display: flex;
	justify-content: center;
	align-items: center;
	transition: 0.3s;
}
.sliding-header.first-header {
	background-color: lightgreen;
	height: 60px;
}
.sliding-header.second-header {
	background-color: lightblue;
	height: 100px;
}
.sliding-header.hidden {
	top: -100px;
}

#app {
	font-family: Helvetica, Arial, sans-serif;
	color: #2c3e50;
	margin-top: 100px;
}
</style>
