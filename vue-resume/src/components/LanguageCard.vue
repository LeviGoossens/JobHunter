<script setup lang="ts">
defineProps<{
  language: string
  grade: string
}>()
</script>

<template>
  <strong>{{ language }}</strong> | {{ grade }}
</template>

<style scoped>

</style>