<script setup>
import {useFetch} from './useFetch.js'
import ProductCard from '../ProductCard.vue'
import SkeletonCard from '../SkeletonCard.vue'

const {data: product, error} = useFetch('https://dummyjson.com/products/1')

</script>

<template>
	<div v-if="error">{{ error.message }}</div> 
	<div v-else-if="product">
		<ProductCard :product="product"/>
	</div>
	<div v-else>
		<SkeletonCard/>
	</div>
</template>
