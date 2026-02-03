<template>
  <section class="stats-section">
    <div class="container">
      <h2 class="section-title">专业服务，值得信赖</h2>
      <p class="section-subtitle">深耕本地牧业二十载，维汉融合团队随时待命</p>
      
      <div class="stats-grid">
        <!-- 经验卡片 -->
        <div class="stat-card">
          <div class="stat-icon">🏆</div>
          <div class="stat-number">20+</div>
          <h3 class="stat-title">年行业深耕</h3>
          <p class="stat-desc">牧场主亲自带队，累计服务本地养殖户超300户，疫病防控零重大事故</p>
        </div>

        <!-- 响应卡片 -->
        <div class="stat-card highlight">
          <div class="stat-icon">⚡</div>
          <div class="stat-number">24/2</div>
          <h3 class="stat-title">小时极速响应</h3>
          <p class="stat-desc">覆盖8个乡镇兽医站、3个养殖合作社，维汉双语团队2小时内到场</p>
        </div>

        <!-- 公益卡片 -->
        <div class="stat-card">
          <div class="stat-icon">🐄</div>
          <div class="stat-number">1200+</div>
          <h3 class="stat-title">头免费配种</h3>
          <p class="stat-desc">23-24年连续获奖，带动本地就业36人，技术培训覆盖牧民200人次</p>
        </div>
      </div>

      <div class="stats-footer">
        <span class="badge">政府认证资质</span>
        <span class="badge">连续2年先进单位</span>
        <p class="contact-hint">📍 服务范围：XX市8个乡镇 | 📞 24小时咨询热线：xxx-xxxxxxx</p>
      </div>
    </div>
  </section>
</template>

<style scoped>
.stats-section {
  background: linear-gradient(135deg, #f0f9f4 0%, #e6f4ea 100%);
  padding: 60px 20px;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
}

.section-title {
  text-align: center;
  font-size: 32px;
  color: #1a5f3f;
  margin-bottom: 8px;
  font-weight: 700;
  letter-spacing: -0.5px;
}

.section-subtitle {
  text-align: center;
  font-size: 16px;
  color: #5a8c6e;
  margin-bottom: 40px;
  font-weight: 400;
}

.stats-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 30px;
  margin-bottom: 40px;
}

.stat-card {
  background: white;
  border-radius: 16px;
  padding: 32px 24px;
  text-align: center;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05), 0 2px 4px -1px rgba(0, 0, 0, 0.03);
  transition: all 0.3s ease;
  border: 1px solid #e0f0e8;
  position: relative;
  overflow: hidden;
}

.stat-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 20px 25px -5px rgba(44, 122, 77, 0.1), 0 10px 10px -5px rgba(44, 122, 77, 0.04);
  border-color: #2c7a4d;
}

.stat-card.highlight {
  background: linear-gradient(135deg, #2c7a4d 0%, #3d9970 100%);
  color: white;
  border: none;
}

.stat-card.highlight .stat-title,
.stat-card.highlight .stat-desc {
  color: rgba(255, 255, 255, 0.95);
}

.stat-card.highlight .stat-number {
  color: white;
  text-shadow: 0 2px 4px rgba(0,0,0,0.2);
}

.stat-icon {
  font-size: 40px;
  margin-bottom: 16px;
  display: block;
}

.stat-number {
  font-size: 48px;
  font-weight: 800;
  color: #2c7a4d;
  line-height: 1;
  margin-bottom: 12px;
  letter-spacing: -2px;
}

.stat-title {
  font-size: 18px;
  font-weight: 600;
  color: #1a5f3f;
  margin-bottom: 12px;
  margin-top: 0;
}

.stat-desc {
  font-size: 14px;
  color: #666;
  line-height: 1.6;
  margin: 0;
}

.stats-footer {
  text-align: center;
  padding-top: 20px;
  border-top: 1px solid #d0e8d8;
}

.badge {
  display: inline-block;
  background: rgba(44, 122, 77, 0.1);
  color: #2c7a4d;
  padding: 6px 16px;
  border-radius: 20px;
  font-size: 13px;
  font-weight: 600;
  margin: 0 8px 10px;
  border: 1px solid rgba(44, 122, 77, 0.2);
}

.contact-hint {
  margin-top: 16px;
  font-size: 14px;
  color: #5a8c6e;
  font-weight: 500;
}

/* 移动端适配 */
@media (max-width: 768px) {
  .stats-section {
    padding: 40px 16px;
  }
  
  .section-title {
    font-size: 24px;
  }
  
  .stat-number {
    font-size: 36px;
  }
  
  .stats-grid {
    gap: 20px;
  }
}
</style>