<script setup>
import { ref } from "vue";

const product = ref({});

async function getProduct() {
	const productResponse = await fetch("https://dummyjson.com/products/1");
	if (!productResponse.ok) {
		console.error(productResponse);
		return;
	}
	const productJSON = await productResponse.json();
	product.value = productJSON;
}

	getProduct();
</script>

<template>
	<div>
		<img :src="product.thumbnail" />
		<h2>{{ product.title }}</h2>
		<p>{{ product.description }}</p>
	</div>
</template>
