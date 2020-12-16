<template>
  <keep-alive>
    <div style="padding:30px;">
      <el-alert :closable="false" title="menu 1-1" type="success">
        <el-input v-model="text" placeholder="" size="normal" clearable />
      </el-alert>
    </div>
  </keep-alive>

</template>

<script>
export default {
  name: 'Menu11234',
  data() {
    return {
      text: ''
    }
  }
}
</script>
