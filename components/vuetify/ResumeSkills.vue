<script setup lang="ts">
    const props = defineProps(['skills']);
</script>

<template>
    <div
        class="text-h4 text-center"
    >Skills</div>
    <v-chip-group>
        <v-chip
            v-for="(skill, key) in skills"
            :key="key"
        >{{ skill }}</v-chip>
    </v-chip-group>
</template>
