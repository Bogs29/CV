<template>
  <v-card
    color="grey lighten-4"
    light
  >
    <v-card-text>
      <content-section
        title="Objectives"
      >
       To secure a position in the organization that offers challenge and opportunity for my career development and at the same time to serve the
organization to the best of my capabilities.
      </content-section>
    
      <content-section
        v-if="educations"
        title="Education"
      >
        <v-layout
          v-for="(education, i) in educations"
          :key="i"
        >
          <v-flex md4>
            {{ education.from }} - {{ education.to }}
          </v-flex>
          <v-flex md8>
            <strong v-if="education.title">{{ education.title }}</strong>
            <div v-if="education.location">
              <i>{{ education.location }}</i>
            </div>
            <div v-if="education.description">
              {{ education.description }}
            </div>
          </v-flex>
        </v-layout>
      </content-section>
      <content-section
        v-if="skills"
        id="to-timeline"
        title="Skills"
      >
        <template slot="actions">
        </template>
        <v-layout wrap>
          <template
            v-for="(skill, i) in skills"
          >
            <v-flex
              v-if="skill.divider"
              :key="i"
              md12
              xs12
              mb-4
            />
            <v-flex
              v-else
              :key="i"
              md6
              xs12
            >
              <div
                class="mr-2 ml-2"
              >
                <div class="align-center">
                  <v-icon
                    small
                  >
                    {{ skill.icon }}
                  </v-icon>
                  {{ skill.title }}
                </div>
                <v-progress-linear
                  class="progress"
                  color="secondary"
                  height="3"
                  :value="skill.value"
                />
              </div>
            </v-flex>
          </template>
        </v-layout>
      </content-section>
       <content-section
        v-if="experiences"
        title="My Experiences"
      >
        <v-layout
          v-for="(experiences, i) in experiences"
          :key="i"
        >
          <v-flex md4>
            {{ experiences.from }} - {{ experiences.to }}
          </v-flex>
          <v-flex md8>
            <strong v-if="experiences.title">{{ experiences.title }}</strong>
            <div v-if="experiences.location">
              <i>{{ experiences.location }}</i>
            </div>
            <div v-if="experiences.description">
              {{ experiences.description }}
            </div>
          </v-flex>
        </v-layout>
      </content-section>
           </content-section>
       <content-section
        v-if="References"
        title="References"
      >
        <v-layout
          v-for="(References, i) in References"
          :key="i"
        >
          <v-flex md4>
            {{ References.from }} - {{ References.to }}
          </v-flex>
          <v-flex md8>
            <strong v-if="References.title">{{ References.title }}</strong>
            <div v-if="References.location">
              <i>{{ References.location }}</i>
            </div>
            <div v-if="References.description">
              {{ References.description }}
            </div>
          </v-flex>
        </v-layout>
      </content-section>
     
      <content-section>
           <i>"I hereby Certify that the above Information is true and correct to the best of my knowledge  and belief". </i>
      </content-section>
           
      <content-section>
        <center><b><u>Gabrielle Valencia</u> </b> </center>
               <center> <i>Applicant</i> </center>

      </content-section>
    
    </v-card-text>
  </v-card>
  
</template>

<script>
import ContentSection from '@/views/dark-template/content/Section'
export default {
  name      : 'MainContent',
  components: { ContentSection },
  data      : () => ({
  
    educations: [
       {
        from       : '2021',
        to         : 'Present',
        title      : 'Master of Information Technology',
        location   : 'Holy Angel University',
      },
      {
        from       : '2015',
        to         : '2019',
        title      : 'Bachelor of Information Technology',
        location   : 'Lyceum of the Philippines University',
      },
    ],
    skills: [
      {
        title: 'HTML',
        icon : 'mdi-language-html',
        value: 80,
      },
      {
        title: 'JavaScript',
        icon : 'mdi-language-javascript',
        value: 60,
      },
      {
        title: 'CSS',
        icon : 'mdi-CSS',
        value: 80,
      },
      {
        title: 'Vue.js Framework',
        icon : 'mdi-vuejs',
        value: 60,
      },
     
    
    ],
       experiences: [
      {
        from       : '2019',
        to         : '2022',
        title      : 'Concentrix Clark',
        location   : 'Clark, Pampanga',
      },
    ],
    References: [
      {
         title      : 'Available Upon Request',

    
      },
    ],
  }),
}
</script>

<style scoped>
.title {
  border-bottom: 2px #bfbfbf solid;
  line-height: 1.5 !important;
}
.progress {
  margin-top: 0.1rem;
}
</style>
