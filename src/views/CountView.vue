<script setup lang="ts">
import { ref } from 'vue';
import CountMessage from '../components/CountMessage.vue';

const count = ref<number>(0);

// カウントアップ
const increment = (): void => {
	count.value++;
};

// カウントダウン
const decrement = (): void => {
	count.value--;
};
</script>

<template>
	<main>
		<h1>カウントテスト</h1>
		<div>
			<p>現在のカウント: {{ count }}</p>
			<button @click="increment">カウントアップ</button>
			<button @click="decrement">カウントダウン</button>
			<CountMessage v-if="count >= 10" :count="count" />
		</div>
	</main>
</template>
