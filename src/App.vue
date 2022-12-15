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

    <Template #frame>
      <ClockFrame />
    </Template>

    <Template #dial>
      <ClockDial />
    </Template>

    <Template #hands>
      <ClockHands />
    </Template>

  </ClockWrapper>

</template>

<style lang="scss">

</style>
