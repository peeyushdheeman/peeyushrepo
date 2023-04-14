<template>
  <div class="calculator">
    <div class="display" :v-model="modulus">{{ current }}</div>

    <div class="btn" v-on:click="clear()">C</div>
    <div class="btn" v-on:click="preoperators()">+/-</div>
    <div class="btn" v-on:click="buttons8()">÷</div>
    <div class="btn" v-on:click="buttons()">%</div>
    <div class="btn" v-on:click="buttons(7)">7</div>
    <div class="btn" v-on:click="buttons(8)">8</div>
    <div class="btn" v-on:click="buttons(9)">9</div>
    <div class="btn" v-on:click="buttons('*')">x</div>
    <div class="btn" v-on:click="buttons('4')">4</div>
    <div class="btn" v-on:click="buttons('5')">5</div>
    <div class="btn" v-on:click="buttons('6')">6</div>
    <div class="btn" v-on:click="buttons('-')">-</div>
    <div class="btn" v-on:click="buttons(1)">1</div>
    <div class="btn" v-on:click="buttons(2)">2</div>
    <div class="btn" v-on:click="buttons(3)">3</div>
    <div class="btn" v-on:click="buttons('+')">+</div>
    <div class="btn zero" v-on:click="buttons(0)">0</div>
    <div class="btn">.</div>
    <div class="btn" v-on:click="equals()">=</div>
  </div>
</template>

<script>
export default {
  name: "CalcuLator",

  data() {
    return {
      // operator: "",
      // previous: "",
      current: null,
      // operatorClicked: false,
      // moduluus: "%",
    };
  },
  methods: {
    // setPrevious() {
    //   this.previous = this.current;
    //   this.operatorClicked = true;
    // },
    clear() {
      this.current = "";
      this.previous = "";
    },
    preoperators() {
      this.current =
        this.current.charAt(0) === "-"
          ? this.current.slice(1)
          : `-${this.current}`;
    },
    // divide() {
    //   // this.divide = "/";
    //   // this.current = this.current + this.divide;
    //   // this.operator = (a, b) => a / b;
    //   // this.setPrevious();
    //   // pattern.test(text);
    //   // ? this.current.slice()
    //   // : `/${this.current}`;
    // },
    // modulus() {
    //   this.modulus = this.current + "%";
    //   this.current = this.current / 100;
    // },
    buttons(event) {
      if (this.operatorClicked) {
        // this.current = "";
        this.operatorClicked = false;
      }
      this.current = this.current + event;
      // console.log(event);
      // if (event == "=") {
      //   this.current == eval(this.current);
      //   console.log("hdkj");
      // }
    },
    // Add() {
    //   this.current = this.current + "+";
    //   this.operator = (a, b) => a + b;
    //   this.setPrevious();
    // },
    // Minus() {
    //   this.current = this.current + "-";
    //   this.operator = (a, b) => a - b;
    //   this.setPrevious();
    // },
    // Product() {
    //   this.current = this.current + "*";
    //   this.operator = (a, b) => a * b;
    //   this.setPrevious();
    // },
    equals() {
      this.current = eval(this.current);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.calculator {
  margin: auto;
  width: 500px;
  font-size: 40px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: minimax(50px, auto);
}
.display {
  grid-column: 1/5;
  height: 100px;
  background-color: #13000096;
}
.btn {
  background-color: #cbc7c7;
  border: 1px solid;
}
.zero {
  grid-column: 1/3;
}
</style>
