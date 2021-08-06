<template>
  <div id="app">
    <router-view></router-view>
    <main-tab-bar></main-tab-bar>
    <!-- 3.使用组件 -->
  </div>
</template>

<script>
// 1.先导入组件
import MainTabBar from "./components/MainTabBar.vue";

export default {
  name: "App",
  components: {
    // 2.注册组件
    MainTabBar,
  },
};
</script>

<style>
@import "./assets/css/base.css";
</style>
