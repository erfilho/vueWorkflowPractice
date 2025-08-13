<template>
  <button
    @click="response"
    class="rounded-md 0 flex flex-col items-center p-1 text-white font-semibold cursor-pointer"
    :class="color"
  >
    {{ title }}
  </button>
</template>

<script setup>
import { ref } from "vue";

const count = ref(0);

const props = defineProps({
  title: {
    type: String,
    required: true,
  },
  type: {
    type: String,
    default: "Primary",
  },
  color: {
    type: String,
    default: "bg-blue-400",
  },
});

const increment = () => {
  count.value++;
};

function response() {
  increment();
  alert(`The ${props.type} button have ${count.value} clicks`);
}
</script>
