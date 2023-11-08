<script setup lang="ts">
    const props = defineProps(['experience']);
</script>

<template>
  <div>
    <v-list
      lines="two"
    >
      <v-list-item
        v-for="(job, key) in experience"
        :key="key"
        :title="`${job.firmName} ${job.dateFrom} - ${job.dateTo}`"
        :subtitle="job.role"
      >
        <v-list
          lines="one"
        >
          <v-list-item
            v-for="(task, taskKey) in job.tasks"
            :key="taskKey"
            :title="`${task}`"
          ></v-list-item>
        </v-list>
      </v-list-item>
    </v-list>
    </div>
</template>

