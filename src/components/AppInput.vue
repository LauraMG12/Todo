<script setup lang="ts"></script>
<template>
  <div class="input-text">
    <input type="text" placeholder="Item text" />
  </div>
</template>

<style scoped lang="scss">
.input-text {
  width: 100%;
  input {
    width: calc(100% - 25px);
    font-size: $font-size-secondary-desktop;
    color: var(--primary-text);
    background-color: transparent;
    border: none;
    &:focus {
      outline: none;
    }
    @media only screen and (max-width: $medium-breackpoint) {
      font-size: $font-size-secondary-mobile;
    }
  }
}
</style>
