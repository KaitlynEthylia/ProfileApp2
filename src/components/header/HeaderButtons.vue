<template>
  <div class="header-buttons">
    <button class="header-button skew"><a :href="about">About</a></button>
    <button class="header-button skew"><a :href="socials">Socials</a></button>
    <button class="header-button skew"><a :href="reviews">Reviews</a></button>
    <button class="header-button" id="github">
      <a :href="github">To GitHub</a>
    </button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'HeaderButtons',
  props: ['about', 'socials', 'reviews', 'github'],
})
</script>

<style lang="scss">
.header-buttons {
  display: inline;
  margin: 0;
  padding: 0;
  top: 0;

  .header-button {
    display: inline;
    border: 0;
    height: 4rem;
    width: 6rem;
    margin-right: 0.2rem;
    background-position: center;
    transition: background 0.4s;
    background-color: var(--colour-inset-light);

    a {
      display: inline-block;
      color: var(--text-colour);
      text-decoration: none;
      font-size: 1rem;
      padding: 20% 10%;

      &:visited {
        color: var(--text-colour);
        text-decoration: none;
      }

    }

    &#github {
      height: 2rem;
      margin: 0 1rem;
      border-radius: var(--border-radius-low);
      box-shadow: var(--shadow-low);

      a {
        padding: 5%;
      }
    }

    &.skew {
      transform: skewX(-0.5rad);

      a {
        transform: skewX(0.5rad);
      }
    }

    &:hover {
      background: var(--colour-inset-light) radial-gradient(circle, transparent 1%, var(--colour-background-dark) 1%) center/15000%;
    }

    &:active {
      background-color: var(--colour-inset-light);
      background-size: 100%;
      transition: background 0s;
    }
  }
}
</style>
