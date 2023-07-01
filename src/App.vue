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
  background-color: $dark-background-1;
  font-family: $font-family;

  #navbar {
    width: 100vw;
    height: 10vh;
  }

  #todo {
    width: 885px;
    height: calc(85vh - 60px);
    margin: 40px auto 20px;
  }

  #footer {
    width: 100vw;
    height: 5vh;
    p {
      font-size: $font-size-small-desktop;
      color: $dark-secondary-text;
      text-align: center;
      margin-top: 30px;
    }
  }
  ::-webkit-scrollbar {
    width: 6px;
  }
  /* Handle */
  ::-webkit-scrollbar-thumb {
    background: $dark-secondary-text;
    border-radius: 6px;
  }

  ::-moz-selection {
    color: $dark-primary-text;
    background: $primary;
  }

  ::selection {
    color: $dark-primary-text;
    background: $primary;
  }
}
</style>
