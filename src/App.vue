<script>
import TagsInput from './components/TagsInput.vue';
// required to use a component (register component locally)
export default{
  // components:{
    // TagsInput
  // }
  data:()=>({
    jsFrameworks:["react.js","vue.js", "angular"]
  }),
  mounted(){
    setTimeout(()=>{
      this.jsFrameworks.push("svelte.js")
    },3000)
  }
}
</script>

<template>
  <h1>Hello world</h1>
  <tags-input :selected-tags="jsFrameworks"/>
</template>

<style>
h1{
  color: blue;
}
</style>
