<script setup>

const route = useRoute()
const cart = useCart()
let isAvailable = ref(false)

const id = computed(() => {
    return route.params.id
    //remove -(hipan)
    // return route.params.id.replaceAll('-', " ")
})
const addToCart = (id) => {
    cart.value.push(id)
    isAvailable.value = !isAvailable.value
}
const removeFromCart = (id) => {
    cart.value.shift()
    isAvailable.value = !isAvailable.value
}
</script>
<template>
    <div class="max-auto container text-center">
        <p>This is phone details page of {{id}}</p>
        <button @click="!isAvailable? addToCart(id): removeFromCart(id)" :class="isAvailable? 'my-4 px-10 py-2 bg-red-400':'my-4 px-10 py-2 bg-yellow-400'">{{isAvailable? 'Remove from cart':'Add to cart'}}</button>
    </div>
</template>