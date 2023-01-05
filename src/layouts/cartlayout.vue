<template>
    <div class="container mx-auto text-center">
        <commons-navbar />
        <div>
            <NuxtPage />
        </div>
        <PropsComponentDummytext @AgainSend="AgainSend($event)" @sendData="sendData($event)" text="hello props"/>
    </div>
</template>

<script setup>
const sendData = (evn) => {
    console.log(evn);
}
const AgainSend = (evn) => {
    console.log(evn);
}
</script>