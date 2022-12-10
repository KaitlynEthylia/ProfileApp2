<template>
  <header class="header" ref="header">
    <div class="header-left header-child">
      <ThemeSwitcher @toggleTheme="toggleTheme"></ThemeSwitcher>
      <ProfilePicture
        start="50"
        stop="200"
        max="16"
        min="8"></ProfilePicture>
    </div>
    <div class="header-middle header-child">
      <Rainbow width="calc(30vw - 2rem)"></Rainbow>
    </div>
    <div class="header-right header-child">
      <HeaderButtons></HeaderButtons>
    </div>
  </header>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import ThemeSwitcher from "./header/ThemeSwitcher.vue";
import ProfilePicture from "./header/ProfilePicture.vue";
import Rainbow from "./header/Rainbow.vue";
import HeaderButtons from "./header/HeaderButtons.vue";
import profilePicture from "./header/ProfilePicture.vue";

export default defineComponent({
  name: 'PageHeader',
  components: { ThemeSwitcher, ProfilePicture, Rainbow, HeaderButtons },
  methods: {
    toggleTheme() {
      this.$emit("toggleTheme")
    },
  },
})
</script>

<style lang="scss">
.header{
  background-color: var(--colour-background-dark);
  transition: var(--trans);
  box-shadow: var(--shadow-low);

  width: 100%;
  height: 4rem;

  display: flex;
  justify-content: left;
  align-items: center;

  position: fixed;

  .header-left {
    flex-grow: 2;
  }

  .header-middle {
    flex-grow: 2;
    justify-content: center;
    display: flex;

    @media screen and (max-width: 70rem) {
      visibility: collapse;
    }
  }

  .header-right {
    display: flex;
    justify-content: right;
  }
}
</style>
