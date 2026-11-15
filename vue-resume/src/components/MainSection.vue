<script setup lang="ts">
defineProps<{
  title: string
}>()
</script>

<template>
  <section class="section-block">
    <h2 class="main-section-title">
      <slot name="icon"></slot>
      {{ title }}
    </h2>
    <slot></slot>
  </section>
</template>

<style scoped></style>
