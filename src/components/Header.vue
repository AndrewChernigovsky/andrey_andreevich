<script setup>
defineProps({
	href: String,
});
</script>

<template>
	<header class="header">
		<div class="container">
			<nav class="nav">
				<ul class="nav__list">
					<li><a href="#/html">HTML</a></li>
					<li><a href="#/css">CSS</a></li>
					<li><a href="#/js">JS</a></li>
				</ul>
			</nav>
		</div>
	</header>
</template>

<style lang="scss" scoped>
.header {
	min-height: 100px;
	border: 1px solid black;

	.container {
		display: flex;
		justify-content: center;
		flex-wrap: wrap;
	}
}

.nav {
	&__list {
		list-style-type: none;
		display: flex;
		padding: 0;

		li:not(:first-child) {
			margin-left: 20px;
		}
	}
}
</style>
