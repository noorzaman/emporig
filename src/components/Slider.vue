<template>
  <div class='carousel-view'>
    <transition-group
      class='carousel'
      tag="div">
      <div
        v-for="slide in slides"
        class='slide'
        :key="slide.id">
        <img :src="'/static/images/carousel/' + slide.image"  :alt="slide.image" class="img-thumbnail">
      </div>
    </transition-group>
    <div class='carousel-controls'>
      <input type="image" src='/static/images/prev.png' class='carousel-controls_prev' @click="previous">
      <input type="image" src='/static/images/next.png' class='carousel-controls_next' @click="next">
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      slides: [
        {
          id: 1,
          image: 'conference-room.jpeg'
        },
        {
          id: 2,
          image: 'cozy-room.jpeg'
        },
        {
          id: 3,
          image: 'calm-room.jpeg'
        },
        {
          id: 4,
          image: 'red-room.jpeg'
        },
        {
          id: 5,
          image: 'zen-room.jpeg'
        }
      ]
    }
  },
  methods: {
    next () {
      const first = this.slides.shift()
      this.slides = this.slides.concat(first)
    },
    previous () {
      const last = this.slides.pop()
      this.slides = [last].concat(this.slides)
    }
  }
}
</script>

<style>
</style>
