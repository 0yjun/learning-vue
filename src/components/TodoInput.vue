<template>
  <div class="inputBox shadow">
    <input type="text" v-model="newTodoItem" v-on:keyup.enter="addTodo">
    <span class="addContainer" v-on:click="addTodo">
      <i class="fa-solid fa-plus addBtn"></i>
    </span>
    <Modal v-if="showModal" @close="showModal = false">
     <h3 slot="header">경고</h3>
     <h3 slot="body">입력하시오</h3>
     <h3 slot="footer">닫기</h3>
    </Modal>
  </div>
</template>

<script>

import Modal from './common/Modal.vue'
export default {
  data :function(){
    return {newTodoItem : '',showModal : false}
  },
  methods:{
    addTodo : function(){
      if(this.newTodoItem !==''){
        this.$emit('addTodoItem',this.newTodoItem);
        this.clearInput();
      }else{
        console.log('thisshowmodal',this.showModal)
        this.showModal = !this.showModal;
      }
     
    },
    clearInput : function(){
      this.newTodoItem = '';
    },
    
  },components : {Modal : Modal}


}
</script>

<style scoped>
  input:focus {
    outline: none;
  }
  .inputBox{
   
    height: 50px;
    line-height:50px;
    border-radius:5px;
  }
  .inputBox input{
   border-style: none;
   font-size: 0.9rem;
  }
  .addContainer{
    float: right;
    background: linear-gradient(to right, #6478FB,#8763FB);
    display: black;
    width: 3rem;
    border-radius:0 5px 5px 0;
    border : 1px solid gray;
  }
  .addBtn{
    color: white;
    vertical-align: middle;
  }

</style>
  