<script setup lang="ts">
    const props = defineProps(['experience']);
</script>

<template>
    <div
      v-for="(job, key) in props.experience"
      :key="key"
      class="mb-4"
    >
      <v-row>
        <v-col
          cols="4"
        >
          {{ job.role }}
        </v-col>
        <v-col
          cols="8"
        >
          {{ job.firmName }}
        </v-col>
      </v-row>

      <v-row
      >
        <v-col
          cols="4"
        >
          {{ `${job.dateFrom} - ${job.dateTo}` }}
        </v-col>
        <v-col
          cols="8"
        >
          <ul>
              <li class="mb-2"
                  v-for="(task, taskKey) in job.tasks"
                  :key="taskKey"
              >
                  {{ task }}

              </li>
          </ul>
          <strong>Techstack</strong>
          <v-chip-group>
              <v-chip
                  v-for="(tech, key) in job.techStack"
                  :key="key"
              >{{ tech }}</v-chip>
          </v-chip-group>
        </v-col>
      </v-row>
    </div>
</template>

