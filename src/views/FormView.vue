<script setup lang="ts">
import { ref } from 'vue';
import { useRoute, useRouter } from 'vue-router';
import type { RouteLocationNormalizedLoaded, Router } from 'vue-router';

interface State {
	name: string;
	email: string;
}

const route: RouteLocationNormalizedLoaded = useRoute();
const router: Router = useRouter();

const initialState: State = { name: '', email: '' };
const form = ref<State>(initialState);

const handleSubmit = (): void => {
	console.log(form.value);
	router.push({ name: 'confirm', state: { name: form.value.name, email: form.value.email } });
};
</script>

<template>
	<main>
		<h1>Form</h1>
		<form @submit.prevent="handleSubmit">
			<label>
				Name:
				<input type="text" v-model="form.name" />
			</label>
			<br />
			<label>
				Email:
				<input type="email" v-model="form.email" />
			</label>
			<br />
			<button type="submit">確認画面へ</button>
		</form>
	</main>
</template>
