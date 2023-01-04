<script setup>
const name = 'dummy data'
useHead({
    title: `partho - ${name}`
})
</script>
<template>
    <div class="max-auto container text-center">
        <p>This is all phone page</p>
        <div class="flex justify-center mt-12">
            <div v-for="i in 10" :key="i">
                <nuxt-link class="px-4 py-2 bg-blue-200 rounded-md mr-3" :to="`/phones/${i}`">{{ i }}</nuxt-link>
            </div>
        </div>
    </div>
</template>
