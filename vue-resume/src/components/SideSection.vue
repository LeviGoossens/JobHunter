<script setup lang="ts">
defineProps<{
  title: string
}>()
</script>

<template>
  <div>
    <h2 class="sidebar-section-title">{{ title }}</h2>
    <slot></slot>
  </div>
</template>

<style scoped></style>
