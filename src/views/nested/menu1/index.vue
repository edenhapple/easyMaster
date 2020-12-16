<template>
  <keep-alive>
    <div style="padding:30px;">
      <el-alert :closable="false" title="menu 1">
        <router-view />
      </el-alert>
    </div>
  </keep-alive>
</template>

<script>
export default {
  name: 'Blank'
}
</script>
