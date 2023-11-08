<script lang="ts">
  console.log('executing ApplicantResume without setup');
  // console.log('executing ApplicantResume with setup');
  import applicantData from '~/assets/applicant.json';

  export default {
      data() {
          return {
              applicant: applicantData.applicant,
              experience: applicantData.experience,
              education: applicantData.education,
              skills: applicantData.skills,
              languages: applicantData.languages,
              leftBarColor: "bg-blue",
              styles: {
                mainTitleSizeClass: "text-h6 bg-orange pa-4"
              },
          };
      }
  }
</script>

<template>
  <v-container
    fluid
    class="resumeWrapper bg-white"
  >
    <v-row>
      <!-- main left col -->
      <v-col
        sm="4"
        :class="`${leftBarColor} hero`"
      >
          <!-- Avatar -->
          <v-sheet
            :height="220"
            class="bg-transparent"
          >
            <div 
                class="text-center"
            >
                <v-avatar size="128" class="ma-4">
                <img :src="applicant.profilImagePath">
                </v-avatar>
            </div>
          </v-sheet>
          <div class="mb-4">
              <!-- Skills -->
              <VuetifyResumeSkills
                  :skills="skills"
              />
          </div>
          <!-- Address and Contact -->
          <VuetifyResumeAddressContact
            :applicant="applicant"
          />
      </v-col>
      <!-- main right col -->
      <v-col
        sm="8"
        no-gutters
        class="main"
      >
        <v-row
        >
          <v-col
          >
            <v-sheet
              class="bg-transparent"
              :height="220"
            >
              <!-- FirstName LastName -->
              <div class="text-h3 text-right mb-4">
                Lebenslauf
              </div>
              <v-card
                flat
              >
                <v-card-title>
                  {{ applicant.firstName }} {{ applicant.secondName }}
                </v-card-title>
                <v-card-subtitle>
                  Entwickler
                </v-card-subtitle>
                <v-card-text>
                  Geboren am {{ applicant.birthDate }} in {{ applicant.birthPlace }}<br />
                  ledig
                </v-card-text>
              </v-card>
            </v-sheet>
            <!-- Experience (Berufspraxis)-->
            <h2
                :class="styles.mainTitleSizeClass"
            >
              Berufspraxis
            </h2>
            
            <!-- Experience Flex -->
            <VuetifyResumeFlex01Experience
              :styles="styles"
              :experience="experience"
            />
            <!-- Experience List -->
            <!-- <VuetifyResumeList01Experience
                :experience="experience"
            /> -->

            <!-- Experience -->
            <!-- <VuetifyResumeExperience
                :experience="experience"
            /> -->
            <!-- Hochschulbildung/Weiterbildung -->
            <VuetifyResumeEducation
              :education="education"
              :styles="styles"
            />
            <!-- Languages -->
            <VuetifyResumeLanguages
              :styles="styles"
              :languages="languages"
            />
          </v-col>
        </v-row>
      </v-col>
    </v-row>
    <v-row>
        <v-card flat>
            <v-card-text>
                This Resume was created with Nuxt 3, Vuetify.<br />
                See complete source on <a href="https://github.com/jackosh/public-resume-builder">https://github.com/jackosh/public-resume-builder</a>
            </v-card-text>
        </v-card>
    </v-row>
  </v-container>
</template>

<style scoped>
@media print {
	p {
		font-size: 12pt;
	}
}
.v-container {
  /* border: 1px solid #ccc; */
}
.resumeWrapper {
    max-width: 1024px;
}
.hero {
  /* background: url('https://cdn.vuetifyjs.com/images/parallax/material.jpg');
  background-size: cover;
  height: 100vh; */
}
</style>
