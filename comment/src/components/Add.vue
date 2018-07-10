<template>
  <div class="add col-xs-4">
    <form action="" class="form-horizontal">
      <div class="form-control">
        <label for="name">你的名字</label>
        <input type="text" name="name" v-model="name" />
      </div>
      <div class="form-control">
        <label for="content">你的评论</label>
        <textarea type="textarea" rows="3" name="content" v-model="content" ></textarea>
      </div>
      <button class="submit" @click.prevent="add">提交</button>
    </form>
  </div>
</template>

<script>
export default {
  props: {
    addComment: {
      type: Function,
      required: true
    }
  },
  data () {
    return {
      name: '',
      content: ''
    }
  },
  methods: {
    add (e) {
      const name = this.name
      const content = this.content
      if (!name || !content) {
        alert('姓名或评论内容不合法')
        return false
      }
      this.comment = {
        name,
        comment: content
      }
      this.addComment(this.comment)
      return false
    }
  }
}
</script>

<style>

</style>
