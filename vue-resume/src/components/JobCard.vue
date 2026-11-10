<script setup lang="ts">
import { format } from 'date-fns'
defineProps<{
  startDate: Date
  endDate: Date
  position: string
  company: string
  location: string
  points: string[]
}>()
</script>
<template>
  <div class="timeline-item">
    <div class="content">
      <div class="title-row">
        <span class="title">{{ position }}</span>
      </div>
      <div class="period">
        {{ format(startDate, 'LLL / yyyy') }} - {{ format(endDate, 'LLL / yyyy')
        }}<span class="spacer"> | </span>
        <span class="location">{{ location }}</span>
      </div>
      <div class="item-subtitle">{{ company }}</div>
      <ul class="bullets">
        <li v-for="point in points">{{ point }}</li>
      </ul>
    </div>
  </div>
</template>

<style scoped></style>
