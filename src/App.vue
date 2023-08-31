<script setup>
	import HeaderBetween from "./components/headers/HeaderBetween.vue"
	import HeaderBetweenLogoLeft from "./components/headers/HeaderBetweenLogoLeft.vue"
	import HeaderManu from "./components/headers/HeaderManu.vue"
	import MagaManuSideBarLeft from "./components/headers/MagaManuSideBarLeft.vue"
	import MagaMnauSideBarRigh from "./components/headers/MagaManuSideBarLeft.vue"
</script>

<template>
	<div>
		<!-- <HeaderBetween /> -->
		<HeaderBetweenLogoLeft />
		<!-- <HeaderManu /> -->
		<!-- <MagaManuSideBarLeft /> -->
		<MagaMnauSideBarRigh />
	</div>
</template>

<style>
	body {
		margin: 0;

		width: 100%;
		max-width: 1980px;
		min-height: 100%;
		display: flex;
		justify-content: stretch;
		align-items: stretch;
	}
	#app {
		text-align: left;
		height: inherit;
		width: inherit;
	}
</style>

