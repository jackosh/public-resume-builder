<script setup lang="ts">
    const props = defineProps(['applicant']);
</script>

<template>
  <!-- Address and Contact -->
  <v-container
    class="bg-surface-variant text-small"
  >
    <!-- Contact - Header -->
    <div class="text-h4 text-center mb-4">Kontakt</div>
    <!-- Email -->
    <v-row>
      <v-col
        cols="2"
      >
        <v-icon
          size="medium"
          icon="mdi-email"
        ></v-icon>
      </v-col>
      <v-col>
        {{ applicant.email}}
      </v-col>
    </v-row>
    <!-- Phone -->
    <v-row>
      <v-col
        cols="2"
      >
        <v-icon
          size="medium"
          icon="mdi-phone"
        ></v-icon>
      </v-col>
      <v-col>
        {{ applicant.telephone }}
      </v-col>
    </v-row>
    <!-- Home Address -->
    <v-row>
      <v-col
        cols="2"
      >
        <v-icon
          size="medium"
          icon="mdi-home"
        ></v-icon>
      </v-col>
      <v-col>
        {{ applicant.address.street }}
        <br />
        {{ applicant.address.zip }}
        {{ applicant.address.city }}
      </v-col>
    </v-row>
  </v-container>
</template>


<style scoped>
	.text-small {
		font-size: 12px;
	}
  @media print {
    .text-small {
      font-size: 9pt;
    }
  }
</style>