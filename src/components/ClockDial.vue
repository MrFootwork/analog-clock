<script setup lang="ts">

</script>

<template>
  <div class="wrapper">
    <!-- <div class="dial marks">
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
    </div> -->
    <div class="dial numbers">
      <div class="hour hour-1">1</div>
      <div class="hour hour-2">2</div>
      <div class="hour hour-3">3</div>
      <div class="hour hour-4">4</div>
      <div class="hour hour-5">5</div>
      <div class="hour hour-6">6</div>
      <div class="hour hour-7">7</div>
      <div class="hour hour-8">8</div>
      <div class="hour hour-9">9</div>
      <div class="hour hour-10">10</div>
      <div class="hour hour-11">11</div>
      <div class="hour hour-12">12</div>
    </div>
  </div>
</template>

<style scoped lang="scss">
@import '@/scss/mixins';

.wrapper {
  position: absolute;
  display: block;

  .dial.marks {
    background-color: white;

    @include setSize(70);
    @include on-circle_marks($item-count: 12, $circle-size: 60);

    .hour {
      border-radius: 4px;

      // adjust positioning of marks
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

      // adjust positioning of marks
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

  .dial.numbers {
    background-color: white;

    @include setSize(70);
    @include on-circle_numbers($item-count: 12, $circle-size: 60);

    .hour {
      position: absolute;
      display: inline;

      @include setSize(14);
      @include setSizeFont(11);
      text-align: center;
      vertical-align: middle;
    }
  }
}
</style>