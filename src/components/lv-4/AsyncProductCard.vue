<script setup>
import ProductCard from "../ProductCard.vue";
import { ref } from "vue";

const product = ref({});

async function getProduct() {
		const productResponse = await fetch("https://dummyjson.com/products/1x");
		if (!productResponse.ok) {
			console.error(productResponse);
			throw Error('索取產品失敗')
		}
		const productJSON = await productResponse.json();
		product.value = productJSON;
}
await	getProduct();
</script>

<template>
  <ProductCard :product="product" />
</template>