<template>
  <div id="app">
    <Display v-bind:displayedValue="displayedValue" />
    <Keys v-on:type-key="handleTypedKey" />
  </div>
</template>

<script>
import Keys from "./components/Keys.vue";
import Display from "./components/Display.vue";

export default {
  name: "App",
  data() {
    return {
      displayedValue: "",
      sign: "",
      savedValue: 0,
    };
  },
  methods: {
    handleTypedKey(value) {
      switch (value) {
        case "1":
        case "2":
        case "3":
        case "4":
        case "5":
        case "6":
        case "7":
        case "8":
        case "9":
        case "0":
        case ".":
          this.displayedValue = `${this.displayedValue}${value}`;
          break;
        case "+":
        case "-":
        case "/":
          this.sign = value;
          this.savedValue = parseFloat(this.displayedValue);
          this.displayedValue = "";
          console.log(this.savedValue);
          console.log(this.sign);
          break;
        case "x":
          this.sign = "*";
          this.savedValue = parseFloat(this.displayedValue);
          this.displayedValue = "";
          console.log(this.savedValue);
          console.log(this.sign);
          break;
        case "=":
          this.displayedValue = "";
          break;
        default:
          console.log("blabla");
      }
    },
  },
  components: {
    Keys,
    Display,
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
