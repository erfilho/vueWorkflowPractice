<template>
  <div
    class="h-24 w-80 flex flex-col items-start justify-around bg-gray-400 rounded-sm p-2"
  >
    <p class="font-semibold">{{ title }}</p>
    <p class="font-medium text-sm">{{ description }}</p>
    <div>
      <Buttons
        title="Remove"
        color="bg-red-400 text-white"
        @click="removeItem"
      />
    </div>
  </div>
</template>

<script setup>
import Buttons from "./Buttons.vue";

function removeItem() {
  alert("Removed item from cart");
}

const props = defineProps({
  title: {
    type: String,
    required: true,
  },
  description: {
    type: String,
    default: "",
  },
});
</script>
