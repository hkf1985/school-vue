<template>
  <header>{{title}}</header>
</template>

<script lang="ts">
import {Vue} from 'vue-class-component'
export default class VHeader extends Vue{
  private title = "第一次绑定数据"
}
</script>

<style scoped lang="less">
  @import "vHeader";
</style>