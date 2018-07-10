<template>
  <div class="col-xs-8">
    <p v-show="comments.length ===0 ">没有评论</p>
    <ul>
      <li class="item" v-for="(comment, index) in comments" :key="index">
        <Item :item="comment" :removeItem="removeItem" :index="index"/>
      </li>
    </ul>
  </div>
</template>

<script>
import Item from './Item.vue'
export default {
  props: {
    comments: Array,
    removeItem: Function
  },
  components: {Item},
  template: '<Item/>'
}
</script>

<style>

</style>
