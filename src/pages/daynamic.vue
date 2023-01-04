<script setup>
const message = shallowRef(resolveComponent('about-message'))
let num = ref(0)
let text = ref('click1')
const toggol = () =>{
    num.value++
    if(num.value%2 == 0){
        text.value = "click1"
        message.value = resolveComponent('about-message')
    }
    else{
        text.value = "click2"
        message.value = resolveComponent('welcome')
    }
}
</script>
<template>
    <div class="max-auto container text-center">
        <h1>This is dynamic component</h1>
        <button class="px-4 py-1 bg-blue-200 my-2 rounded-lg" @click="toggol">{{text}}</button>
        <component :is="message"></component>
    </div>
</template>

