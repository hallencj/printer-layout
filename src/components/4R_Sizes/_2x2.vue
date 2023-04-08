<template>
  <div id="size">
    <v-img v-for="n in 4" :key="'image'+n" src="./../../assets/logo.png" class="image" contain></v-img>
    <!-- <v-img v-for="n in 4" :key="'image'+n" :src="selected_image" class="image" contain></v-img> -->
  </div>
</template>

<script>
export default {
  props: ['selected_image']
}
</script>

<style scoped>
#size {
  align-content: flex-start;
  display: flex;
  flex-wrap: wrap;
  height: 6in;
  position: relative;
  width: 4in;
}

.image {
  max-height: 2in;
  min-height: 2in;
  height: 2in;
  max-width: 2in;
  min-width: 2in; 
  width: 2in;
  margin: 10px;
}
</style>