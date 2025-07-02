<template>
  <div class="course-filter">
    <div class="filter-group">
      <label>Semester:</label>
      <select v-model="selectedSemester">
        <option disabled value="">Select Semester</option>
        <option v-for="sem in semesters" :key="sem" :value="sem">
          {{ sem }}
        </option>
      </select>
    </div>

    <div class="filter-group">
      <label>Course:</label>
      <select v-model="selectedCourse">
        <option disabled value="">Select Course</option>
        <option v-for="course in courses" :key="course" :value="course">
          {{ course }}
        </option>
      </select>
    </div>
  </div>
</template>

<script setup>
import { ref, watch } from 'vue'

const semesters = ['Spring-2025', 'Fall-2024', 'Spring-2024']
const courses = [
  'Cyber Security',
  'Database Administration',
  'Software Quality Assurance',
  'Data Science Lab',
]

const selectedSemester = ref('')
const selectedCourse = ref('')

// Emit selected values to parent page
const emit = defineEmits(['update'])

watch([selectedSemester, selectedCourse], () => {
  emit('update', {
    semester: selectedSemester.value,
    course: selectedCourse.value,
  })
})
</script>

<style scoped>
.course-filter {
  display: flex;
  gap: 2rem;
  background-color: #f7941d; /* yellow-ish */
  padding: 12px 20px;
  border-radius: 6px;
  align-items: center;
  flex-wrap: wrap;
}
.filter-group {
  display: flex;
  flex-direction: column;
  font-size: 14px;
}
select {
  padding: 6px 12px;
  margin-top: 4px;
  border-radius: 4px;
  border: 1px solid #ccc;
}
</style>
