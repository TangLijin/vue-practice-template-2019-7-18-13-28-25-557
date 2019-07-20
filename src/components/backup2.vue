<template>
  
  <div id="app">请输入数字：
  <!--
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  
      <!-- <form>  -->
    <input v-model.number="counter_input" type="text" id="amount" > <br>
      <!-- </form> -->

    <div v-for="n in counter_input" v-bind:key="n" v-pre:>

      <p> {{count[n]}}</p>
      <button v-on:click ="add(n)">点我+</button>
      <button v-on:click ="decrease(n)">点我-</button> 
      
    </div>

    <!-- <div><br>
    总数：<span> {{sum}}</span>

    </div>
     -->
  </div>
</template> 

<script>
// import { METHODS } from 'http';
// import func from '../vue-temp/vue-editor-bridge';
//import HelloWorld from './components/HelloWorld.vue'
//import CounterGroup from './components/CounterGroup.vue';
//import HelloWorld from './components/CounterSum.vue';

/*
export default {
  name: 'app',
  components: {
    HelloWorld
  }
} */

// let get_count = function(){
 
//     let l = [];
//     for(let j =0; j < counter_input; j++){
//       l[j] = Math.round(Math.random()*10);
//     }
//     return l;        
    
// }

export default {
  name: 'app',
  data: function(){
      return {
        counter_input:1,
        count:2
        
      } 
  },
 
  // components: {
  //   CounterGroup,
  //   CourterSum
  // },

  methods: {
    add:function(index) {
      this.count[index]++;
    },
    decrease:function(index){
      this.count[index]--;
    },
    get_sum:function(){

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
