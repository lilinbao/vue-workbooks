<template>
<!--
  思考一下这两对事件有何不同之处
  onmouseenter
  onmouseleave
  onmouseover
  onmouseout
-->
  <li class="item" @mouseenter="updateui(true)" @mouseleave="updateui(false)" :style="{background: bgColor}">
    <input type="checkbox" v-model="item.status" :id="'n'+index">
    <label>{{item.title}}</label>
    <button class="del" v-show="showDelBtn" @click="delItem">删除</button>
  </li>
</template>

<script>
export default {
  props: {
    item: Object,
    index: Number,
    deleteTodoItem: Function
  },
  data () {
    return {
      bgColor: 'white',
      showDelBtn: false
    }
  },
  methods: {
    updateui (active) {
      if (active) {
        this.bgColor = '#aaa'
        this.showDelBtn = true
      } else {
        this.bgColor = 'white'
        this.showDelBtn = false
      }
    },
    delItem () {
      const {index, deleteTodoItem} = this
      deleteTodoItem(index)
    }
  }
}
</script>

<style>
.item{
  position: relative;
  height: 35px;
  line-height: 35px;
  margin: 0px 10px;
}
.del{
  position: absolute;
  width: 50px;
  top: 4px;
  bottom: 4px;
  right: 30px;
  border: 1px solid #aaa;
  color: white;
  border-radius: 5px;
  background-color: red;
}
</style>
