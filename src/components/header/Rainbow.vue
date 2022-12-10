<template>
  <svg class="rainbow-container" xmlns="http://www.w3.org/2000/svg" :width="width">
    <rect class="rainbow" :width="width" height="calc(6rem / 6)" y="calc(0rem / 6)" x="0" fill="#f99"/>
    <rect class="rainbow" :width="width" height="calc(6rem / 6)" y="calc(4rem / 6)" x="0" fill="#fc9"/>
    <rect class="rainbow" :width="width" height="calc(6rem / 6)" y="calc(8rem / 6)" x="0" fill="#ff9"/>
    <rect class="rainbow" :width="width" height="calc(6rem / 6)" y="calc(12rem / 6)" x="0" fill="#bf9"/>
    <rect class="rainbow" :width="width" height="calc(6rem / 6)" y="calc(16rem / 6)" x="0" fill="#9ff"/>
    <rect class="rainbow" :width="width" height="calc(4rem / 6)" y="calc(20rem / 6)" x="0" fill="#c9f"/>
  </svg>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'Rainbow',
  props: ['width'],
})
</script>

<style lang="scss">
  .rainbow-container {
    display: flex;
    height: 4rem;
    transform: skewX(-0.5rad);
  }

  .dark .rainbow-container .rainbow {
    filter: brightness(0.6) saturate(1.3) contrast(2);
  }
</style>