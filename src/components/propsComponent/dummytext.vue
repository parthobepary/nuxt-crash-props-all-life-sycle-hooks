<template>
  <div class="container mx-auto text-center">
    <h1>This is props component</h1>
    <div>
      <p>{{ text }}</p>
      <button @click="sendEmit" class="px-4 py-1 bg-blue-200">send emit</button>
    </div>
  </div>
</template>

<script setup>
const { text } = defineProps(["text"]);
const emit = defineEmits(["sendData", "AgainSend"]);
const sendEmit = () => {
  emit("sendData", "This is emit data");
  emit("AgainSend", "This is second emit data");
};

/* 
const props = defineProps({
  users: {
    type: Array,
    default: [],
  },
});
*/
</script>

<style scoped></style>
