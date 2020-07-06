# Sliding Header

Vue.js component representing sliding header (or two different headers) for top navigation bar

![VB-preview](https://altrusl.github.io/vuesence-sliding-header/vsh.gif)

# How to use

This Vue component consists of one <a href="https://github.com/altrusl/vuesence-sliding-header/blob/master/src/components/SlidingHeader.vue" target="_blank">`SlidingHeader.vue`</a> file that can be copy-pasted into your Vue.js project or can be plugged in as an NPM package:

```bash
npm install @vuesence/sliding-header --save
```

Then you can use it in the your Vue code:

```html
<template>
	<div id="app">
		<sliding-header :threshold-hide="200" :threshold-open="400">
			<template v-slot:first-header>
				<p>The first header</p>
			</template>

			<template v-slot:second-header>
				<p>The second header</p>
			</template>
		</sliding-header>
	</div>
</template>

<script>
	import SlidingHeader from "@vuesence/sliding-header";

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
</style>
```

Each `template` contains code for corresponding header / top navigation bar

Two props - `threshold-hide` and `threshold-open` - define vertical scrolling thresholds for hiding the first and opening the second header.

It is possible to use just one header - either the first or the second. Just omit one of the `templates`

`sliding-header` CSS class selector is shared by both headers, `.first-header` and `.second-header` are dedicated.

`.sliding-header.hidden`'s `top` property should be maximum of headers' `height` with "-" sign.

You can play with `height`, `transition`, `opacity` and other CSS properties to adjust the animation to your needs.

## Demo

<a href="https://altrusl.github.io/vuesence-sliding-header/" target="_blank">https://altrusl.github.io/vuesence-sliding-header/</a>

## Playground

Try it on <a href="https://codesandbox.io/s/sliding-header-z3j3t" target="_blank">codesandbox.io</a>

<!-- > ! The version on `codesandbox.io` might be slightly out of date -->

## Troubleshooting

Any bugs, issues, feature and pull requests are welcome

Please use GitHub's issue reporter or send me an <a href="mailto:ruslan.makarov@gmail.com">email</a>

### Check out my other Vue.js components

- <a href="https://github.com/altrusl/vuesence-book" target="_blank">Vuesence book</a> - minimalistic Vue.js based documentation system component
- <a href="https://github.com/altrusl/vuesence-cloud-sync-button" target="_blank">Cloud Sync Button</a> - a button with cloud synchronization animation

## Contribution

Contribution is always welcome and recommended. Here is how:

-   Fork the repository
-   Clone to your machine
-   Make your changes
-   Create a pull request

-------

<img src="https://imgur.com/A92i02A.png" />
You like Vuesence Sliding Header? GitHub star it and <a href="https://twitter.com/vuesence/status/1280083512645881856?s=20">twit it!</a>

-------


## License

**@vuesence/sliding-header** package is freely distributable under the terms of the [MIT license](LICENSE).
