<script setup lang="ts">
import { format } from 'date-fns'

defineProps<{
  startDate: Date
  endDate: Date
  position: string
  company: string
  location: string
  points?: string[]
}>()
</script>

<template>
  <div class="timeline-item">
    <div class="item-date">
      {{ format(startDate, 'LLL yyyy') }} - {{ format(endDate, 'LLL yyyy') }}
      <span class="item-location">| {{ location }}</span>
    </div>
    <div class="item-content">
      <div class="item-title-row">
        <span class="item-title">{{ position }}</span>
      </div>
      <div class="item-subtitle">{{ company }}</div>
      <ul v-if="points?.length" class="item-bullets">
        <li v-for="point in points" :key="point">{{ point }}</li>
      </ul>
    </div>
  </div>
</template>

<style scoped></style>
