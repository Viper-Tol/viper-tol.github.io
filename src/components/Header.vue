<template>
  <div class="headbox">
    <div class="buttonBox">
      <!-- 将 button 替换为 router-link -->
      <router-link
        v-for="tab in tabs"
        :key="tab.id"
        :to="tab.path"
        :class="{ active: $route.path === tab.path }"
        class="nav-button" 
      >
        {{ tab.name }}
      </router-link>
    </div>
  </div>
</template>
<script setup>
import { useRoute } from 'vue-router'

const route = useRoute()

const tabs = [
  { id: 'home', name: '首页', path: '/' },
  { id: 'about', name: '关于我们', path: '/about' },
  { id: 'products', name: '服务内容', path: '/products' },
  { id: 'news', name: '资料下载', path: '/news' }
]
</script>
<style scoped>
/* 容器样式保持不变 */
.headbox {
  background-color: black;
  padding: 10px 0;
}
.buttonBox {
  display: flex;
  gap: 0;
  background-color: black;
  margin: 0;
  padding-left: 20px;
  max-width: none;
}

/* 核心改造：将 button 选择器替换为 .nav-button */
.nav-button {
  padding: 12px 24px;
  background-color: black;
  color: white;
  border: none;
  cursor: pointer;
  font-size: 16px;
  font-weight: 500;
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
  border-radius: 0;
  min-width: 100px;
  /* 针对 router-link（渲染为<a>）的额外重置 */
  text-decoration: none; /* 去除下划线 */
  display: inline-block; /* 保证布局与button一致 */
  text-align: center;
  box-sizing: border-box; /* 确保边框计算一致 */
}

/* 默认状态：对应原来的 button:not(.active) */
.nav-button:not(.active) {
  background-color: black;
  color: white;
  border: 1px solid transparent;
}

/* 鼠标悬停效果 - 对应原来的 button:not(.active):hover */
.nav-button:not(.active):hover {
  background: linear-gradient(135deg, #444 0%, #222 50%, #444 100%);
  background-size: 200% 200%;
  animation: gradientShift 2s ease infinite;
  color: white;
  border: 1px solid #666;
}

/* 选中状态 - 对应原来的 button.active */
.nav-button.active {
  background-color: white;
  color: black;
  font-weight: bold;
  border: 1px solid white;
}

/* 选中状态下的悬停效果 */
.nav-button.active:hover {
  background-color: #f0f0f0;
  color: black;
}

/* 底部指示条 - 对应原来的 button.active::after */
.nav-button.active::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 80%;
  height: 3px;
  background-color: #42b983;
}

/* 渐变动画（保持不变） */
@keyframes gradientShift {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}

/* 交互反馈 */
.nav-button:active {
  transform: translateY(1px);
}
</style>