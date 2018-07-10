<template>
  <div class="header">
    <h1>任务列表实战</h1>
    <input class="task" v-model="task" type="text" @keyup.enter="add" placeholder="Hit Enter to Add New Task"/>
  </div>
</template>

<script>

export default {
  data () {
    return {
      task: ''
    }
  },
  props: {
    todolist: {
      type: Array,
      required: true
    }
  },
  methods: {
    add () {
      let obj = {
        title: this.task,
        status: false
      }
      this.todolist.unshift(obj)
      this.task = ''
    }
  }
}
</script>

<style>
.header {
  text-align: center;
}
.header > input {
  border: 1px solid #aaa;
  border-radius: 5px;
  width: 90%;
  height: 60px;
  margin: 10px 0px;
  font-size: 28px;
}
</style>
