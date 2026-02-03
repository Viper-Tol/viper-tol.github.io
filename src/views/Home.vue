<template>
  <div class="home-page">
    <!-- Hero 区域：全宽轮播图 -->
    <section class="hero-section">
      <Carousel :images="farmImg" :showArrows="false" />
      <div class="hero-overlay">
        <h1 class="hero-title">伊犁利牧春畜牧科技服务有限公司</h1>
        <p class="hero-subtitle">专注畜牧科技服务 · 守护牧场健康</p>
      </div>
    </section>

    <!-- 数据统计区 -->
    <StatsSection />

    <!-- 关于我们简介 -->
    <section class="about-section">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">关于我们</h2>
          <p class="section-desc">深耕本地牧业二十载，专业服务值得信赖</p>
        </div>
        <div class="about-content">
          <p class="about-text">
            伊犁利牧春畜牧科技服务有限公司成立于2023年，是一家集畜牧技术服务、疫病防控、兽药供应、养殖培训于一体的专业化科技服务企业。公司持有《动物诊疗许可证》《兽药经营许可证》等资质，拥有14人专业团队（含高级兽医师2人、执业兽医师2人），以"全周期、一站式"服务模式开展良种繁育、疫病快速诊疗、兽药饲料供应及农牧民技术培训等业务。
          </p>
          <p class="about-text">
            服务网络覆盖伊宁市8个乡镇兽医站、3个养殖合作社，提供2小时紧急到场、7×24小时热线服务。2023年获评"伊宁市农业产业化重点企业"，2024年项目获自治区科技进步三等奖。
          </p>
        </div>
      </div>
    </section>

    <!-- 防疫展板 -->
    <section class="prevention-section">
      <div class="container">
        <div class="section-header light">
          <h2 class="section-title">防疫展板</h2>
          <p class="section-desc">标准化防疫流程 · 科学养殖指导</p>
        </div>
        <div class="carousel-wrapper">
          <Carousel :images="preImg" :showArrows="true" />
        </div>
      </div>
    </section>

    <!-- 页脚 -->
    <footer class="footer">
      <div class="container">
        <p class="copyright">© 2024 伊犁利牧春畜牧科技服务有限公司 · 版权所有</p>
        <p class="contact">服务热线：15299261462 | 地址：新疆伊宁市巴彦岱镇安康路西2号楼门面房</p>
      </div>
    </footer>
  </div>
</template>

<script setup>
import Carousel from '@/components/common/Carousel.vue'
import StatsSection from '@/components/StatsSection.vue'

const farmImg = [
  { id: 1, src: '/img/farm1.jpg' },
  { id: 2, src: '/img/farm2.jpg' },
  { id: 3, src: '/img/farm3.jpg' },
  { id: 4, src: '/img/farm4.jpg' },
]

const preImg = [
  { id: 1, src: '/imgP/1.jpg' },
  { id: 2, src: '/imgP/2.jpg' },
  { id: 3, src: '/imgP/3.jpg' },
  { id: 4, src: '/imgP/4.jpg' },
  { id: 5, src: '/imgP/5.jpg' },
  { id: 6, src: '/imgP/6.jpg' },
  { id: 7, src: '/imgP/7.jpg' },
  { id: 8, src: '/imgP/8.jpg' },
  { id: 9, src: '/imgP/9.jpg' },
  { id: 10, src: '/imgP/10.jpg' },
  { id: 12, src: '/imgP/12.jpg' },
  { id: 13, src: '/imgP/13.jpg' },
]
</script>

<style scoped>
/* 基础变量（便于维护） */
.home-page {
  --primary-color: #2c7a4d;
  --primary-dark: #1a5f3f;
  --primary-light: #e6f4ea;
  --text-dark: #1a202c;
  --text-gray: #4a5568;
  --bg-gray: #f7fafc;
  --white: #ffffff;
  --max-width: 1200px;
  --section-padding: 80px;
}

/* 容器：统一最大宽度 */
.container {
  max-width: var(--max-width);
  margin: 0 auto;
  padding: 0 20px;
}

/* 区块标题统一样式 */
.section-header {
  text-align: center;
  margin-bottom: 50px;
}

.section-title {
  font-size: 32px;
  font-weight: 700;
  color: var(--primary-dark);
  margin-bottom: 12px;
  position: relative;
  display: inline-block;
}

/* 标题下的装饰线 */
.section-title::after {
  content: '';
  display: block;
  width: 60px;
  height: 4px;
  background: linear-gradient(90deg, var(--primary-color), #48bb78);
  margin: 12px auto 0;
  border-radius: 2px;
}

.section-desc {
  font-size: 16px;
  color: var(--text-gray);
  margin-top: 8px;
}

/* Hero 区域：全宽轮播图 + 文字叠加 */
.hero-section {
  position: relative;
  width: 100%;
  height: 500px;
  overflow: hidden;
}

.hero-section :deep(.carousel) {
  height: 100%;
}

.hero-section :deep(.carousel-inner) {
  height: 100%;
}

.hero-section :deep(.carousel-item) {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.hero-overlay {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  background: linear-gradient(to top, rgba(0,0,0,0.7) 0%, rgba(0,0,0,0) 100%);
  padding: 60px 20px 40px;
  text-align: center;
  color: white;
}

.hero-title {
  font-size: 36px;
  font-weight: 700;
  margin-bottom: 12px;
  text-shadow: 0 2px 4px rgba(0,0,0,0.3);
  letter-spacing: 2px;
}

.hero-subtitle {
  font-size: 18px;
  opacity: 0.95;
  letter-spacing: 4px;
  text-transform: uppercase;
}

/* 关于我们区域 */
.about-section {
  padding: var(--section-padding) 0;
  background-color: var(--white);
}

.about-content {
  max-width: 800px;
  margin: 0 auto;
}

.about-text {
  font-size: 16px;
  line-height: 1.8;
  color: var(--text-gray);
  margin-bottom: 20px;
  text-align: justify;
  text-indent: 2em;
}

.about-text:last-child {
  margin-bottom: 0;
}

/* 防疫展板区域（深色背景突出） */
.prevention-section {
  padding: var(--section-padding) 0;
  background-color: var(--bg-gray);
  border-top: 1px solid #e2e8f0;
}

.prevention-section .section-title {
  color: var(--primary-dark);
}

.carousel-wrapper {
  max-width: 900px;
  margin: 0 auto;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 10px 30px rgba(0,0,0,0.1);
}

/* 页脚 */
.footer {
  background-color: var(--primary-dark);
  color: rgba(255,255,255,0.8);
  padding: 40px 0;
  text-align: center;
  font-size: 14px;
}

.copyright {
  margin-bottom: 8px;
  font-weight: 500;
}

.contact {
  opacity: 0.8;
  font-size: 13px;
}

/* 响应式调整 */
@media (max-width: 768px) {
  .home-page {
    --section-padding: 50px;
  }
  
  .hero-section {
    height: 400px;
  }
  
  .hero-title {
    font-size: 24px;
  }
  
  .hero-subtitle {
    font-size: 14px;
    letter-spacing: 2px;
  }
  
  .section-title {
    font-size: 24px;
  }
  
  .about-text {
    font-size: 15px;
  }
}

/* 深度选择器：调整 Carousel 组件在容器中的样式 */
:deep(.carousel) {
  width: 100%;
  height: 100%;
  position: relative;
}

:deep(.carousel-inner) {
  display: flex;
  height: 100%;
  transition: transform 0.5s ease;
}

:deep(.carousel-item) {
  width: 100%;
  height: 100%;
  flex-shrink: 0;
  object-fit: cover;
}

:deep(.dots) {
  bottom: 20px;
}

:deep(.dots span) {
  width: 10px;
  height: 10px;
  background: rgba(255,255,255,0.5);
  margin: 0 6px;
  border-radius: 50%;
  cursor: pointer;
  transition: all 0.3s;
}

:deep(.dots span.active) {
  background: white;
  width: 24px;
  border-radius: 5px;
}
</style>