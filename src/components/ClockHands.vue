<script setup lang="ts">
import { watchEffect, ref, computed } from 'vue';

const hour = ref(0)
const minute = ref(0)
const second = ref(0)

const degHour = computed(() => {
  let hour12 = 0
  hour12 = hour.value > 12 ? hour.value - 12 : hour.value
  hour12 = hour12 + minute.value / 60
  hour12 = hour12 * 30

  return hour12
})
const degMinute = computed(() => {
  return minute.value * 6
})
const degSecond = computed(() => {
  return second.value * 6
})

watchEffect(() => {

  setInterval(() => {
    const currentTime = new Date()
    hour.value = currentTime.getHours()
    minute.value = currentTime.getMinutes()
    second.value = currentTime.getSeconds()
  }, 250)

})

</script>

<template>
  <div class="hands">
    <div class="hand hour" :style="{ rotate: degHour + 'deg' }"></div>
    <div class="hand minute" :style="{ rotate: degMinute + 'deg' }"></div>
    <div class="hand second" :style="{ rotate: degSecond + 'deg' }"></div>
    <div class="button"></div>
  </div>
</template>

<style scoped lang="scss">
@import '@/scss/mixins';

.hands {
  position: absolute;

  display: flex;
  align-items: center;
  justify-content: center;

  .hand {
    position: absolute;
    transform-origin: 50% 84%;
    // FIXME make this transition work
    // 1. go up to 60
    // 2. remove transition for split second
    // 3. set to 0
    // 4. add transition
    // transition: 1s ease-in-out;

  }

  .hour {
    @include setSizeHand($size: 24, $width: 30, $color: hwb(174 24% 50%));
  }

  .minute {
    @include setSizeHand($size: 39, $width: 0, $color: hwb(174 24% 36%));
  }

  .second {
    background-color: hsl(0, 100%, 40%);
    border: 1px solid hsl(0, 100%, 40%);
    border-radius: 15%;
    transform-origin: 35% 100%;

    @media (orientation: landscape) {
      height: 32vh;
      width: .5vh;
      translate: 0 -16.25vh;
    }

    @media (orientation: portrait) {
      height: 32vw;
      width: .5vw;
      translate: 0 -16.25vw;
    }
  }

  .button {
    height: 2vh;
    width: 2vh;
    border-radius: 50%;
    background-color: gold;
    z-index: 10;
    ;
  }
}
</style>