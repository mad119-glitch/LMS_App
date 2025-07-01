<template>
  <div class="auth-page">
    <h2>Sign Up</h2>

    <form @submit.prevent="signup">
      <input type="text" v-model="name" placeholder="Name" required />
      <input type="email" v-model="email" placeholder="Email" required />
      <input type="password" v-model="password" placeholder="Password" required />
      <button type="submit">Create Account</button>
    </form>

    <p>
      Already have an account?
      <button @click="goToLogin">Login</button>
    </p>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { useRouter } from 'vue-router'

const name = ref('')
const email = ref('')
const password = ref('')
const router = useRouter()

function signup() {
  alert(`Name: ${name.value}\nEmail: ${email.value}\nPassword: ${password.value}`)
}
function goToLogin() {
  router.push('/')
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
