<template>
  <div class="sq-app">
    <!-- 遍历底部四个路由 -->
    <router-link
      class="sq-app-li" 
      v-for="nav in navs"
      :key="nav.name"
      :to="{name:nav.name}"
      tag="li"
    >
    <span class="iconfont" v-html="nav.meta.icon"></span>
    {{nav.meta.title}}</router-link>
  </div>
</template>

<script>
import routes from '@/router/routes'

export default {
  data() {
    return {
      // 过滤掉首页重定向的数据，留下需要的（四个）模块
      navs: routes.filter(item =>  item.meta.isTabItem === true)
    }
  },
  created() {
  }
}
</script>

<style lang="scss" scoped>
  .sq-app {
    color: grey;
    height: 52px;
    width: 100%;
    display: flex;
    .router-link-exact-active,
    .router-link-active{
      color: red;
    }
    &-li{
      width: 25%;
      box-sizing: border-box;
      text-align: center;
      height: 100%;
      border-top: 1px solid #dedede;
      display: flex;
      flex-direction: column;
      padding-top:2px; 
      line-height: 25px;
      justify-content: center;
  }
  }
</style>
