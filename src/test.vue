//轮播图
<template>
    <div class="flexbox">
        <div class="img-group">
        <img v-for="(src, i) in list" :key="i" :src="src" />
        </div>
        <div class="arrow-group">
            <button class="arrow arrow-left" @click="go(-1)">‹</button>
            <button class="arrow arrow-right" @click="go(1)">›</button>
        </div>
        </div>
    
</template>
<script setup>
import { ref } from 'vue'
const list=[
'/img/farm1.jpg',
  '/img/farm2.jpg',
  '/img/farm3.jpg',
  '/img/farm4.jpg'
]
const current=ref(0)
function go(step){
    current.value=(current.value+step+list.length)%list.length
}

//自动播放样式
const isPlaying=ref(false)//状态
let timerId=null//控制器
const INTERVAL =3000//间隔时间

function startAutoPlay(){
  //....
  stopAutoPlay()
  timerId=setInterval(()=>{
    go(1)
  },INTERVAL)
  isPlaying.value=true
}
function stopAutoPlay(){
  //...
  if(timerId){
    clearInterval(timerId)
    timerId=null
  }
  isPlaying.value=false
  }
onMounted(() => { startAutoPlay() })
onUnmounted(() => { stopAutoPlay() })


</script>
<style scoped>
    /* 长队容器 */
.img-group {
  display: flex;        /* 横着排 */
  width: 100%;          /* 占满窗口宽度 */
  height: 400px;        /* 你想多高就改数字 */
}

/* 每一张图 */
.img-group img {
  width: 100%;          /* 每张图宽 = 窗口宽 */
  height: 100%;
  object-fit: cover;    /* 图不变形，填满区域 */
  flex-shrink: 0;       /* 不让图被挤扁 */
}
</style>
