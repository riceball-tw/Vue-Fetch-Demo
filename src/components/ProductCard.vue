<script setup>
defineProps(['product'])

		
</script>
<template>
    <div role="status" class="max-w-sm p-4 border border-gray-200 rounded shadow md:p-6 dark:border-gray-700">
        <img class="object-fit aspect-video flex items-center justify-center h-48 mb-4 bg-gray-300 rounded dark:bg-gray-700" :src="product.thumbnail" alt="fake alt">
        <div style="height: 80px;">
          <h2 class="text-xl font-bold">{{ product.title }}</h2>
          <p>{{ product.description }}</p>
        </div>
    </div>
</template>