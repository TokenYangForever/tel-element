<template>
  <div 
  class="tel-carousel-item"
  :style="{
    msTransform: translate,
    webkitTransform: translate,
    transform: translate
  }">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'carouselItem',
  props: {
    height: String,
    width: String
  },

  data () {
    return {
      translate: '',
      active: false
    }
  },

  methods: {
    setTranslate (index, actIndex) {
      const parentWidth = this.$parent.width
      this.translate = 'translateX(' + parentWidth * (index - actIndex) + 'px)'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.tel-carousel-item{
  width: 100%;
  height: 100%;
  position: absolute;
  transition: .4s ease-in-out;
}
</style>
