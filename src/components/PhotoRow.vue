<template>
  <div class="vue-photo-row" :style="{ height: rowHeight }">
    <slot></slot>
  </div>
</template>

<script>
export default {
  props: {
    rowHeight: String,
  },
};
</script>

<style lang="scss" scoped>
.vue-photo-row {
  
  display: flex;
  border: 1px solid #ddd;
  box-sizing: border-box;

  & + & {
    margin-top: 2px;
  }

}
</style>
