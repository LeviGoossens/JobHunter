<script setup lang="ts">
import { format } from 'date-fns'

defineProps<{
  startDate: Date
  endDate: Date
  grade: string
  subject: string
  institution: string
  location: string
}>()
</script>

<template>
  <div class="timeline-item">
    <div class="item-date">
      {{ format(startDate, 'LLL yyyy') }} - {{ format(endDate, 'LLL yyyy') }}
      <span class="item-location">| {{ location }}</span>
    </div>
    <div class="item-content">
      <div class="item-title">{{ grade }} in {{ subject }}</div>
      <div class="item-subtitle">{{ institution }}</div>
    </div>
  </div>
</template>

<style scoped></style>
