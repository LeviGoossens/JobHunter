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
    <div class="content">
      <div class="title-row">
        <span class="title">{{ grade }} in {{ subject }}</span>
      </div>
      <div class="item-subtitle">{{ institution }}</div>
      <div class="period">
        {{ format(startDate, 'LLL / yyyy') }} - {{ format(endDate, 'LLL / yyyy')
        }}<span class="spacer"> | </span>
        <span class="location">{{ location }}</span>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
