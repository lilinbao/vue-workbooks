<template>
  <div class="app">
    <header>
    <div class="head">
      <div class="brand">
        <h1>BB怎么好</h1>
        <img src="" alt="">
      </div>
    </div>
  </header>
  <div class="container">
    <div class="row">
      <Add :addComment="addComment"/>
      <List :comments="comments" :removeItem="removeItem"/>
    </div>
  </div>
  </div>
</template>

<script>
import List from './components/List.vue'
import Add from './components/Add.vue'
export default {
  data () {
    return {
      comments: [
        {
          name: 'Bob',
          comment: 'Vue is very nice!'
        },
        {
          name: 'Cat',
          comment: 'Vue is very Easy!'
        },
        {
          name: 'Jack',
          comment: 'Vue is very lite!'
        }

      ]
    }
  },
  methods: {
    addComment (comment) {
      this.comments.unshift(comment)
    },
    removeItem (index) {
      this.comments.splice(index, 1)
    }
  },
  components: {
    List,
    Add
  }
}
</script>

<style>

</style>
