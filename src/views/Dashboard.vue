<template>
  <div class="dashboard-page">
    <AppHeader />

    <div class="main-wrapper">
      <Sidebar />

      <main class="dashboard-content">
        <h2 class="page-title">DASHBOARD</h2>
        <CourseFilter />

        <div class="table-container">
          <table>
            <thead>
              <tr>
                <th>Sr.No.</th>
                <th>Course Title</th>
                <th>Class</th>
                <th>Semester</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(course, index) in courses" :key="index">
                <td>{{ index + 1 }}</td>
                <td>{{ course.title }}</td>
                <td>{{ course.class }}</td>
                <td>{{ course.semester }}</td>
              </tr>
            </tbody>
          </table>
        </div>
      </main>
    </div>
  </div>
</template>

<script setup>
defineOptions({ name: 'DashboardView' })
import AppHeader from '@/components/AppHeader.vue'
import Sidebar from '@/components/Sidebar.vue'
import CourseFilter from '@/components/CourseFilter.vue'

const courses = [
  { title: 'Cyber Security', class: 'BS (IT)-7 (B) Morning', semester: 'Spring-2025' },
  { title: 'Pakistan Studies', class: 'BS (IT)-7 (B) Morning', semester: 'Spring-2025' },
  {
    title: 'Database Administration and Management',
    class: 'BS (IT)-7 (B) Morning',
    semester: 'Spring-2025',
  },
  {
    title: 'Database Administration and Management Lab',
    class: 'BS (IT)-7 (B) Morning',
    semester: 'Spring-2025',
  },
  { title: 'Project – I', class: 'BS (IT)-7 (B) Morning', semester: 'Spring-2025' },
  { title: 'Software Quality Assurance', class: 'BS (IT)-7 (B) Morning', semester: 'Spring-2025' },
  {
    title: 'Introduction to Data Science',
    class: 'BS (IT)-7 (B) Morning',
    semester: 'Spring-2025',
  },
  {
    title: 'Introduction to Data Science Lab',
    class: 'BS (IT)-7 (B) Morning',
    semester: 'Spring-2025',
  },
]
</script>

<style scoped>
.dashboard-page {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  width: 100vw;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background-color: #f5f6fa;
}

.main-wrapper {
  display: flex;
  flex: 1;
}

.dashboard-content {
  flex: 1;
  padding: 30px;
}

.page-title {
  font-size: 24px;
  font-weight: bold;
  background-color: #e5e5e5;
  padding: 10px 20px;
  margin-bottom: 20px;
  border-left: 5px solid #f7941d;
  color: #444;
}

.table-container {
  margin-top: 20px;
  background: white;
  border-radius: 8px;
  overflow-x: auto;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.06);
}

table {
  width: 100%;
  border-collapse: collapse;
}

th {
  background-color: #f7941d;
  color: white;
  padding: 12px;
  text-align: left;
}

td {
  padding: 12px;
  border-bottom: 1px solid #eee;
  color: #333;
}
</style>
