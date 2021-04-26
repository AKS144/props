<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <!--<HelloWorld msg="Welcome to Your Vue.js App"/>-->
    <!--<child name="Vue"/>//string only
    <child v-bind:name="userName"/> //string only props+data()parent to child in<child/>-->
   

   <!-- <child v-bind:usersc="usersp"/> props+data()parent to child in<child/>-->
   
   <h1>{{title}}</h1>
    <child2 v-on:changeTitle="updateTitle2($event)"/>
       <!-- <child2 @increment="incrementCount"></child2>-->

  </div> 
</template>

<script>
//import child from './components/child.vue'
import child2 from './components/child2.vue'

export default {
  name: 'App',
  components: {   
    //child,
    child2,
  }, 

/*
 //for child class
  data()
  { 
    //return {userName:"Abhishek"}//for single data and below is for array
    return {//for child.vue
        usersp:[
          {name:"Ravi", email:"ravi144k@gmail.com"},
           {name:"Sam", email:"ravi144k@gmail.com"},
            {name:"Bruce", email:"ravi144k@gmail.com"}
        ]}
    }
  };*/

  
  //for child2
  data(){
        return {title:"Props check", count:0}
  },
    methods:{
      updateTitle2(title)
      {
        this.title=title
      },
      incrementCount(data)
      {
        this.count += data;
      }      
    }
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
