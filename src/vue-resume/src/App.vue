<script setup lang="ts">
import ProjectCard from './components/ProjectCard.vue'
const date1: Date = new Date(2026, 1)
console.log(date1.toLocaleString())
const date2: Date = new Date(2026, 5)
</script>

<template>
  <h1>You did it!</h1>
  <p>
    Visit <a href="https://vuejs.org/" target="_blank" rel="noopener">vuejs.org</a> to read the
    documentation
  </p>
  <ProjectCard
    name="Sint-Vincentius-app"
    :startDate="date1"
    :endDate="date2"
    position="Developer"
    associatedWith="PXL smart-ICT"
    :points="['a', 'b', 'c']"
    :technologies="['C#', 'javascript']"
  ></ProjectCard>
</template>

<style scoped></style>
