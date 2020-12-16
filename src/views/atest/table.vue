<template>
  <div class="app-container">
    <el-button type="primary" size="default" @click="tapBtn">点击</el-button>
    <p v-if="isShow"> {{ text }}</p>
    <el-table :data="list" border stripe>
      <el-table-column
        v-for="(col, index) in columns"
        :key="index"
        :prop="col.id"
        :label="col.label"
        :width="col.width"
      />
    </el-table>
  </div>
</template>

<script>
import request from '@/utils/request'
// import TableColumn from '@/views/atest/test'
export default {
  name: 'TestTable',
  // components: { cccc: TableColumn },
  data() {
    return {
      aaa: '',
      isShow: false,
      list: [],
      text: '111',
      query: {
        page: 1,
        limit: 10
      },
      columns: [
        {
          id: 'author',
          label: '33333',
          width: '180'
        },
        {
          id: 'reviewer',
          label: '5555',
          width: '280'
        }
      ]
    }
  },
  watch: {
    text() {},
    deep: true,
    immediate: true
  },
  beforeCreate() {
    console.log('beforeCreate 创建前状态 ------------>')
    console.log('%c%s', 'color:red', 'el     : ' + this.$el) // undefined
    console.log('%c%s', 'color:red', 'data   : ' + this.$data) // undefined
    console.log('%c%s', 'color:red', 'message: ' + this.message)
  },
  created() {
    this.getList(this.query)
    console.log('created 创建完毕状态 ------------>')
    console.log('%c%s', 'color:red', 'el     : ' + this.$el) // undefined
    console.log('%c%s', 'color:red', 'data   : ' + this.$data) // 已被初始化
    console.log('%c%s', 'color:red', 'message: ' + this.message) // 已被初始化
  },
  beforeMount() {
    console.log('beforeMount 挂载前状态 ------------>')
    console.log('%c%s', 'color:red', 'el     : ' + (this.$el)) // 已被初始化
    console.log('%c%s', 'color:red', 'data   : ' + this.$data) // 已被初始化
    console.log('%c%s', 'color:red', 'message: ' + this.message) // 已被初始化
  },
  mounted() {
    console.log('mounted 挂载结束状态 ------------>')
    console.log('%c%s', 'color:red', 'el     : ' + this.$el) // 已被初始化
    // console.log(this.$el)
    console.log('%c%s', 'color:red', 'data   : ' + this.$data) // 已被初始化
    console.log('%c%s', 'color:red', 'message: ' + this.message) // 已被初始化
  },
  beforeUpdate() {
    console.log('beforeUpdate 更新前状态 ------------>')
    console.log('%c%s', 'color:red', 'el     : ' + this.$el)
    // console.log(this.$el)
    // console.log('真实dom结构：' + document.getElementById('app').innerHTML)
    console.log('%c%s', 'color:red', 'data   : ' + this.$data)
    console.log('%c%s', 'color:red', 'message: ' + this.message)
  },
  updated() {
    console.log('updated 更新完成状态 ------------>')
    console.log('%c%s', 'color:red', 'el     : ' + this.$el)
    // console.log(this.$el)
    // console.log('真实dom结构：' + document.getElementById('app').innerHTML)
    console.log('%c%s', 'color:red', 'data   : ' + this.$data)
    console.log('%c%s', 'color:red', 'message: ' + this.message)
  },
  beforeDestroy() {
    console.log('beforeDestroy 销毁前状态 ------------>')
    console.log('%c%s', 'color:red', 'el     : ' + this.$el)
    // console.log(this.$el)
    console.log('%c%s', 'color:red', 'data   : ' + this.$data)
    console.log('%c%s', 'color:red', 'message: ' + this.message)
  },
  destroyed() {
    console.log('destroyed 销毁完成状态 ------------>')
    console.log('%c%s', 'color:red', 'el     : ' + this.$el)
    // console.log(this.$el)
    console.log('%c%s', 'color:red', 'data   : ' + this.$data)
    console.log('%c%s', 'color:red', 'message: ' + this.message)
  },
  methods: {
    async getList(query) {
      const { data } = await request({
        url: '/vue-element-admin/article/list',
        method: 'get',
        params: query
      })
      this.list = data.items
      const result = await this.getToken()
      console.log(result)
    },
    async getToken() {
      const { data } = await request({
        url: '/vue-element-admin/roles', // 假地址 自行替换
        method: 'get'
      })
      return data
    },
    tapBtn() {
      this.isShow = !this.isShow
    }
  }
}

</script>
<style lang='scss' scoped></style>
