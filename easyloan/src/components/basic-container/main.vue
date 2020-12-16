<template>
  <div :class="{'basic-container--block':block}" class="basic-container">
    <el-card>
      <slot />
    </el-card>
  </div>
</template>

<script>
export default {
  name: 'BasicContainer',
  props: {
    block: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style lang="scss">
.basic-container {
  // padding: 8px 10px;
  /*border-radius: 10px;*/

  box-sizing: border-box;
  .el-card {
    width: 100%;
    box-shadow: none;
    border: 1px solid #D9D9D9 ;
  }
  &:first-child {
    padding-top: 0;
  }
  &--block {
    height: 100%;
    .el-card {
      height: 100%;
    }
  }
}
</style>
