<script setup lang="ts">

const styles = ['style 1', 'style 2']

</script>

<template>
  <div class="dropdown">
    <label class="style-label" for="dropdown">Styles</label>
    <ul class="style-container">
      <li class="style-item" v-for="style in styles">
        <button>{{ style }}</button>
      </li>
    </ul>
  </div>
</template>

<style scoped lang="scss">
.dropdown {
  position: absolute;
  top: 0;
  right: 0;

  & .style-label {
    color: violet;

    &:hover {
      color: green;
    }
  }

  & .style-container {
    visibility: hidden;
    display: none;


  }

  .style-label:hover+.style-container {
    visibility: visible;
    display: block;
  }
}
</style>