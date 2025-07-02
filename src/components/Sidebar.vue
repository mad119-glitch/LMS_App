<!-- Sidebar.vue -->
<template>
  <aside class="sidebar">
    <ul class="nav-links">
      <li>Dashboard</li>
      <li>Course Outline</li>
      <li>Course Plan</li>
      <li>Assignments</li>
      <li>Quizzes</li>
      <li>Miscellaneous</li>
      <li>Papers</li>
      <li>Announcements</li>
      <li>Guidelines</li>
    </ul>
  </aside>
</template>

<script setup>
defineOptions({ name: 'AppSidebar' })
</script>

<style scoped>
.sidebar {
  width: 220px;
  background-color: white;
  padding-top: 30px;
  min-height: calc(100vh - 60px);
}

.nav-links {
  list-style: none;
  padding: 0;
  margin: 0;
}

.nav-links li {
  padding: 15px 20px;
  color: #333;
  font-weight: 500;
  cursor: pointer;
}

.nav-links li:hover {
  background-color: #f9a53b;
}
</style>
