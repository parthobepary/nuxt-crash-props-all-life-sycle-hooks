<script setup>
const cart = useCart()
console.log(cart.value.length);
</script>
<template>
    <div class="text-center mb-3 bg-green-200 py-3">
        <nuxt-link class="underline" to="/">Home</nuxt-link>
        <nuxt-link class="mx-5 underline"  to="/daynamic">Dynamic</nuxt-link>
        <nuxt-link class="underline" to="/phones/">Phones</nuxt-link>
        <nuxt-link class="mx-5 underline" to="/cart/">Cart{{cart.length}}</nuxt-link>
    </div>
</template>