<template>
  <div id="app">
    <img src="./assets/image.png">
    <router-view/>
      <section>
        <input placeholder="num1" type="number" class="num" v-model.number="num1"><div class="warning1">Enter number1</div>
        <select class="num" v-model="operate"> 
          <option value="+"> + </option>
          <option value="-"> - </option>
          <option value="*"> * </option>
          <option value="/"> / </option>
        </select>
        <input placeholder="num2" type="number" class="num" v-model.number="num2"><div class="warning2">Enter number2</div>
        <button class="cli" v-on:click="press">Result</button>
        <h2>Output:{{result}}</h2>
    </section>
  </div>
</template>

<script>
export default {
  name: 'App',
  data(){
    return{
      result:''
    }
  },

  methods: {
    // this is calculate part.
    press(){
      switch(this.operate) {
      case "+":
        return this.result = this.num1 + this.num2
      case "-":
        return this.result = this.num1 - this.num2
      case "*":
        return this.result = this.num1 * this.num2
      case "/":
        return this.result = this.num1 / this.num2
    }
    }
  },
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.num{
  position: relative;
  padding: 5px;
  border-radius: 4px;
}
.warning1{
  position: absolute;
  margin-left: 37%;
  display: none;
}
.warning2{
  position: absolute;
  margin-left: 50%;
  display: none;
}
.cli{
  padding: 5px;
  background:black;
  color: aliceblue;
  border-radius: 4px;
}
</style>
