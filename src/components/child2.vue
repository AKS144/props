<template>
    <div>            
       <button v-on:click="updateTitle1()">Update</button> 
       <button v-on:click="increment()">Increment</button> 

    </div>
</template>

<script>
export default {
   name: 'child2',
   methods:{
       updateTitle1(){
           //console.warn("hello from title")//check for data from title
           this.$emit('changeTitle',"Title")//pass data to parent
       },

       increment()
       {
           this.$emit('increment',2);//2 is data
       }

   }   
};
</script>