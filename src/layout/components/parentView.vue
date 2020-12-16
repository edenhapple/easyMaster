<template>
  <keep-alive :include="cacheList" :exclude="notCacheName">
    <router-view ref="child" />
  </keep-alive>
</template>
<script>
export default {
  name: 'ParentView',
  computed: {
    key() {
      return this.$route.path
    },
    notCacheName() {
      return [(this.$route.meta && this.$route.meta.noCache) ? this.$route.name : '']
    },
    cacheList() {
      return ['ParentView', ...this.$store.state.tagsView.cachedViews]
    }
  }
}
</script>
