<template>
  <div class="services-page">
    <!-- Hero -->
    <div class="services-hero">
      <h1>服务内容</h1>
      <p>14项专业服务 · 覆盖畜牧全产业链</p>
      <a href="/downloads/畜牧业社会化服务公司服务内容.pdf" download>下载完整服务手册</a>
    </div>
    
    <!-- 核心服务4项 -->
    <div class="core-services">
      <div v-for="service in coreServices" :key="service.name" class="service-card">
        <div class="icon">{{ service.icon }}</div>
        <h3>{{ service.name }}</h3>
        <p>{{ service.desc }}</p>
        <ul>
          <li v-for="item in service.items" :key="item">{{ item }}</li>
        </ul>
      </div>
    </div>
    
    <!-- 价格表图片 -->
    <div class="price-section">
      <h2>服务价格</h2>
      <img src="/imgP/价格表.jpg" alt="服务价格表" />
      <p>详细请下载完整手册或电话咨询</p>
    </div>
    
    <!-- 全部服务列表（简化） -->
    <div class="all-services">
      <h2>全部服务项目</h2>
      <div class="service-list">
        <span v-for="(service, index) in allServices" :key="index">
          {{ service }} {{ index < allServices.length - 1 ? '·' : '' }}
        </span>
      </div>
      <a href="/downloads/畜牧业社会化服务公司服务内容.pdf" download>下载完整服务手册</a>
    </div>
  </div>
</template>

<script setup>
const coreServices = [
  {
    icon: '💉',
    name: '疫病免疫注射',
    desc: '强制免疫政策执行，持证兽医操作，抗体监测达标',
    items: ['口蹄疫/禽流感/猪瘟', '持证兽医注射', '抗体效价监测']
  },
  {
    icon: '🧬',
    name: '品种改良服务',
    desc: '人工授精、基因检测、胚胎移植，提升生产性能',
    items: ['优质种畜引进', '基因选育技术', '胚胎移植推广']
  },
  {
    icon: '🚨',
    name: '24小时上门服务',
    desc: '疫病防控、紧急诊疗、免疫注射，随时响应',
    items: ['24小时热线', '紧急疫病响应', '服务到户']
  },
  {
    icon: '📊',
    name: '信息化管理服务',
    desc: '电子档案、大数据分析、智能决策支持',
    items: ['电子养殖档案', '数据采集分析', '生产决策支持']
  }
]

const allServices = [
  '疫病免疫', '畜牧保险', '品种改良', '疾病诊疗', 
  '疫苗药浴', '兽药售卖', '24h上门', '技术培训',
  '信息化管理', '环境治理', '质量追溯', '绿色饲料',
  '粪污处理', '金融服务'
]
</script>



<style scoped>
.services-page {
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
.services-hero {
  background: linear-gradient(135deg, #f0f9f4 0%, #e6f4ea 100%);
  padding: 60px 20px;
  text-align: center;
}

.services-hero h1 {
  font-size: 32px;
  font-weight: 700;
  color: var(--primary-dark);
  margin-bottom: 12px;
}

.services-hero p {
  font-size: 16px;
  color: #5a8c6e;
  margin-bottom: 20px;
}

.services-hero a {
  display: inline-block;
  background: var(--primary-color);
  color: white;
  padding: 12px 24px;
  border-radius: 8px;
  text-decoration: none;
  font-weight: 600;
  transition: background 0.3s;
}

.services-hero a:hover {
  background: var(--primary-dark);
}

/* 核心服务4项 */
.core-services {
  max-width: var(--max-width);
  margin: 0 auto;
  padding: var(--section-padding) 20px;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 30px;
}

.service-card {
  background: var(--white);
  border-radius: 16px;
  padding: 32px 24px;
  text-align: center;
  box-shadow: 0 4px 6px rgba(0,0,0,0.05);
  transition: all 0.3s ease;
  border: 1px solid #e0f0e8;
}

.service-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 20px 25px rgba(44,122,77,0.1);
}

.service-card .icon {
  font-size: 48px;
  margin-bottom: 16px;
}

.service-card h3 {
  font-size: 20px;
  font-weight: 700;
  color: var(--primary-dark);
  margin-bottom: 12px;
}

.service-card p {
  font-size: 14px;
  color: var(--text-gray);
  margin-bottom: 16px;
  line-height: 1.6;
}

.service-card ul {
  list-style: none;
  padding: 0;
  margin: 0;
  text-align: left;
}

.service-card li {
  font-size: 14px;
  color: var(--text-gray);
  padding: 6px 0;
  padding-left: 20px;
  position: relative;
}

.service-card li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: var(--primary-color);
  font-weight: bold;
}

/* 价格表区域 */
.price-section {
  background: var(--bg-gray);
  padding: var(--section-padding) 20px;
  text-align: center;
}

.price-section h2 {
  font-size: 24px;
  font-weight: 700;
  color: var(--primary-dark);
  margin-bottom: 20px;
}

.price-section img {
  max-width: 800px;
  width: 100%;
  border-radius: 12px;
  box-shadow: 0 10px 30px rgba(0,0,0,0.1);
}

.price-section p {
  margin-top: 20px;
  color: var(--text-gray);
  font-size: 14px;
}

/* 全部服务列表 */
.all-services {
  max-width: var(--max-width);
  margin: 0 auto;
  padding: var(--section-padding) 20px;
  text-align: center;
}

.all-services h2 {
  font-size: 24px;
  font-weight: 700;
  color: var(--primary-dark);
  margin-bottom: 20px;
}

.service-list {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 8px;
  margin-bottom: 24px;
  font-size: 14px;
  color: var(--text-gray);
}

.service-list span {
  background: rgba(44,122,77,0.1);
  color: var(--primary-color);
  padding: 6px 12px;
  border-radius: 20px;
  font-weight: 500;
}

.all-services a {
  display: inline-block;
  color: var(--primary-color);
  text-decoration: none;
  font-weight: 600;
  border-bottom: 2px solid var(--primary-color);
  padding-bottom: 2px;
}

.all-services a:hover {
  color: var(--primary-dark);
  border-color: var(--primary-dark);
}

/* 响应式 */
@media (max-width: 768px) {
  .services-hero h1 {
    font-size: 24px;
  }
  
  .core-services {
    grid-template-columns: 1fr;
    padding: 40px 16px;
  }
  
  .price-section, .all-services {
    padding: 40px 16px;
  }
}
</style>