<template>
  <div style="padding:30px;">
    <el-alert :closable="false" title="menu 1-2-1" type="warning" />
    <el-input v-model="input" placeholder="请输入内容" />
  </div>
</template>

<script>
export default {
  name: 'Menu1210999',
  data() {
    return {
      input: ''
    }
  },
  watch: {
    '$route'(val) {
      console.log(val)
    }
  },
  created() {
    console.log(this.$options.name)
  }
}
</script>
