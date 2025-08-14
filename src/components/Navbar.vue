<template>
  <nav>
   <h1> Meu projeto </h1>
   <button class="sm:hidden" @click="toggleMenu"> = </button>
   <ul
       class="sm:flex gap-4"
     :class="menuOpen ? 'block' : 'hidden'">
     <li v-for="link in links" :key="link.path">
      <router-link :to="link.path" class="hover:underline"> {{ link.name }}</router-link> 
     </li>
    </ul>
  </nav>
</template>

<script setup>
  import {ref} from 'vue'

  const menuOpen = ref(false)

  const toggleMenu = () => (menuOpen.value = !menuOpen.value)

  const links = [
    { name: 'Home', path: '/home'},
    { name: 'About', path:'/about'},
  ]
</script>
