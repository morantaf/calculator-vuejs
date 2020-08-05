<template>
  <div>
    <button value="0" v-on:click="onClick($event)">0</button>
    <button value="1" v-on:click="onClick($event)">1</button>
    <button value="2" v-on:click="onClick($event)">2</button>
    <button value="3" v-on:click="onClick($event)">3</button>
    <button value="4" v-on:click="onClick($event)">4</button>
    <button value="5" v-on:click="onClick($event)">5</button>
    <button value="6" v-on:click="onClick($event)">6</button>
    <button value="7" v-on:click="onClick($event)">7</button>
    <button value="8" v-on:click="onClick($event)">8</button>
    <button value="9" v-on:click="onClick($event)">9</button>
    <button value="." v-on:click="onClick($event)">.</button>
  </div>
</template>

<script>
export default {
  methods: {
    onClick(e) {
      this.$emit("type-key", e.target.value);
    },
  },
};
</script>

<style></style>
