<template>
  <div>
    <div class="grid">
      <input  type="text" v-model="result" placeholder="0">
      <button @click="inputAdd(num)"  class="cell num" v-for="num in numbers">{{num}}</button>
      <button @click="inputAdd(op)"  class="cell op" v-for="op in operations">{{op}}</button>
      <button @click="reset"  class="cell op">R</button>
      <button @click="calck"  class="cell op">=</button>
    </div>
  </div>
</template>
<script>
export default {
  name: "App",
  data() {
    return {
      result: '',
      numbers: [0,1,2,3,4,5,6,7,8,9],
      operations: ['+','-','*','/']
    }
  },
  methods: {
    calck() {
      this.result = eval(this.result);
    },
    reset() {
      this.result = '';
    },
    inputAdd(a) {
      this.result = this.result.toString();
      this.result+=a;
    }
  }
}
</script>
<style>
  * {
  font-family: 'Gilroy',sans-serif;
  transition: 0.3s all;
    font-weight: 600;
}
#app {
  width: 200px;
  box-shadow: 0 3px 15px grey;
}
input[type="text"] {
  width: 200px;
  border: 0;
  color: #243849;
  font-size: 18px;
  padding: 5px 5px;
  text-align: right;
}
.grid {
  display: flex;                       
  flex-wrap: wrap;  
  justify-content: space-around;
  width: 100%;
  
}
.cell {
  flex: 33%;                       
  height: 50px;
  font-size: 18px;
  border: none;
}
.num {
  background-color: #243849;
  color: #fff;
  font-weight: 400;
}
.cell:hover{
  background-color: #182530;
}
.op {
  background-color: #ff9900;
  color: #243849;
}

</style>