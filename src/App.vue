<script>
import { defineComponent } from 'vue'
import AppHeader from './components/AppHeader.vue'
import AppMainTitle from './components/AppMainTitle.vue'
import AppOurActivity from './components/AppOurActivity.vue'
import AppOurValues from './components/AppOurValues.vue'
import AppOpportunities from './components/AppOpportunities.vue'
import AppNowStream from './components/AppNowStream.vue'
import AppPractice from './components/AppPractice.vue'
import AppQuestions from './components/AppQuestions.vue'
import AppRecruitingForm from './components/AppRecruitingForm.vue'

export default defineComponent({
  components: {
    AppHeader,
    AppMainTitle,
    AppOurActivity,
    AppOurValues,
    AppOpportunities,
    AppNowStream,
    AppPractice,
    AppQuestions,
    AppRecruitingForm,
  },

  setup() {},
})
</script>

<template>
  <AppHeader />
  <AppMainTitle />
  <AppOurActivity />
  <AppOurValues />
  <AppOpportunities />
  <AppNowStream />
  <AppPractice />
  <AppQuestions />
  <AppRecruitingForm />
</template>
