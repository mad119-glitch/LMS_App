<template>
  <div class="auth-page">
    <h2>Login</h2>

    <form @submit.prevent="login">
      <input type="email" v-model="email" placeholder="Email" required />
      <input type="password" v-model="password" placeholder="Password" required />
      <button type="submit">Login</button>
    </form>

    <p>
      Don't have an account?
      <button @click="goToSignup">Sign up</button>
    </p>
  </div>
</template>

<script setup>
defineOptions({ name: 'UserLogin' })
import { ref } from 'vue'
import { useRouter } from 'vue-router'

const email = ref('')
const password = ref('')
const router = useRouter()

function login() {
  alert(`Email: ${email.value}\nPassword: ${password.value}`)
}
function goToSignup() {
  router.push('/signup')
}
</script>

<style scoped>
.auth-page {
  max-width: 300px;
  margin: 50px auto;
  text-align: center;
}
input,
button {
  display: block;
  width: 100%;
  margin: 10px 0;
  padding: 8px;
}
</style>
