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
      savedValue: null,
      operator: null,
      operatorClicked: false,
      end: false,
    };
  },
  methods: {
    clearAll() {
      this.displayedValue = "";
    },
    assignNegativeOrPositive() {
      if (this.displayedValue !== "")
        this.displayedValue =
          this.displayedValue.charAt(0) === "-"
            ? this.displayedValue.slice(1)
            : `-${this.displayedValue}`;
    },
    percent() {
      this.displayedValue = `${parseFloat(this.displayedValue) / 100}`;
    },
    append(number) {
      if (number === "0" && this.displayedValue === "")
        this.displayedValue = "";
      else {
        if (this.operatorClicked) {
          this.displayedValue = "";
          this.operatorClicked = false;
        }
        this.displayedValue = `${this.displayedValue}${number}`;
      }
    },
    saveValue() {
      this.savedValue = this.displayedValue;
      this.operatorClicked = true;
    },
    divide() {
      this.operator = (a, b) => a / b;
      this.saveValue();
      this.sign = "÷";
    },
    times() {
      this.operator = (a, b) => a * b;
      this.saveValue();
      this.sign = "x";
    },
    minus() {
      this.operator = (a, b) => a - b;
      this.saveValue();
      this.sign = "-";
    },
    add() {
      this.operator = (a, b) => a + b;
      this.saveValue();
      this.sign = "+";
    },
    equal() {
      this.displayedValue = this.operator(
        parseFloat(this.savedValue),
        parseFloat(this.displayedValue)
      );
      this.savedValue = null;
      this.sign = "";
      this.end = true;
    },
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
          this.append(parseInt(value));
          break;
        case ".":
          if (this.displayedValue.indexOf(".") === -1) this.append(".");
          break;
        case "+":
          this.add();
          break;
        case "-":
          this.minus();
          break;
        case "/":
          this.divide();
          break;
        case "x":
          this.times();
          break;
        case "=":
          this.equal();
          break;
        case "+/-":
          this.assignNegativeOrPositive();
          break;
        case "C":
          this.clearAll();
          break;
        case "%":
          this.percent();
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
  width: 33%;
  margin: auto;
}
</style>
