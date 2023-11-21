<script setup>
import { onErrorCaptured, ref } from "vue";
import AsyncProductCard from "./AsyncProductCard.vue";
import SkeletonCard from "../SkeletonCard.vue";

const error = ref(null)

onErrorCaptured((err)=> {
	error.value = err.message
})
</script>

<template>

<div v-if="error" class="bg-red-300">
	Err: {{ error }}
</div>

<Suspense>
	<template #default>
		<AsyncProductCard />
	</template>
	<template #fallback>
		<SkeletonCard />
	</template>
</Suspense>
</template>
