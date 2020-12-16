<template>
  <div style="padding: 30px">
    <el-alert :closable="false" title="menu 1-2" type="success">
      <keep-alive :include="cachedViews">
        <router-view />
      </keep-alive>
    </el-alert>
  </div>
</template>
<script>
export default {
  name: 'Blank',
  computed: {
    cachedViews() {
      return this.$store.state.tagsView.cachedViews
    }
  }
}
</script>
