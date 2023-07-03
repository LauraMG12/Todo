<script setup lang="ts">
import Navbar from "./components/Navbar.vue";
import Todo from "./components/Todo.vue";
</script>

<template id="app">
  <Navbar id="navbar" />
  <Todo id="todo" />
  <div id="footer">
    <p>@ 2023 Laura Mañogil González</p>
  </div>
</template>

<style lang="scss">
@import "@/styles/_variables.scss";

body {
  margin: 0;
  box-sizing: border-box;
  overflow: hidden;
}
p {
  margin: 0;
}
#app {
  background-color: var(--background-1);
  font-family: $font-family;

  #navbar {
    width: 100vw;
    height: 10vh;
  }

  #todo {
    width: 885px;
    height: calc(85vh - 60px);
    margin: 40px auto 20px;
    @media only screen and (max-width: $medium-breackpoint) {
      height: calc(90vh);
      margin-bottom: 0;
      width: auto;
    }
  }

  #footer {
    width: 100vw;
    height: 5vh;
    cursor: default;
    p {
      font-size: $font-size-small-desktop;
      color: var(--secondary-text);
      text-align: center;
      margin-top: 30px;
    }
    @media only screen and (max-width: $medium-breackpoint) {
      display: none;
    }
  }
  ::-webkit-scrollbar {
    width: 6px;
  }
  /* Handle */
  ::-webkit-scrollbar-thumb {
    background: var(--secondary-text);
    border-radius: 6px;
  }

  ::-moz-selection {
    color: var(--primary-text);
    background: $primary;
  }
  &[theme="dark-mode"] {
    ::selection {
      color: var(--primary-text);
      background: $primary;
    }
  }
  &[theme="light-mode"] {
    ::selection {
      color: var(--primary-text);
      background: $primary-lighter;
    }
  }
  &[theme="dark-mode"] {
    --background-1: #{$dark-background-1};
    --background-2: #{$dark-background-2};
    --background-3: #{$dark-background-3};
    --background-4: #{$dark-background-4};
    --primary-text: #{$dark-primary-text};
    --secondary-text: #{$dark-secondary-text};
  }
  &[theme="light-mode"] {
    --background-1: #{$light-background-1};
    --background-2: #{$light-background-2};
    --background-3: #{$light-background-3};
    --background-4: #{$light-background-4};
    --primary-text: #{$light-primary-text};
    --secondary-text: #{$light-secondary-text};
  }
}
</style>
