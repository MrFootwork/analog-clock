<script setup lang="ts">

</script>

<template>
  <div class="wrapper">
    <div class="dial">
      <div class="hour hour-1"></div>
      <div class="hour hour-2"></div>
      <div class="hour hour-3"></div>
      <div class="hour hour-4"></div>
      <div class="hour hour-5"></div>
      <div class="hour hour-6"></div>
      <div class="hour hour-7"></div>
      <div class="hour hour-8"></div>
      <div class="hour hour-9"></div>
      <div class="hour hour-10"></div>
      <div class="hour hour-11"></div>
      <div class="hour hour-12"></div>
    </div>
  </div>
</template>

<style scoped lang="scss">
@import '@/scss/mixins';

.wrapper {
  position: absolute;
  display: block;

  .dial {
    background-color: white;

    @include setSize(70);
    border-radius: 50%;

    @include on-circle($item-count: 12, $circle-size: 60);

    .hour {
      @media (orientation: landscape) {
        translate: .3vh 1vh;
      }

      @media (orientation: portrait) {
        translate: .3vw 1vw;
      }
    }

    .hour:nth-of-type(3n + 1) {
      position: absolute;
      @include setSize(4, 8);
      background-color: black;

      @media (orientation: landscape) {
        translate: -.7vh -1.2vh;
      }

      @media (orientation: portrait) {
        translate: -.7vw -1.2vw;
      }
    }

    .hour:nth-of-type(3n + 2),
    .hour:nth-of-type(3n + 3) {
      position: absolute;
      @include setSize(2, 4);
      background-color: black;
    }
  }
}
</style>