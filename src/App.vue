<script setup>
	import HeaderBetween from "./components/headers/HeaderBetween.vue"
</script>

<template>
	<div>
		<HeaderBetween />
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

