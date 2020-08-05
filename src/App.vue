<template>
  <div id="app">
    <Display />
    <Keys v-bind:values="values" v-bind:callback="doSomething" />
  </div>
</template>

<script>
import Keys from "./components/Keys.vue";
import Display from "./components/Display.vue";

export default {
  name: "App",
  data() {
    return {
      values: [
        0,
        1,
        2,
        3,
        4,
        5,
        6,
        7,
        8,
        9,
        "+",
        "-",
        "*",
        "/",
        ".",
        "C",
        "+/-",
      ],
    };
  },
  components: {
    Keys,
    Display,
  },
  methods: {
    doSomething() {
      console.log("button clicked");
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
