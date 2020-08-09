<template>
  <div>
    <input id="display" v-model="displayedValue" />
  </div>
</template>

<script>
export default {
  props: ["displayedValue"],
};
</script>

<style>
#display {
  width: 98.7%;
  height: 50px;
  font-size: xx-large;
  grid-column: 1 / 5;
  display: flex;
  justify-content: flex-end;
  align-items: center;
  background-color: #333;
  color: #fff;
}
</style>