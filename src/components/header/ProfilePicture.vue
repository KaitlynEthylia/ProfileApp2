<template>
  <span class="pfp-container">
    <img class="pfp"
         ref="pfp"
         src="../../assets/images/pfp.webp"
         alt="profile picture"
         :style="`height: ${max}rem`">
  </span>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'ProfilePicture',
  props: ['start', 'stop', 'max', 'min'],
  created () {
    window.addEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll (event: Event) {
      const style = (<HTMLImageElement>this.$refs.pfp).style
      const scrollInVh = window.scrollY / window.innerHeight * 100
      const start = parseInt(this.start)
      const stop = parseInt(this.stop)
      const min = parseInt(this.min)
      const max = parseInt(this.max)

      style.height = `${this.calculateDifference(scrollInVh, start, stop, min, max)}rem`
    },
    calculateDifference(scroll:number, start:number, stop:number, final:number, initial:number) {
      if(scroll < start) { return initial }
      if(scroll > stop) {return final}

      return (scroll * (final - initial) - (final * start) + (initial * stop) ) / (stop - start)
    }
  },
})
</script>

<style lang="scss">
  .pfp-container .pfp {
    box-shadow: var(--shadow-low);
    margin-top: 1rem;
    position: absolute;
    border-radius: 50%;
    z-index: 1;
    transition: border-color 0.2s;
  }
</style>