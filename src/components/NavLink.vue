<template>
    <div class="h-full flex items-center justify-center">
    <router-link :to="path"> {{ name }} </router-link>
  </div>
</template>

<script setup>
  const props = defineProps({
    path: { type: String, required: true },
    name: { type: String, required: true }
  });
</script>
