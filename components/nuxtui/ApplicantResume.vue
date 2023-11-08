<template>
  <div class="p-4">
    <!-- Header with applicant name and image -->
    <div class="flex justify-between items-center mb-6">
      <div>
        <h1 class="text-2xl font-bold">{{ applicant.firstName }} {{ applicant.secondName }}</h1>
        <!-- Additional applicant info -->
      </div>
      <div>
        <img :src="applicant.profilImagePath" alt="Profile Picture" class="w-24 h-24 rounded-full"/>
      </div>
    </div>
    <div>
      <h2 class="text-xl font-semibold mb-2">Zur Person</h2>
      <p>
        Geboren am: {{ applicant.birthDate }} in {{ applicant.birthPlace }}<br />
        {{ applicant.familyState }}
      </p>
    </div>

    <!-- Experience section -->
    <div class="mb-6">
      <h2 class="text-xl font-semibold mb-4">Experience</h2>
      <ul>
        <li v-for="job in experience" :key="job.firmName" class="mb-4">
          <h3 class="font-semibold">{{ job.firmName }} - {{ job.role }}</h3>
          <!-- Job details -->
          {{ job.dateFrom }} - {{ job.dateTo }}
          <!-- Role -->
          <strong>Rolle</strong> {{ job.role }}
          <h3 class="font-semibold"> Tasks </h3>
          <ul>
            <li v-for="(task, key) in job.tasks" :key="key" class="mb-4">
              {{ task }}
            </li>
          </ul>
        </li>
      </ul>
    </div>

    <!-- Education section -->
    <!-- Similar to experience section -->

    <!-- Languages section -->
    <!-- Similar structure -->
  </div>
</template>

<script lang="ts"> 
  import applicantData from '~/assets/applicant.json';
  export default {
    data() {
      return {
        applicant: applicantData.applicant,
        experience: applicantData.experience,
        education: applicantData.education,
        languages: applicantData.languages
      };
    }
  }
</script>

