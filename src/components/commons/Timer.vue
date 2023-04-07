<template>
  <div>
    <h1>Countdown Timer</h1>
    <p>{{ formattedTime }}</p>
    <button @click="startCountdown">Start</button>
    <button @click="stopCountdown">Stop</button>
    <button @click="resetCountdown">Reset</button>
  </div>
</template>

<script setup>
const props = defineProps({
    time:{
        type: Number,
        default: null
    }
});
const emit = defineEmits(["timeover"])

let countdownInterval = null;
const timeRemaining = ref(props.time);

// set hh:mm:ss
const formattedTime = computed(() => {
  const hours = Math.floor(timeRemaining.value / 3600);
  const minutes = Math.floor((timeRemaining.value % 3600) / 60);
  const seconds = timeRemaining.value % 60;
  return `${padNumber(hours)}:${padNumber(minutes)}:${padNumber(
    seconds
  )}`;
});
/* method */
// start time
const startCountdown = () => {
  countdownInterval = setInterval(() => {
    if (timeRemaining.value > 0) {
      timeRemaining.value--;
    } else {
        emit('timeover', true);
      stopCountdown();
    }
  }, 1000);
};
// stop timer
const stopCountdown = () => {
  clearInterval(countdownInterval);
  emit('timeover', true)
};
// restart
const resetCountdown = () => {
  timeRemaining.value = 4200;
  stopCountdown();
};
const padNumber = (number) => {
    // helper time zone
  return String(number).padStart(2, "0");
};
</script>

<style scoped>
/* style here */
</style>
