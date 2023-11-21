<script setup>
import FakeContent from './components/FakeContent.vue'
import FetchProduct from './components/lv-1/FetchProduct.vue'
import AdvanceFetchProduct from './components/lv-2/AdvanceFetchProduct.vue'
import ComposibleFetchProduct from './components/lv-3-1/ComposibleFetchProduct.vue';
import BeautifyAdvanceFetchProduct from './components/lv-3/BeautifyAdvanceFetchProduct.vue';
import SuspenseFetchProduct from './components/lv-4/SuspenseFetchProduct.vue';

</script>

<template>
  <div class="min-h-screen w-full flex flex-wrap gap-8  p-8">
    <!-- Lv-1 -->
    <div class="flex flex-col gap-4" style="width: 600px">
      <div class="mb-8 text-center">
        <h2 class="font-bold text-4xl mb-2 whitespace-nowrap">Lv.1: FetchProduct.vue</h2>
        <p class="text-2xl text-center text-gray-700">索取資料並更新狀態，狀態更新時反映在畫面上</p>
      </div>
      <FakeContent/>
      <FetchProduct/>
      <FakeContent/>
    </div>

    <!-- Lv-2 -->
    <div class="flex flex-col gap-4" style="width: 600px">
      <div class="mb-8 text-center">
        <h2 class="font-bold text-4xl mb-2 whitespace-nowrap">Lv.2: AdvanceFetchProduct.vue</h2>
        <p class="text-2xl text-center text-gray-700">添加加載與錯誤狀態以便應對非同步遭遇的各種狀態</p>
      </div>
      <FakeContent/>
      <AdvanceFetchProduct/>
      <FakeContent/>
      <AdvanceFetchProduct productUrl="https://dummyjson.com/products/brokenLink"/>
      <FakeContent/>
    </div>

    <!-- Lv-3 -->
    <div class="flex flex-col gap-4" style="width: 600px">
      <div class="mb-8 text-center">
        <h2 class="font-bold text-4xl mb-2 whitespace-nowrap">Lv.3: AdvanceFetchProduct.vue</h2>
        <p class="text-2xl text-center text-gray-700">設計 UI 並且添加加載骨架提升用戶體驗</p>
      </div>
      <FakeContent/>
      <BeautifyAdvanceFetchProduct/>
      <FakeContent/>
    </div>

    <!-- Lv-3-1 -->
    <div class="flex flex-col gap-4" style="width: 600px">
      <div class="mb-8 text-center">
        <h2 class="font-bold text-4xl mb-2 whitespace-nowrap">Lv.3-1: ComposibleFetchProduct.vue</h2>
        <p class="text-2xl text-center text-gray-700">包裝 Fetch 並且將狀態解構出來使用</p>
      </div>
      <FakeContent/>
      <ComposibleFetchProduct/>
      <FakeContent/>
    </div>

    <!-- Lv-4 -->
    <div class="flex flex-col gap-4" style="width: 600px">
      <div class="mb-8 text-center">
        <h2 class="font-bold text-4xl mb-2">Lv.4: SuspenseFetchProduct.vue</h2>
        <p class="text-2xl text-center text-gray-700">使用 Vue 的實驗性 Suspense 功能獲得更好的開發體驗。</p>
      </div>
      <FakeContent/>
      <SuspenseFetchProduct/>
      <FakeContent/>
    </div>

  </div>
</template>

