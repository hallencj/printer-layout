<template>
  <div>
    <h6 class="font-weight-medium body-1 mb-4">3. Select an Image</h6>

    <div v-if="selected_image" id="for-print">
      <Size1x1 v-if="photo_size === '1x1'" :selected_image="selected_image" />
      <Size2x2 v-else-if="photo_size === '2x2'" :selected_image="selected_image" />
    </div>
  
    <div v-show="!selected_image" class="mt-2 mb-10">
      <input @change="getSelectedPhoto" type="file" ref="file" />
    </div>

    <v-btn :disabled="!selected_image" @click="print" class="mr-2" color="primary"><v-icon left>mdi-printer</v-icon> Print</v-btn>
    <v-btn v-if="selected_image" @click="clear">Clear</v-btn>
  </div>
</template>

<script>
import Size1x1 from './4R_Sizes/_1x1'
import Size2x2 from './4R_Sizes/_2x2'

export default {
  props: ['photo_size'],

  components: {
    Size1x1,
    Size2x2
  },

  data() {
    return {
      selected_image: ''
    }
  },

  methods: {
    getSelectedPhoto() {
      const result = this.$refs.file.files[0] 
      const url = URL.createObjectURL(result);
      this.selected_image = url
    },
    
    clear() {
      this.$refs.file.value = null
      this.selected_image = ''
    },

    print() {
      window.print()
    }
  }
}
</script>

<style scoped>
@media print {
  #for-print {
    left: 0;
    margin: 0;
    position: fixed;
    top: 0;
    visibility: visible;
  }
}
</style>
