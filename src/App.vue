<template>
  <div id="app">
    <h1 style="text-align: center;">
      TEST
    </h1>
    <todoList :todolist="todolist"></todoList>
    <todoButton @changeActive="changeActive"></todoButton>
  </div>

</template>

<script>
import todoList from './components/todoList.vue'
import todoButton from './components/todoButton.vue'
export default {
  name: "App",
  data(){
    return {
      todolist:[
        {id:1,task:'吃饭',isCompleted:true},
        {id:1,task:'睡觉',isCompleted:false},
        {id:1,task:'打豆豆',isCompleted:true},
      ],
      active:0,
    };
  },
  components: {
    todoList,
    todoButton
  },
  computed:{
    todolist(){
      if(this.active===0){
        return this.todolist
      }
      else if(this.active===1){
        return this.todolist.filter(item => item.isCompleted)
      }
      else{
        return this.todolist.filter(item => !item.isCompleted)
      }
    }
  },
  methods:{
    changeActive(active){
      this.active = active
      console.log(active)
    }
  }
}
</script>

<style>
#app{
  width: 50%;
  margin: 0 auto;
}
</style>
