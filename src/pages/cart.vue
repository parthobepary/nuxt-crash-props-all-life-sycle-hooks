<script setup>
definePageMeta({
    layout:'cartlayout',
    middleware:['auth']
})
const cart = useCart()
</script>
<template>
    <div>
        {{cart}}
        <h1>this is cart page</h1>
    </div>
</template>
