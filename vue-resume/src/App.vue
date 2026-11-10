<script setup lang="ts">
import ProjectCard from '@/components/ProjectCard.vue'
import JobCard from '@/components/JobCard.vue'
const date1: Date = new Date(2026, 1)
const date2: Date = new Date(2026, 5)
const date3: Date = new Date(2021, 2)
const date4: Date = new Date(2023, 9)
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

  <JobCard
    location="Tessenderlo"
    :startDate="date3"
    :endDate="date4"
    position="EMC - Assistant"
    company="Melexis"
    :points="['a', 'b', 'c']"
    :technologies="['C#', 'javascript']"
  ></JobCard>
</template>

<style scoped></style>
