<template>
  <li class="item">
    {{item.name}} 说 {{item.comment}} <a href="javascript:void" @click.prevent="delItem" > 删除</a>
  </li>
</template>
<script>
export default {
  props: {
    item: Object,
    index: Number,
    removeItem: Function
  },
  methods: {
    delItem () {
      const {item, removeItem, index} = this
      if (window.confirm(`确定要删除${item.name}吗？`)) {
        console.log('deleted')
        removeItem(index)
      }
    }
  }
}
</script>
<style>

</style>
