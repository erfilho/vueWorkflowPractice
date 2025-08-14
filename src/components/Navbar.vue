<template>
  <nav class="p-2">
    <div class="rounded-md w-full h-8 bg-red-200 flex flex-row items-center justify-center">
      <h1 class="sm:w-3/4 flex flex-row w-1/2 justify-start text-start px-4 font-semibold"> My project </h1>
      <ul
         class="flex-row items-center justify-end px-4 w-1/2 gap-4"
        :class="menuOpen ? 'flex' : 'hidden'">
        <li v-for="link in links" :key="link.path">
          <router-link :to="link.path" class="hover:underline"> {{ link.name }}</router-link> 
        </li>
      </ul>
      <button class="sm:hidden w-1/2 flex items-end justify-end px-4 cursor-pointer" @click="toggleMenu"> <BxMenu /> </button>
    </div>
  </nav>
</template>

<script setup>
  import { BxMenu } from '@kalimahapps/vue-icons';

  import {ref} from 'vue'

  const menuOpen = ref(false)

  const toggleMenu = () => (menuOpen.value = !menuOpen.value)

  const links = [
    { name: 'Home', path: '/home'},
    { name: 'About', path:'/about'},
  ]
</script>
