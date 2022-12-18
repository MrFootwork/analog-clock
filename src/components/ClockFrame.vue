<script setup lang="ts">

</script>

<template>
  <div class="wrapper">
    <div class="outer frame">
      <div class="inner frame">
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
// @import './../scss/mixins';
@import '@/scss/mixins';

.wrapper {
  position: absolute;

  display: flex;
  align-items: center;
  justify-content: center;

  .frame {
    border-radius: 50%;
    position: absolute;

    &.outer {
      border: 3rem solid hwb(174 24% 12%);
      @include setFrameSize();

      display: flex;
      align-items: center;
      justify-content: center;

      & .inner {
        border: 1rem solid hwb(93 24% 12%);
        @include setFrameSize();

      }
    }


  }
}
</style>