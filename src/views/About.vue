<template>
  <div class="about-page">
    <!-- Hero小横幅 -->
    <div class="about-hero">
      <h1>关于我们</h1>
      <p>专注畜牧科技服务 · 守护牧场健康</p>
    </div>
    
    <!-- 核心数据（复用StatsSection或简化版） -->
    <div class="about-stats">
      <div>20+年行业经验</div>
      <div>24/2小时极速响应</div>
      <div>1200+头免费配种</div>
    </div>
    
    <!-- 公司简介 -->
    <div class="about-content">
      <h2>公司简介</h2>
      <p>伊犁利牧春畜牧科技服务有限公司成立于2023年，总部位于伊宁市巴彦岱镇，是一家集畜牧技术服务、疫病防控、兽药供应与养殖培训于一体的专业化科技服务企业。公司提供全周期一站式服务，包括良种繁育、疫病诊疗、兽药饲料供应及技术培训，服务覆盖伊犁河谷多个乡镇，拥有14人专业团队和高效响应网络。秉承“科技引领畜牧，服务赋能未来”的理念，公司致力于推动畜牧产业升级，助力乡村振兴，目标成为西北地区最具影响力的畜牧科技服务品牌。</p>
      <p>持有《动物诊疗许可证》《兽药经营许可证》...</p>
    </div>
    
    <!-- 营业执照 -->
    <div class="about-license">
      <h2>资质证书</h2>
      <img src="/imgP/license.jpg" alt="营业执照" />
    </div>
  </div>
</template>
<script setup>
// 这里可以留空，或者以后加逻辑
</script>

<style scoped>
.about-page {
  --primary-color: #2c7a4d;
  --primary-dark: #1a5f3f;
  --primary-light: #e6f4ea;
  --text-dark: #1a202c;
  --text-gray: #4a5568;
  --bg-gray: #f7fafc;
  --white: #ffffff;
  --max-width: 1200px;
  --section-padding: 60px;
}

/* Hero区域 */
.about-hero {
  background: linear-gradient(135deg, #f0f9f4 0%, #e6f4ea 100%);
  padding: 60px 20px;
  text-align: center;
}

.about-hero h1 {
  font-size: 32px;
  font-weight: 700;
  color: var(--primary-dark);
  margin-bottom: 12px;
}

.about-hero p {
  font-size: 16px;
  color: #5a8c6e;
}

/* 核心数据 - 复用StatsSection风格或简化 */
.about-stats {
  display: flex;
  justify-content: space-around;
  padding: 40px 20px;
  background: var(--white);
  max-width: var(--max-width);
  margin: 0 auto;
}

.about-stats div {
  text-align: center;
  font-size: 18px;
  font-weight: 600;
  color: var(--primary-color);
}

/* 公司简介 */
.about-content {
  max-width: 800px;
  margin: 0 auto;
  padding: var(--section-padding) 20px;
}

.about-content h2 {
  font-size: 24px;
  font-weight: 700;
  color: var(--primary-dark);
  margin-bottom: 20px;
  position: relative;
  display: inline-block;
}

.about-content h2::after {
  content: '';
  display: block;
  width: 40px;
  height: 3px;
  background: var(--primary-color);
  margin-top: 8px;
  border-radius: 2px;
}

.about-content p {
  font-size: 16px;
  line-height: 1.8;
  color: var(--text-gray);
  margin-bottom: 16px;
  text-align: justify;
}

/* 营业执照 */
.about-license {
  background: var(--bg-gray);
  padding: var(--section-padding) 20px;
  text-align: center;
}

.about-license h2 {
  font-size: 24px;
  font-weight: 700;
  color: var(--primary-dark);
  margin-bottom: 20px;
}

.about-license img {
  max-width: 600px;
  width: 100%;
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0,0,0,0.1);
}

/* 响应式 */
@media (max-width: 768px) {
  .about-hero h1 {
    font-size: 24px;
  }
  
  .about-stats {
    flex-direction: column;
    gap: 20px;
  }
  
  .about-content, .about-license {
    padding: 40px 16px;
  }
}

</style>