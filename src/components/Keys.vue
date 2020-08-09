<template>
  <div class="keys">
    <button class="btn operator" value="C" v-on:click="onClick($event)">C</button>
    <button class="btn operator" value="+/-" v-on:click="onClick($event)">+/-</button>
    <button class="btn operator" value="%" v-on:click="onClick($event)">%</button>
    <button class="btn operator" value="/" v-on:click="onClick($event)">/</button>
    <button class="btn" value="1" v-on:click="onClick($event)">1</button>
    <button class="btn" value="2" v-on:click="onClick($event)">2</button>
    <button class="btn" value="3" v-on:click="onClick($event)">3</button>
    <button class="btn operator" value="x" v-on:click="onClick($event)">x</button>
    <button class="btn" value="4" v-on:click="onClick($event)">4</button>
    <button class="btn" value="5" v-on:click="onClick($event)">5</button>
    <button class="btn" value="6" v-on:click="onClick($event)">6</button>
    <button class="btn operator" value="-" v-on:click="onClick($event)">-</button>
    <button class="btn" value="7" v-on:click="onClick($event)">7</button>
    <button class="btn" value="8" v-on:click="onClick($event)">8</button>
    <button class="btn" value="9" v-on:click="onClick($event)">9</button>
    <button class="btn operator" value="+" v-on:click="onClick($event)">+</button>
    <button class="btn" value="0" v-on:click="onClick($event)">0</button>
    <button class="btn" value="." v-on:click="onClick($event)">.</button>
    <button class="btn">&nbsp;</button>
    <button class="btn operator" value="=" v-on:click="onClick($event)">=</button>
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

<style>
.keys {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: minmax(50px, auto);
  height: 100%;
  background-color: #333;
}

.btn {
  background-color: #f2f2f2;
  border: 1px solid rgb(110, 110, 110);
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 50%;
  place-self: center;
  height: 55px;
  width: 55px;
  font-size: x-large;
}

.operator {
  background-color: #ff9501;
  color: white;
}

.btn:hover {
  background-color: rgb(33.8%, 86.6%, 50.5%);
  cursor: pointer;
}
</style>
