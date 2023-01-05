<script setup>
import {fetchData} from "~/composables/fetch";
const tokens = UseToken()
const email = ref('')
const password = ref('')
const url = 'https://reqres.in/api/login'

const login = async () => {
    let user = {
        "email": email.value,
        "password": password.value
    }
    const response = await useFetch(url, {
        method: "post",
        body: user
    })
    /* console.log(response.data._rawValue.token);
    tokens.value = response.data._rawValue.token */
    if (response.data._rawValue.token) {
        tokens.value = true
    }
    clear()
}
const clear = () => {
    email.value = ''
    password.value = ''
}
//use fetch mixin
const contentData = await fetchData('https://jsonplaceholder.typicode.com/users')
const logData = contentData.data._rawValue

</script>
<template>
    <div class="container max-auto text-center">
        <div>
            <h1>This is login page </h1>
                <div class="my-4">
                    <input v-model="email"
                        class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg mr-3"
                        placeholder="email" type="email">
                    <input v-model="password"
                        class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg "
                        placeholder="password" type="password">
                    <div>
                        <button @click="login" class="px-4 mt-3 bg-green-300">submit</button>
                    </div>
                </div>
                <div class="grid grid-cols-4 md:grid-cols-4">
                    <div v-for="data in logData" :key="data">
                    {{data.name}}
                    </div>
                </div>
        </div>
    </div>
</template>