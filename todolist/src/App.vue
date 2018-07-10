<template>
  <div class="container">
    <Header :todolist="todolist"/>
    <Body :todolist="todolist" :deleteTodoItem="deleteTodoItem"/>
    <Footer :todolist="todolist" :selectAllTodo="selectAllTodo"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Body from './components/Body.vue'
import Footer from './components/Footer.vue'
export default {
  data () {
    return {
      todolist: JSON.parse(window.localStorage.getItem('todolist') || '[]')
    }
  },
  methods: {
    selectAllTodo (check) {
      this.todolist.forEach((item, index) => { item.status = check })
    },
    deleteTodoItem (index) {
      this.todolist.splice(index, 1)
    }
  },
  watch: {// 实现深度监听，不仅能监听原始类型数据的改变，也能监听对象内部的改变
    todolist: function (present, old) {
      window.localStorage.setItem('todolist', JSON.stringify(present))
    }
  },
  components: {Header, Body, Footer}
}
</script>

<style>
*{
  margin: 0px;
  padding: 0px;
}
</style>
