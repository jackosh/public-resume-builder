<script setup lang="ts">
    const props = defineProps(['education', 'styles']);
</script>

<template>
  <div
    :class="styles.mainTitleSizeClass"
  >
    Hochschulbildung/Weiterbildung
  </div>
  <v-card flat>
    <v-card-text>
      <ul
      >
        <li v-for="(station, stationKey) in education" :key="stationKey">
          {{ station.instituteName }}
          {{ station.dateFrom }} - 
          {{ station.dateTo }}
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
