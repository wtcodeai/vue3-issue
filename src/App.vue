<template>
  <div>
    <header class="bg-white shadow" v-if="$route.meta.title">
      <div class="max-w-7xl mx-auto py-6 px-4 sm:px-6 lg:px-8">
        <h1 class="text-3xl font-bold leading-tight text-gray-900">{{ $route.meta.title }}</h1>
      </div>
    </header>
    <main>
      <router-view v-slot="{ Component }" :key="route.path">
        <Suspense>
          <div style="height: 100%">
            <component :is="Component" /> 
          </div>
        </Suspense>
      </router-view>
    </main>
  </div>
</template>

<script setup>
  import { computed, watch, onMounted, ref } from 'vue'
  import { useRoute } from 'vue-router'
  const route = useRoute()


</script>
