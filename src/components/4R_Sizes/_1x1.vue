<template>
  <div id="size">
    <!-- <v-img v-for="n in 12" :key="'image'+n" src="./../../assets/logo.png" class="image" contain></v-img> -->
    <v-img v-for="n in 12" :key="'image'+n" :src="selected_image" class="image" contain></v-img>

    <div id="v-guide-lines">
      <div v-for="n in 3" :key="'v-guide'+n"></div>
    </div>

    <div id="h-guide-lines">
      <div v-for="n in 4" :key="'h-guide'+n"></div>
    </div>
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
  max-height: 1in;
  min-height: 1in;
  height: 1in;
  max-width: 1in;
  min-width: 1in; 
  width: 1in;
  margin: 10px;
}

#v-guide-lines {
  line-height: 0;
  position: absolute;
}

#v-guide-lines div {
  background: black;
  display: inline-block;
  height: 8px;
  width: 1px;
  margin-left: 115px;
}

#v-guide-lines div:before {
  background: black;
  content: '';
  height: 8px;
  position: absolute;
  top: 456px;
  width: 1px;
}

#h-guide-lines {
  position: absolute;
}

#h-guide-lines div {
  background: black;
  display: block;
  height: 1px;
  width: 8px;
  margin-top: 115px;
}

#h-guide-lines div:before {
  border-bottom: 1px solid black;
  content: '';
  left: 340px;
  position: absolute;
  width: 8px;
}

@media print {
  @page {
    size: 4in 6in;
  }
}
</style>