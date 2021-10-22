<template>
  <div class="hello">
    <!-- <h1>{{ msg }}</h1> -->
    <input type="number" v-model.number="operand1">
    <input type="number" v-model.number="operand2">
    = {{result}}
    <br>
    <br>
    <button @click="plus(operand1, operand2)">+</button>
    <button @click="minus(operand1, operand2)">-</button>
    <button @click="multiply(operand1, operand2)">*</button>
    <button @click="divide(operand1, operand2)">/</button>
    <button @click="degree(operand1, operand2)"
   >x&#8319;</button>
    <br>
    <div v-show="res0">На 0 делить нельзя!</div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      result: 0,
      operand1: 0,
      operand2: 0,
      res0: false
    }
  },
  methods: {
    plus (operand1, operand2) {
      this.result = operand1 + operand2
    },
    minus (operand1, operand2) {
      this.result = operand1 - operand2
    },
    multiply (operand1, operand2) {
      this.result = operand1 * operand2
    },
    divide (operand1, operand2) {
      if (operand2 !== 0) {
        this.result = Math.floor(operand1 / operand2)
        this.res0 = false
      } else this.res0 = true
    },
    degree (operand1, operand2) {
      this.result = Math.pow(operand1, operand2)
    }
  }
  //   // props: {
  //   //   // msg: String,
  //   // },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
// h3 {
//   margin: 40px 0 0;
// }
// ul {
//   list-style-type: none;
//   padding: 0;
// }
// li {
//   display: inline-block;
//   margin: 0 10px;
// }
// a {
//   color: #42b983;
// }
</style>
