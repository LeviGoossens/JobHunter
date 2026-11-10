<script setup lang="ts">
import { format } from 'date-fns'
defineProps<{
  name: string
  startDate: Date
  endDate: Date
  position: string
  points: string[]
  associatedWith?: string
  link?: string
  technologies?: string[]
}>()
</script>

<template>
  <div class="timeline-item full-width-project">
    <div class="period">
      {{ format(startDate, 'LLL / yyyy') }} - {{ format(endDate, 'LLL / yyyy') }}
    </div>
    <div class="content">
      <div class="title-row">
        <span class="item-title" style="font-size: 15px"
          ><a :href="link" target="_blank">{{ name }}</a></span
        >
        <span class="title-row-spacer"> | </span>
        <span class="associated-with">{{ associatedWith }}</span>
      </div>
      <div class="item-subtitle">{{ position }}</div>
      <div class="tech-stack" v-if="technologies">
        Technologieën
        <ul class="sub-bullets">
          <li v-for="technology in technologies">{{ technology }}</li>
        </ul>
      </div>
      <ul class="bullets">
        <li v-for="point in points">{{ point }}</li>
      </ul>
    </div>
  </div>
</template>

<style scoped></style>
