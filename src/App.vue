<template>
  <div id="frame">
    <PageHeader @toggleTheme="toggleTheme"></PageHeader>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import CodeBlock from './components/about/CodeBlock.vue'
import ThemeSwitcher from './components/header/ThemeSwitcher.vue'
import HeaderButtons from './components/header/HeaderButtons.vue'
import Rainbow from "./components/header/Rainbow.vue";
import ProfilePicture from "./components/header/ProfilePicture.vue";
import PageHeader from "./components/PageHeader.vue";

export default defineComponent({
  components: { PageHeader, ProfilePicture, Rainbow, ThemeSwitcher, CodeBlock, HeaderButtons },
  data() {
    return {
      dark: false,
    }
  },
  methods: {
    toggleTheme() {
      document.body.classList.toggle('dark')
    },
  }
})
</script>

<style lang="scss">
  #frame {
    height: 400vh;
  }
</style>
