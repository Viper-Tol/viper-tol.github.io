<!-- src/components/common/Carousel.vue -->
<template>
  <div class="carousel">
    <div class="carousel-inner" :style="innerStyle">
      <img v-for="item in list"
       :key="item.id" 
       :src="item.src" 
       class="carousel-item" />
    </div>
    <button class="arrow left" @click="go(-1)">‹</button>
    <button class="arrow right" @click="go(1)">›</button>
    <div class="dots">
      <span
        v-for="(src,i) in list"
        :key="i"
        :class="{active:i===current}"
        @click="current=i"
      />
    </div>
  </div>
</template>

<script setup>
import { ref, computed, onMounted, onUnmounted } from 'vue'
const props = defineProps({
  //待重构，ts
  images: {
    type: Array,      // 必须传入数组
    required: true,   // 必须传！不能为空
    default: () => [] // 默认值（如果没传）
  },
  autoPlay: {
    type: Boolean,
    default: true
  }
})
const list=props.images
// const list = [
//   {id :1,src: '/img/farm1.jpg'},
//   {id :2,src: '/img/farm2.jpg'},
//   {id :3,src: '/img/farm3.jpg'},
//   {id :4,src: '/img/farm4.jpg'},
// ]
const current = ref(0)
const isPlaying = ref(false)
const duration = 3000
let timer = null

const innerStyle = computed(() => ({
  transform: `translateX(-${current.value * 100}%)`,
  transition: 'transform .5s ease'
}))

function go(step) {
  const len = list.length
  current.value = (current.value + step + len) % len
}

function startTimer() {
  stopTimer()
  timer = setInterval(() => go(1), duration)
  isPlaying.value = true
}
function stopTimer() {
  if (timer) {
    clearInterval(timer)
    timer = null
  }
  isPlaying.value = false
}

onMounted(() => startTimer())
onUnmounted(() => stopTimer())
</script>

<style scoped>
/* 将原 Home.vue 中 .carousel 及相关样式全部剪切过来 */
.carousel {
  position: relative;
  width: 100%;
  height: 400px;
  overflow: hidden;
}
.carousel-inner {
  display: flex;
  height: 100%;
}
.carousel-item {
  width: 100%;
  height: 100%;
  object-fit: cover;
  flex-shrink: 0;
  pointer-events: none;
}
.arrow {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background: rgba(0,0,0,.4);
  color: #fff;
  border: none;
  width: 40px;
  height: 40px;
  font-size: 24px;
  cursor: pointer;
  border-radius: 50%;
  transition: background .3s;
  z-index: 100;
}
.arrow:hover {
  background: rgba(0,0,0,.7);
}
.left {
  left: 15px;
}
.right {
  right: 15px;
}
.dots {
  position: absolute;
  bottom: 15px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  gap: 8px;
}
.dots span {
  width: 10px;
  height: 10px;
  border-radius: 50%;
  background: rgba(255,255,255,.6);
  cursor: pointer;
  transition: background .3s;
}
.dots span.active {
  background: #42b983;
}
</style>