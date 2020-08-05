<template>
  <div>
    <button v-for="(value, index) in values" v-bind:key="index">{{ value }}</button>
  </div>
</template>

<script>
export default {
  props: ["values"],
};
</script>

<style></style>
