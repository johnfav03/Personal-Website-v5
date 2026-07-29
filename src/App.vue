<script setup>
import { ref, onMounted } from 'vue'
import Frame from './components/Frame.vue'
import Home from './pages/Home.vue'
import Projects from './pages/Projects.vue'
import About from './pages/About.vue'

const stage = ref(0)

const pages = [
	{ id: 0, title: "HOME", color: "--acc-one", component: Home },
	{ id: 1, title: "PROJECTS", color: "--acc-two", component: Projects },
	{ id: 2, title: "ABOUT", color: "--acc-thr", component: About }
]

function getOffset(id) {
	if (stage.value === 0) {
		return ["0px", "45px", "90px"][id]
	}
	if (stage.value === 1) {
		return ["calc(130px - 100vw)", "45px", "90px"][id]
	}
	if (stage.value === 2) {
		return ["calc(130px - 100vw)", "calc(175px - 100vw)", "90px"][id]
	}
}

function toggle(id) {
	if (id === stage.value) {
		stage.value = stage.value < 2 ? stage.value + 1 : 0
	} else {
		stage.value = id
	}
	window.history.pushState({}, '', `/${pages[stage.value].title.toLowerCase()}`)
}

onMounted(() => {
	const path = window.location.pathname
	if (path.includes("projects")) {
		stage.value = 1
	}
	if (path.includes("about")) {
		stage.value = 2
	}
})
</script>

<template>
	<Frame
		v-for="page in pages"
		:key="page.id"
		:pos="page.id"
		:off="getOffset(page.id)"
		:title="page.title"
		:color="page.color"
		@toggle="toggle"
	>
		<component :is="page.component" />
	</Frame>
</template>