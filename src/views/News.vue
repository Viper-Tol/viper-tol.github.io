<template>
  <div class="download-page">
    <!-- Hero -->
    <div class="download-hero">
      <h1>资料下载</h1>
      <p>服务协议 · 管理制度 · 操作规范</p>
    </div>
    
    <!-- 下载列表 -->
    <div class="download-list">
      <div v-for="file in files" :key="file.name" class="download-card">
        <div class="file-icon">📄</div>
        <h3>{{ file.title }}</h3>
        <p>{{ file.desc }}</p>
        <a :href="file.url" download class="download-btn">下载PDF</a>
      </div>
    </div>
    
    <!-- 提示 -->
    <div class="download-tip">
      <p>如需更多资料，请联系：15299261462</p>
    </div>
  </div>
</template>

<script setup>
const files = [
  {
    title: '服务协议模板',
    desc: '标准化服务合同，明确双方权责',
    url: '/downloads/项目服务协议.pdf'
  },
  {
    title: '公司管理制度',
    desc: '规范运营流程，保障服务质量',
    url: '/downloads/伊犁利牧春畜牧科技服务有限公司管理制度.pdf'
  },
  {
    title: '畜牧兽医服务操作手册',
    desc: '专业服务标准，14项全流程规范',
    url: '/downloads/伊犁州畜牧兽医社会化服务组织管理操作手册.pdf'
  }
]
</script>



<style scoped>
.download-page {
  --primary-color: #2c7a4d;
  --primary-dark: #1a5f3f;
  --primary-light: #e6f4ea;
  --text-gray: #4a5568;
  --bg-gray: #f7fafc;
  --white: #ffffff;
}

.download-hero {
  background: linear-gradient(135deg, #f0f9f4 0%, #e6f4ea 100%);
  padding: 60px 20px;
  text-align: center;
}

.download-hero h1 {
  font-size: 32px;
  font-weight: 700;
  color: var(--primary-dark);
  margin-bottom: 12px;
}

.download-hero p {
  font-size: 16px;
  color: #5a8c6e;
}

.download-list {
  max-width: 800px;
  margin: 0 auto;
  padding: 60px 20px;
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.download-card {
  background: var(--white);
  border-radius: 12px;
  padding: 24px;
  display: flex;
  align-items: center;
  gap: 20px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.05);
  border: 1px solid #e0f0e8;
}

.file-icon {
  font-size: 40px;
  flex-shrink: 0;
}

.download-card h3 {
  font-size: 18px;
  font-weight: 600;
  color: var(--primary-dark);
  margin: 0 0 4px 0;
}

.download-card p {
  font-size: 14px;
  color: var(--text-gray);
  margin: 0;
  flex-grow: 1;
}

.download-btn {
  background: var(--primary-color);
  color: white;
  padding: 10px 20px;
  border-radius: 6px;
  text-decoration: none;
  font-size: 14px;
  font-weight: 500;
  flex-shrink: 0;
}

.download-btn:hover {
  background: var(--primary-dark);
}

.download-tip {
  text-align: center;
  padding: 40px 20px;
  color: var(--text-gray);
  font-size: 14px;
}

@media (max-width: 768px) {
  .download-card {
    flex-direction: column;
    text-align: center;
  }
  
  .download-btn {
    width: 100%;
    margin-top: 12px;
  }
}
</style>
