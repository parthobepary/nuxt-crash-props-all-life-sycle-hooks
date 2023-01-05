<script setup>
/* data */
const data = ref(false)
/* compute */
 const massage = computed(()=>{
    return 'I am computed'
 })
 /* method */
 const setClick = () => {
    data.value = !data.value
 }
 const show = () => {
    console.log('this is mounted');
 }
 /* watch */
 watch(data, function(nv,ov){
    console.log(ov);
 })
 /* mounted */
 onMounted(() => {
    show()
 })
 /* beforeMount */
 onBeforeMount(()=>{
    console.log('i am before mount');
 })

</script>
<template>
    <div>
        <h1>All Life cycle</h1>
        <p>Computed: {{ massage }}</p>
        <p>{{ data }}</p>
        <button @click="setClick" class="px-3 py-1 rounded-lg bg-gray-200">click</button>
    </div>
</template>
