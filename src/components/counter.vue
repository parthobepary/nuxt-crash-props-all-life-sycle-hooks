<script setup>
let num = ref(0)
const clickEvent = (st) => {
    if(st == 'add'){
        num.value++
    }
    else{
        if(num.value>0){
            num.value--
        }else{
            return
        }
    }
}
</script>

<template>
    <div class="container mx-auto">
        <div class="text-center">
            <div class="flex justify-center item-center mt-2">
                <button @click="clickEvent('add')" class="p-2 bg-green-400 rounded-md">+</button>
                <h1 class="mx-3">{{num}}</h1>
                <button @click="clickEvent('sub')" class="p-2 bg-red-400 rounded-md">-</button>
            </div>
        </div>
    </div>
</template>
