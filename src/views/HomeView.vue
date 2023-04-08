<template>
  <v-card id="not-for-print" class="ma-12">
    <div class="white--text primary px-6 py-2">
      <h1 class="font-weight-medium">Printing Layout Application - v1.0</h1>
      <h3 class="font-weight-regular mt-n1">by Hallen Cj Corpuz</h3>
    </div>
    
    <div class="pa-6">
      <Step1 :selected_size="selected_size" class="d-print-none" />
      <Step2 :selected_size="selected_size" class="d-print-none" />
      <Step3 :photo_size="selected_size.photo" />
    </div>
  </v-card>
</template>

<script>
import Step1 from '@/components/Step1'
import Step2 from '@/components/Step2'
import Step3 from '@/components/Step3'

export default {
  components: {
    Step1,
    Step2,
    Step3
  },

  data() {
    return {
      selected_size: {
        paper: '4R',
        photo: '1x1'
      }
    }
  }
}
</script>

<style scoped>
@media print {
  #not-for-print {
    visibility: hidden;
  }
}
</style>