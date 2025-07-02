<template>
  <header class="topbar">
    <div class="title-left">TereSol</div>

    <div class="title-center">Learning Management System</div>

    <div class="user-info" @click="toggleMenu">
      Muhammad Daud
      <div v-if="showMenu" class="dropdown">
        <button @click="logout">Logout</button>
      </div>
    </div>
  </header>
</template>

<script setup>
defineOptions({ name: 'AppHeader' })
import { ref } from 'vue'
import { useRouter } from 'vue-router'

const showMenu = ref(false)
const router = useRouter()

function toggleMenu() {
  showMenu.value = !showMenu.value
}

function logout() {
  // Later you'll clear auth state here too
  router.push('/') // Go to login page
  showMenu.value = false
}
</script>

<style scoped>
.topbar {
  background-color: #f7941d;
  color: white;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 24px;
  font-weight: 500;
  position: relative;
}

.title-left {
  font-size: 18px;
  font-weight: bold;
}

.title-center {
  font-size: 20px;
  font-weight: bold;
  text-align: center;
  flex-grow: 1;
}

.user-info {
  position: relative;
  cursor: pointer;
}

.dropdown {
  position: absolute;
  right: 24px;
  top: 60px;
  background-color: white;
  color: black;
  border: 1px solid #ddd;
  border-radius: 4px;
  padding: 8px;
  z-index: 999;
}

.dropdown button {
  background: none;
  border: none;
  padding: 6px 12px;
  cursor: pointer;
  font-weight: 500;
  color: #3b82f6;
}
</style>
