<template>
  <div>
    <div class="flex justify-center">
        <div v-if="isTimeOver"><p>Time is over</p></div>
      <div v-else>
        <CommonsTimer @timeover="timeover($event)" time="10"/>
      </div>
    </div>
  </div>
</template>

<script setup>
    let isTimeOver = ref(false);

    // method

    const timeover = (evn) => {
        isTimeOver.value =  evn;
    }
</script>

<style lang="scss" scoped></style>
