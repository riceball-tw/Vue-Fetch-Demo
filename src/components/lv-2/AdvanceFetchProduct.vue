<script setup>
import { ref } from "vue";

const {productUrl} = defineProps({
	productUrl: {
		type: String,
		default: "https://dummyjson.com/products/1"
	}
})

const product = ref({});
const isLoading = ref(true);
const errorMessage = ref('')

getProduct(productUrl);

async function getProduct(productUrl) {
	isLoading.value = true;
	const productResponse = await fetch(productUrl);
	if (!productResponse.ok) {
		console.error(productResponse);
		errorMessage.value = (await productResponse.json()).message
		return;
	}
	const productJSON = await productResponse.json();
	product.value = productJSON;
	isLoading.value = false;
}
</script>

<template>
	<div id="app">
		<div class="bg-white text-black p-4 max-w-fit mx-auto">
			<div class="bg-red-300 p-4" v-if="errorMessage">{{ errorMessage }}</div> 
			<div v-else-if="!isLoading">
				<img :src="product.thumbnail" />
				<h2>{{ product.title }}</h2>
				<p>{{ product.description }}</p>
			</div>
			<div v-else>Loading...</div>
		</div>
	</div>
</template>
