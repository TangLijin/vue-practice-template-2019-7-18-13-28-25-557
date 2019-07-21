<template>
  
  <div id="app">
    <!-- 请输入数字： -->
  <!--
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
      <p> {{count}}</p>
      <button v-on:click ="add">点我+</button>
      <button v-on:click ="decrease">点我-</button> 
  
  </div>
</template>

<script>
// import { METHODS } from 'http';
// import func from '../vue-temp/vue-editor-bridge';
//import HelloWorld from './components/HelloWorld.vue'

/*
export default {
  name: 'app',
  components: {
    HelloWorld
  }
} */


export default {
  name: 'CounterGroup',
  props:["index"],
  data: function(){
      return {
        // count: Math.round(Math.random()*10)
        count:0
      } 
  },

  methods: {
    add:function() {
      this.count++;
      this.$emit("add",this.count,this.index);
    },
    decrease:function(){
      this.count--;
      this.$emit("decrease",this.count,this.index);
    }
  }
};

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
</style>
