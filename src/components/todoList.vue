<template>
  <ul class="list-group">
    <li 
      class="list-group-item d-flex justify-content-between align-items-center"
      v-for="item in todolist" :key="item.id"
    >
      <div class="form-group form-check">
        <input 
          type="checkbox" 
          class="form-check-input" 
          value=""
          :id="item.id"
          v-model="item.isCompleted"
        >
        <label class="form-check-label" :for="item.id" :class="item.isCompleted ? 'delete':''">
          {{item.task}}
        </label>
      </div>
      <span class="badge badge-primary badge-pill" v-if="item.isCompleted">已完成</span>
      <span class="badge badge-warning badge-pill" v-else>未完成</span>
    </li>



  </ul>
</template>

<script>
export default {
  name:'todoList',
  props:{
    todolist:{ 
      type:Array,
      required:true,
      default:[]
    }
  },
}
</script>

<style>
.list-group{
  /* width: 30%;
  margin: 0 auto; */
}
.delete{
  text-decoration: line-through;
}
</style>
