<script setup lang="ts">
defineProps<{
  groupSkill: string
  subSkills: string[]
}>()
</script>

<template>
  <li class="skill-group">
    <span class="skill-group-title">{{ groupSkill }}</span>
    <ul class="skill-subskills">
      <li v-for="subSkill in subSkills">{{ subSkill }}</li>
    </ul>
  </li>
</template>

<style scoped>

</style>