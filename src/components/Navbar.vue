<template>
  <nav class="p-2">
    <div class="rounded-md w-full bg-red-200 flex md:flex-row items-center justify-center px-2"
        :class="menuOpen? 'flex-col': 'h-8'">
      <div class="flex flex-row w-full h-8 justify-center md:justify-start items-center">
        <h1 class="w-3/4 flex flex-row h-8 justify-start text-start px-4 items-center font-semibold "> My project </h1>
        <button class="sm:hidden w-1/4 h-8 flex items-center justify-end cursor-pointer" @click="toggleMenu"> <BxMenu /> </button>
      </div>
      <transition name="fade">
        <div
          class="md:flex md:flex-row items-center md:justify-end px-4 w-1/2 md:h-8 md:gap-4"
          :class="menuOpen ? 'flex flex-col h-16 w-full justify-between' : 'hidden'">
          <NavLink v-for="link in links" :key="link.path" :path="link.path" :name="link.name"/>
        </div>
      </transition>
    </div>
  </nav>
</template>

<script setup>
  import { BxMenu } from '@kalimahapps/vue-icons';
  import NavLink from "../components/NavLink.vue";

  import {ref} from 'vue'

  const menuOpen = ref(false)

  const toggleMenu = () => (menuOpen.value = !menuOpen.value)

  const links = [
    { name: 'Home', path: '/home'},
    { name: 'About', path:'/about'},
  ]
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
