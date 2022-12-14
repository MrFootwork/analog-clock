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
  top: 5vw;
  right: 10vw;
  cursor: pointer;

  min-width: 25vw;
  min-height: 15vw;

  text-align: center;
  font-family: 'Mountains of Christmas', cursive;

  @media (orientation: landscape) {
    font-size: 5vh;
  }

  @media (orientation: portrait) {
    font-size: 10vw;
  }


  & .style-label {}

  & .style-container {
    visibility: hidden;
    display: none;

    display: flex;
    align-items: center;

    & .style-item {}
  }

  & .style-container:hover {
    visibility: visible;

    display: flex;
    align-items: center;

    & .style-item {}
  }

  &:hover .style-container,
  & .style-container:hover .style-item,
  & .style-container .style-item:hover {
    visibility: visible;
    display: block;

    background: none;
    outline: none;
    cursor: pointer;

  }
}
</style>