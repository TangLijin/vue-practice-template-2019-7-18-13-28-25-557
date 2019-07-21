<template>
  
  <div id="app">
    
    请输入数字：

  
      <!-- <form>   -->
    <input v-model.number="counter_input" type="text" id="amount" > <br>
      <!-- </form> -->

    <!-- <div v-for="n in counter_input" v-bind:key="n" > -->
    <div v-for = "(item,index) in parseInt(counter_input)" v-bind:key="index">

      <!-- <p> {{count}}</p>
      <button v-on:click ="add">点我+</button>
      <button v-on:click ="decrease">点我-</button>  -->
      <counter-group v-bind:index="index" v-on:add="get_sum" v-on:decrease="get_sum"></counter-group>
    </div>

    <div><br>
    总数：<span> {{sum}}</span>
    </div>
    
  </div>
</template> 

<script>
// import { METHODS } from 'http';
import CounterGroup from './components/CounterGroup.vue';


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
        count_array:[],
        sum:0
      } 
  },
 components: {
    CounterGroup
  },
  

  methods: {

    get_sum:function(count,index){
      this.count_array[index] = count;
      this.sum = this.count_array.reduce((a,b) => a+b);
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
