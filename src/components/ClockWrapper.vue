<script setup lang="ts">

</script>

<template>
  <div class="wrapper">
    <slot name="frame"></slot>
    <slot name="dial"></slot>
    <slot name="hands"></slot>

    <img src="public/bg__btm-right.svg" alt="">
    <img src="public/bg__left.svg" alt="">
    <img src="public/bg__top-right.svg" alt="">
  </div>
</template>

<style scoped>
.wrapper {
  background-color: white;
  width: 100vw;
  height: 100vh;
  /* FIXME add mixins for theming */
}
</style>