<template>
  <ul class="nav-list">
    <li v-for="(nav,index) of navList" :key="index">
      <div class="menu">{{nav.name}}</div>
      <template v-if="nav.children && nav.children.length>0">
        <div class="menu-list" v-for="(item,index) of nav.children " :key="index">
          <a @click="toPath(nav,item)" >{{item.name}}</a>
        </div>
      </template>
    </li>
  </ul>
</template>

<script lang="ts">
import {Vue} from 'vue-class-component'
export default class VNav extends  Vue{
    private navList = [
      {
        name:'简介',
        path:'/index'
      },
      {
        name:'快速上手',
        path:'/novice',
        children:[
          {
            name:'项目搭建',
            path:'createApp'
          }
        ]
      },
      {
        name:'基础知识',
        path:'/'
      },

    ]
}
</script>

<style scoped lang="less">
  @import "pNav";
</style>