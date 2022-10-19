<template>
  <div>
    <ul>
      <li v-for="(todoItem,index) in propsdata" v-bind:key="todoItem.item" class="shadow">
        <span v-on:click="toggleComplete(todoItem,index)">
          <i class="checkBtn fa-solid fa-check " v-bind:class="{checkBtnCompleted:todoItem.complement}" ></i>
        </span>
        <span v-bind:class="{textCompleted:todoItem.complement}">{{todoItem.item}}</span>
        <span class="removeBtn" v-on:click="removeTodo(todoItem,index)">
          <i class="fa-solid fa-ban" ></i>
        </span>
      </li>
    </ul>
  </div>
</template>

<script>
export default { 
  props : ['propsdata'],
  methods : {
    removeTodo : function(todoItem,index){
      this.$emit('removeItem',todoItem,index);
    },
    toggleComplete : function(todoItem,index){
      this.$emit('toggleItem',todoItem,index);
    }
  },
}
</script>

<style>
ul {
  list-style-type: none;
  padding-left: 0px;
  margin-top : 0px;
  text-align: center;
}
li{
  display:   flex;
  min-height : 50px;
  height:50px;
  line-height:50px;
  margin : 0.4rem 0;
  padding : 0 0.0rem;
  background: white;
  border-radius : 5px;
}
.removeBtn{
  margin-left:auto;
  color: #DE4343;
}
.checkBtn{
  line-height: 45px;
  color: #62acde;
  margin-right: 5px;
}
.checkBtnCompleted{
  color:#b3adad;
}
.textCompleted{
  text-decoration: line-through;
  color:#b3adad;
}
</style>
  