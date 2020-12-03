<template>
  <label for="email-address" class="sr-only">Email address</label>
  <input type="text" v-model="username" class="appearance-none rounded-none relative block w-full px-3 py-2 border border-gray-300 placeholder-gray-500 text-gray-900 rounded-md focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 focus:z-10 sm:text-sm mb-2">
  <input type="password" v-model="password" class="appearance-none rounded-none relative block w-full px-3 py-2 border border-gray-300 placeholder-gray-500 text-gray-900 rounded-md focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 focus:z-10 sm:text-sm mb-3">
  <button @click="doLogin" class="btn-login group relative w-full flex justify-center py-2 px-4 border border-transparent text-sm font-medium rounded-md text-white focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500">
    Entrar
  </button>
  <Modal
    v-if="showModal"
    :username="username"
    :password="password"
    @on-close-modal="onCloseModal"
  />
</template>

<script>
import Modal from './Modal'
import { ref } from 'vue'
export default {
  name: 'Login',
  components: {
    Modal
  },
  setup() {
    const username = ref('hola@mundo.cl')
    const password = ref('123456')
    const showModal = ref(false)

    function doLogin() {
      showModal.value = true
    }
    const onCloseModal = () => showModal.value = false
    return { username, password, doLogin, showModal, onCloseModal }
  }
}
</script>