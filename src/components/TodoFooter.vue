<template>
  <div class="clearAllContainer">
    <span class="clearAllBtn" v-on:click="clearTodo">
      clear all
    </span>
  </div>
</template>

<script>
export default {
  methods : {
    clearTodo : function(){
      localStorage.clear();
    }
  }
}
</script>

<style scoped>
  .clearAllContainer {
    width: 8.5rem;
    height : 50px;
    line-height: 50px;
    background-color: white;
    border-radius: 5px;
  }
  .clearAllBtn{
    display : block;
    color : #E20303;
  }
</style>
  