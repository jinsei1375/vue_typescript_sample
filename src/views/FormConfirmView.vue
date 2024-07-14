<script setup lang="ts">
import { ref, onMounted } from 'vue';
import { useRoute, useRouter } from 'vue-router';
const route = useRoute();
const router = useRouter();
// const state = route.params.state;
const state = ref({ name: '', email: '' });
console.log(route.params.state);
console.log(route.params);

onMounted(() => {
	console.log(history.state);
	const currentState = history.state; // 直接history.stateを参照
	console.log(currentState);
	if (currentState) {
		state.value = currentState;
	}
});

const handleSubmit = () => {
	router.push('/completed');
};

const handleBack = () => {
	router.push({ name: 'form', state: { name: state.value.name, email: state.value.email } });
};
</script>

<template>
	<main>
		<h1>確認ページ</h1>
		<p>Name: {{ state.name }}</p>
		<p>Email: {{ state.email }}</p>
		<button type="button" @click="handleBack">戻る</button>
		<button type="button" @click="handleSubmit">送信</button>
	</main>
</template>
