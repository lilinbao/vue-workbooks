<template>
  <div class="body container">
    <ul v-for="(item, index) in todolist" :key="index">
       <todo-item :item="item" :index="index" :deleteTodoItem="deleteTodoItem"/>
    </ul>
  </div>
</template>

<script>
import TodoItem from './TodoItem.vue'
export default {
  data () {
    return {}
  },
  props: {
    todolist: {
      type: Array,
      required: true
    },
    deleteTodoItem: Function
  },
  components: { TodoItem }
}
</script>

<style>
.container{
  width: 90%;
  margin: 0px auto;
}
ul{
  list-style: none;
}
</style>
