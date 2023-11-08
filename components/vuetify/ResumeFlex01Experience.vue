<script setup lang="ts">
    const props = defineProps(['experience', 'styles']);
</script>

<template>
  <v-card
    v-for="(job, key) in experience"
    :key="key"
    class="mb-4"
  >
    <v-card-title
      class="d-flex flex-nowrap flex-row"
    >
      <v-row>
        <v-col
          md="8"
        >
          {{ job.firmName }}
        </v-col>
        <v-col class="flex-grow-0 flex-shrink-1">
          {{ job.dateFrom }} - {{job.dateTo}}
        </v-col>
      </v-row>
    </v-card-title>
    <v-card-subtitle class="text-subtitle">
      {{ job.role }}
    </v-card-subtitle>
    <v-card-text>
      <ul
      >
        <li
          v-for="(task, taskKey) in job.tasks"
          :key="taskKey"
        >
          {{ task }}
        </li>
      </ul>
    </v-card-text>
  </v-card>
</template>

<style scoped>
  ul {
    list-style-type: circle;
    margin-left: 1.5rem;
  }
</style>
