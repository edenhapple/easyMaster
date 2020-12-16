<template>
  <el-table-column
    :prop="name"
    :label="lable"
    :width="width"
  />
</template>

<script>
export default {
  name: 'Test',
  props: {
    name: {
      type: String,
      default: ''
    },
    lable: {
      type: String,
      default: ''
    },
    width: {
      type: String,
      default: ''
    },
    ttt: {
      type: String,
      default: ''
    }
  },
  data() {
    return {
      a: this.width
    }
  },
  computed: {
    width1() {
      return this.a
    }
  },
  beforeCreate() {
    console.log('222222222 beforeCreate 创建前状态 ------------>')
    console.log('%c%s', 'color:red', 'el     : ' + this.$el) // undefined
    console.log('%c%s', 'color:red', 'data   : ' + this.$data) // undefined
    console.log('%c%s', 'color:red', 'message: ' + this.message)
  },
  created() {
    console.log('222222222 created 创建完毕状态 ------------>')
    console.log('%c%s', 'color:red', 'el     : ' + this.$el) // undefined
    console.log('%c%s', 'color:red', 'data   : ' + this.$data) // 已被初始化
    console.log('%c%s', 'color:red', 'message: ' + this.message) // 已被初始化
  },
  beforeMount() {
    console.log('2222222 beforeMount 挂载前状态 ------------>')
    console.log('%c%s', 'color:red', 'el     : ' + (this.$el)) // 已被初始化
    console.log('%c%s', 'color:red', 'data   : ' + this.$data) // 已被初始化
    console.log('%c%s', 'color:red', 'message: ' + this.message) // 已被初始化
  },
  mounted() {
    console.log('2222222 mounted 挂载结束状态 ------------>')
    console.log('%c%s', 'color:red', 'el     : ' + this.$el) // 已被初始化
    // console.log(this.$el)
    console.log('%c%s', 'color:red', 'data   : ' + this.$data) // 已被初始化
    console.log('%c%s', 'color:red', 'message: ' + this.message) // 已被初始化
  },
  beforeUpdate() {
    console.log('222222 beforeUpdate 更新前状态 ------------>')
    console.log('%c%s', 'color:red', 'el     : ' + this.$el)
    // console.log(this.$el)
    // console.log('真实dom结构：' + document.getElementById('app').innerHTML)
    console.log('%c%s', 'color:red', 'data   : ' + this.$data)
    console.log('%c%s', 'color:red', 'message: ' + this.message)
  },
  updated() {
    console.log('2222222 updated 更新完成状态 ------------>')
    console.log('%c%s', 'color:red', 'el     : ' + this.$el)
    // console.log(this.$el)
    // console.log('真实dom结构：' + document.getElementById('app').innerHTML)
    console.log('%c%s', 'color:red', 'data   : ' + this.$data)
    console.log('%c%s', 'color:red', 'message: ' + this.message)
  },
  beforeDestroy() {
    console.log('2222222 beforeDestroy 销毁前状态 ------------>')
    console.log('%c%s', 'color:red', 'el     : ' + this.$el)
    // console.log(this.$el)
    console.log('%c%s', 'color:red', 'data   : ' + this.$data)
    console.log('%c%s', 'color:red', 'message: ' + this.message)
  },
  destroyed() {
    console.log('22222222 destroyed 销毁完成状态 ------------>')
    console.log('%c%s', 'color:red', 'el     : ' + this.$el)
    // console.log(this.$el)
    console.log('%c%s', 'color:red', 'data   : ' + this.$data)
    console.log('%c%s', 'color:red', 'message: ' + this.message)
  }
}

</script>
<style lang='scss' scoped></style>
