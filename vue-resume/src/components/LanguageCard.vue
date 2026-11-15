<script setup lang="ts">
defineProps<{
  language: string
  grade: string
}>()
</script>

<template>
  <div class="language-item"><strong>{{ language }}</strong> | {{ grade }}</div>
</template>

<style scoped></style>
