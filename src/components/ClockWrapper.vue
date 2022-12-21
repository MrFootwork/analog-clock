<script setup lang="ts">

</script>

<template>
  <div class="wrapper">
    <slot name="frame"></slot>
    <slot name="dial"></slot>
    <slot name="hands"></slot>

    <img class="bg__image" id="bg__btm-right" src="/bg__btm-right.svg" alt="">
    <img class="bg__image" id="bg__left" src="/bg__left.svg" alt="">
    <img class="bg__image" id="bg__top-right" src="/bg__top-right.svg" alt="">
  </div>
</template>

<style scoped lang="scss">
.wrapper {
  --bg_image_size: 20rem;
  background-color: bisque;
  width: 100vw;
  height: 100vh;

  position: absolute;

  display: flex;
  justify-content: center;
  align-items: center;

  z-index: -20;

  .bg__image {
    width: var(--bg_image_size);
    height: var(--bg_image_size);
    z-index: -10;
    filter: blur(2px);

    &#bg__btm-right {
      position: absolute;
      bottom: 0;
      right: 0;
    }

    &#bg__left {
      position: absolute;
      left: 0;
      bottom: 20vh;
    }

    &#bg__top-right {
      position: absolute;
      top: 0;
      right: 0;
    }
  }




}
</style>