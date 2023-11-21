<script setup>
import { ref } from "vue";
import SkeletonCard from "../SkeletonCard.vue";
import ProductCard from '../ProductCard.vue'

const product = ref({});
const isLoading = ref(true);
const errorMessage = ref('')

getProduct();

async function getProduct() {
	isLoading.value = true;
	const productResponse = await fetch("https://dummyjson.com/products/1");
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
	<div v-if="errorMessage">{{ errorMessage }}</div> 
	<div v-else-if="!isLoading">
		<ProductCard :product="product"/>
	</div>
	<div v-else>
		<SkeletonCard/>
	</div>
</template>
