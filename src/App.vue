<template>
  <div id="app">
    <h1>
      TEST
    </h1>
    <todoList :todolist="todolist"></todoList>

  </div>

</template>

<script>
import todoList from './components/todoList.vue'
export default {
  name: "App",
  data(){
    return {
      todolist:[
        {id:1,task:'吃饭',isCompleted:true},
        {id:1,task:'睡觉',isCompleted:false},
        {id:1,task:'打豆豆',isCompleted:true},
      ],
    };
  },
  components: {
    todoList
  }
}
</script>

<style>

</style>
