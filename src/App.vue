<script setup lang="ts">
import SelectorStyle from '@/components/SelectorStyle.vue'
import ClockWrapper from '@/components/ClockWrapper.vue'
import ClockFrame from '@/components/ClockFrame.vue'
import ClockDial from '@/components/ClockDial.vue'
import ClockHands from '@/components/ClockHands.vue'
</script>

<template>

  <SelectorStyle />
  <ClockWrapper>

    <template #frame>
      <ClockFrame />
    </template>

    <template #dial>
      <ClockDial />
    </template>

    <template #hands>
      <ClockHands />
    </template>

  </ClockWrapper>

</template>

<style lang="scss">

</style>
