<script setup lang="ts">
import { format } from 'date-fns'

defineProps<{
  name: string
  startDate: Date
  endDate?: Date
  position: string
  points: string[]
  associatedWith?: string
  link?: string
  technologies?: string[]
  technologyGroups?: { label: string; items: string[] }[]
}>()
</script>

<template>
  <div class="timeline-item full-width-project">
    <div class="item-date">
      {{ format(startDate, 'LLL yyyy') }} -
      <template v-if="endDate">{{ format(endDate, 'LLL yyyy') }}</template>
      <template v-else>Present</template>
    </div>
    <div class="item-content">
      <div class="item-title-row">
        <span class="item-title project-title">
          <a v-if="link" :href="link" target="_blank" rel="noopener noreferrer">{{ name }}</a>
          <template v-else>{{ name }}</template>
        </span>
        <span v-if="associatedWith" class="item-institution">| {{ associatedWith }}</span>
      </div>
      <div class="item-subtitle">{{ position }}</div>
      <div v-if="technologies?.length" class="tech-stack">
        Technologies:
        <span class="tech-list">{{ technologies.join(', ') }}</span>
      </div>
      <template v-if="technologyGroups?.length">
        <div class="tech-stack">Technologies</div>
        <ul class="sub-bullets">
          <li v-for="group in technologyGroups" :key="group.label">
            {{ group.label }}: {{ group.items.join(', ') }}
          </li>
        </ul>
      </template>
      <ul class="item-bullets">
        <!-- eslint-disable-next-line vue/no-v-html -->
        <li v-for="point in points" :key="point" v-html="point"></li>
      </ul>
    </div>
  </div>
</template>

<style scoped></style>
