<script setup>

import { ref, computed } from 'vue';
import Js from "./pages/js.vue";
import Css from "./pages/css.vue";
import Html from "./pages/html.vue";
import Home from "./pages/home.vue";
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";

const routes = {
	'/': Home,
	'/html': Html,
	'/js': Js,
	'/css': Css
}

const currentPath = ref(window.location.hash)

window.addEventListener('hashchange', () => {
	currentPath.value = window.location.hash
})

const currentView = computed(() => {
	return routes[currentPath.value.slice(1) || '/'] || Home
})

</script>

<template>
	<Header href="[js, html, css]" />
	<main class="main">
		<component :is="currentView" />
	</main>
	<Footer href="[js, html, css]" />
</template>

<style lang="scss">
.main {
	flex-grow: 1;
}

.container {
	max-width: 1440px;
	padding: 0 10px;
	margin: 0 auto;
}
</style>
