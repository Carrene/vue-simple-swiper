<template>
  <div class="simple-swiper" :style="slideStyle">
    <img :src="leftIcon">
    <div>
      <div class="swiper-content" :style="swiperContent">
        <slot></slot>
      </div>
    </div>
    <img :src="rightIcon">
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
    },
    swiperContent () {
      return {
        gridTemplateColumns: `repeat(${ this.imagePerview }, 1fr)`
      }
    },
    arrowStyle () {
      if (this.arrowSize) {
        return {
          width: `${this.arrowSize}px`
        }
      } else {
      }
    }
  },
  props: {
    imagePerview: {
      type: Number,
      default: 3
    },
    width: {
      type: Number,
      default: 80
    },
    height: {
      type: Number,
      default: 80
    },
    rightIcon: {
      type: String,
      default: require('@/assets/right-arrow.svg')
    },
    leftIcon: {
      type: String,
      default: require('@/assets/left-arrow.svg')
    },
    arrowSize: {
      type: Number,
      default: null
    }
  }
}
</script>
<style lang="sass">
.simple-swiper
  display: grid
  grid-template-column: auto 1fr auto
  .swiper-content
    display: grid
    overflow: hidden
    grid-auto-flow: column
</style>
