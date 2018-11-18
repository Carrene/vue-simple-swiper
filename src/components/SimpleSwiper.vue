<template>
  <div class="simple-swiper" :style="slideStyle">
    <img src="./../assets/left-arrow.svg">
    <div>
      <slot></slot>
    </div>
    <img src="./../assets/right-arrow.svg">
  </div>
</template>

<script>
export default {
  name: 'SimpleSwiper',
  computed: {
    slideStyle () {
      return {
        width: `${this.width}px`,
        height: `${this.height}px`
      }
    }
  },
  props: {
    count: {
      type: Number,
      default: 0
    },
    width: {
      type: Number,
      default: 80
    },
    height: {
      type: Number,
      default: 80
    }
  }
}
</script>
<style lang="sass">
.simple-swiper
  display: grid
  grid-template-column: auto 1fr auto
</style>
