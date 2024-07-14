<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router';
// import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
	<header>
		<nav>
			<RouterLink to="/">Home</RouterLink>
			<RouterLink to="/form">Form</RouterLink>
			<RouterLink to="/count">Count</RouterLink>
		</nav>
	</header>

	<RouterView />
</template>
