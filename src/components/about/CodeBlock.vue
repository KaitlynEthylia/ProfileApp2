<template>
  <div class="codeblock line-numbers">
    <header class="codeblock-header">
      <svg height="1em" width="1em">
        <circle cx="0.5em" cy="0.5em" r="0.5em" style="fill: #ff5555"></circle>
      </svg>
      <svg height="1em" width="1em">
        <circle cx="0.5em" cy="0.5em" r="0.5em" style="fill: #ffdd66"></circle>
      </svg>
      <svg height="1em" width="1em">
        <circle cx="0.5em" cy="0.5em" r="0.5em" style="fill: #77ff55"></circle>
      </svg>
      <span class="codeblock-header-title">{{ name }}</span>
    </header>
    <pre>
      <code :class="'language-' + language">
        {{ text }}
      </code>
    </pre>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'CodeBlock',
  props: ['language', 'text', 'name', 'margin'],
})
</script>

<style lang="scss">
@font-face {
  font-family: 'CaskaydiaCove';
  src: url('../../assets/fonts/CaskaydiaCove.ttf');
}

.codeblock {
  background-color: var(--codeblock-header);
  overflow: hidden;
  border-radius: var(--border-radius-med);
  opacity: 80%;
  box-shadow: var(--shadow);
  margin: v-bind(margin);

  * {
    font-family: 'CaskaydiaCove', 'Roboto Mono', monospace;
    font-weight: 500;
  }

  .codeblock-header {
    display: flex;
    align-items: center;
    height: 1.6rem;

    .codeblock-header-title {
      color: gray;
      margin-left: 1vw;
    }

    svg {
      margin-left: 0.5rem;
      transition: var(--trans);
      &:hover {
        scale: 1.1;
        filter: saturate(90%) brightness(90%);
      }
    }
  }

  pre {
    background-color: var(--codeblock) !important;
  }

  transition: var(--trans);
  &:hover {
    scale: 1.05;
  }
}
</style>
