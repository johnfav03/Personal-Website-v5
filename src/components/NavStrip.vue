<script setup>
import PolyBg from './PolyBg.vue'

defineProps(['title', 'color'])
</script>

<template>
	<span>
		<PolyBg class="hover-overlay" />
		<div class="bar" :style="{ backgroundColor: `var(${color})` }">
			<h1>{{ title }}</h1>
		</div>
	</span>
</template>

<style scoped>
span {
	display: block;
	width: 40px;
	height: 100%;
	position: relative;
}

.hover-overlay {
	opacity: 0;
	position: absolute;
	top: 0;
	left: 0;
	transition: opacity 0.2s;
}

.hover-overlay:hover {
	opacity: 0.25;
}

.bar {
	color: var(--tx-dark);
	width: 40px;
	height: 100%;
	padding-top: 25px;
}

h1 {
	font-size: 25px;
	height: 40px;
	line-height: 40px;
	transform: rotate(90deg) translateY(-100%);
	transform-origin: top left;
	white-space: nowrap;
	color: inherit;
	pointer-events: none;
}
</style>