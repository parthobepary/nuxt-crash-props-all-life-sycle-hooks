<template>
  <div>
    <h1>Timer</h1>
    <p class="my-4">{{ time }} seconds</p>
    <button class="bg-blue-300 rounded-md px-4 py-1" @click="startTimer">
      Start
    </button>
    <button class="mx-3 bg-red-300 rounded-md px-4 py-1" @click="stopTimer">
      Stop
    </button>
    <button class="bg-green-300 rounded-md px-4 py-1" @click="resetTimer">
      Reset
    </button>
  </div>
</template>

<script setup>
let timerInterval = null;
const time = ref(100);

const startTimer = () => {
  timerInterval = setInterval(() => {
    if (time.value <= 0) {
      clearInterval(timerInterval);
    } else {
      time.value--;
    }
  }, 1000);
};
const stopTimer = () => {
  clearInterval(timerInterval);
};
const resetTimer = () => {
  time.value = 100;
};
</script>

<style scoped>
/* Add any custom styles for the timer component here */
</style>
