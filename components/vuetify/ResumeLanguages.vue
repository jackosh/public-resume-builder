<script setup lang="ts">
    const props = defineProps(['languages', 'styles']);
</script>

<template>
  <div
    :class="styles.mainTitleSizeClass"
  >
    Sprachen
  </div>
  <v-card flat>
    <v-card-text>
      <ul
      >
        <li v-for="(lang, key) in languages" :key="key">
          {{ lang }}
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