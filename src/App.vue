<template>
  <div class="app">
    <!-- 全局导航栏组件 -->
    <Header />
    
    <!-- 路由出口：这里会根据URL自动切换显示不同的页面 -->
    <!-- 访问 / 时显示 Home.vue，访问 /about 时显示 About.vue -->
    <router-view />
    
    <!-- 全局页脚（如果不需要可以先不加） -->
    <!-- <Footer /> -->
  </div>
</template>

<script setup>
// 导入导航栏组件（你需要先创建这个文件）
import Header from '@/components/Header.vue'
// 导入页脚组件（可选，需要时再创建）
// import Footer from '@/components/Footer.vue'
</script>

<style>
/* 全局样式 - 影响整个应用 */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Arial, sans-serif;
  line-height: 1.6;
  background-color: #f5f5f5;
}

.app {
  min-height: 100vh; /* 确保至少占满整个视口高度 */
  display: flex;
  flex-direction: column;
}

/* 路由切换时的动画效果（可选） */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>