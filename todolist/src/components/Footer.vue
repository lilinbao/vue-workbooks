<template>
  <div class="footer container">
    <input type="checkbox" v-model="isAllCheck">
    <label>{{completed}} of {{todolist.length}} are completed</label>
  </div>
</template>

<script>
export default {
  props: {
    todolist: {
      type: Array,
      required: true
    },
    selectAllTodo: Function
  },
  computed: {
    completed () {
      return this.todolist.reduce((total, item) => { return total + (item.status ? 1 : 0) }, 0)
    },
    isAllCheck: {
      get () {
        return this.todolist.length !== 0 && this.completed === this.todolist.length
      },
      set (value) { // value 是当前 checkbox最新的值
        this.selectAllTodo(value)
      }
    }
  }
}
</script>

<style>

</style>
