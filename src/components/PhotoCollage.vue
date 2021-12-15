<template>
  <div class="vue-photo-collage" :style="photoCollageStyle">
    <row-photos 
      @itemClick="(data, i) => $emit('itemClick', data, i)"
      v-for="(data, i) in layout" 
      :key="i"
      :height="height[i]"
      :photos="layoutPhotoMaps[i]"
      :layoutNum="layoutNum"
      :remainingNum="remainingNum"
      :showNumOfRemainingPhotos="showNumOfRemainingPhotos"
    ></row-photos>
  </div>
</template>

<script>
import RowPhotos from "./RowPhotos.vue";

export default {
  components: {
    RowPhotos,
  },
  props: {
    width: String,
    height: Array,
    layout: Array,
    layoutPhotoMaps: Object,
    layoutNum: Number,
    remainingNum: Number,
    showNumOfRemainingPhotos: Boolean,
  },
  computed: {
    photoCollageStyle() {
      return {
        width: this.width,
      };
    }
  }
}
</script>

<style lang="scss" scoped>
.vue-photo-collage {
  font-family: inherit;
}
</style>
