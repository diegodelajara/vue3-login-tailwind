<template>
  <label for="email-address" class="sr-only">Email address</label>
  <input type="text" v-model="username" class="appearance-none rounded-none relative block w-full px-3 py-2 border border-gray-300 placeholder-gray-500 text-gray-900 rounded-md focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 focus:z-10 sm:text-sm mb-2">
  <input type="password" v-model="password" class="appearance-none rounded-none relative block w-full px-3 py-2 border border-gray-300 placeholder-gray-500 text-gray-900 rounded-md focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 focus:z-10 sm:text-sm mb-3">
  <button @click="doLogin" class="btn-login group relative w-full flex justify-center py-2 px-4 border border-transparent text-sm font-medium rounded-md text-white focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500">
    Entrar
  </button>
</template>

<script>
import { ref } from 'vue'
export default {
  name: 'Login',
  setup() {
    const username = ref('hola')
    const password = ref('mundo')
    function doLogin() {
      console.log('%c username', 'color:cyan', username.value)
      console.log('%c password', 'color:tomato', password.value)
    }
    return { username, password, doLogin }
  }
}
</script>