<script setup lang="ts">
const personalInfo = {
  name: 'Renato',
  title: '全栈开发工程师',
  email: 'renatito@163.com',
  // phone: '138-0013-8000',
  location: '西安市',
  github: 'https://github.com/Renato-Santiago',
  // linkedin: 'https://linkedin.com/in/zhangsan',
  experience: '11年',
  introduction: '专注于全栈开发及机器学习,具有丰富的项目经验,擅长Vue 3、TypeScript、React等技术栈。热爱技术,乐于分享,追求卓越。',
  website: 'https://renatito.com',
  wechat: 'mx153370'
}
</script>

<template>
  <div class="personal-info">
    <div class="intro-section">
      <p class="introduction">{{ personalInfo.introduction }}</p>
    </div>
    
    <div class="info-grid">
      <div class="info-item">
        <div class="info-icon">👤</div>
        <div class="info-content">
          <span class="label">姓名</span>
          <span class="value">{{ personalInfo.name }}</span>
        </div>
      </div>
      <div class="info-item">
        <div class="info-icon">💼</div>
        <div class="info-content">
          <span class="label">职位</span>
          <span class="value">{{ personalInfo.title }}</span>
        </div>
      </div>
      <div class="info-item">
        <div class="info-icon">📧</div>
        <div class="info-content">
          <span class="label">邮箱</span>
          <a :href="`mailto:${personalInfo.email}`" class="value link">{{ personalInfo.email }}</a>
        </div>
      </div>
      <!-- <div class="info-item">
        <div class="info-icon">📱</div>
        <div class="info-content">
          <span class="label">电话</span>
          <span class="value">{{ personalInfo.phone }}</span>
        </div>
      </div> -->
      <div class="info-item">
        <div class="info-icon">📍</div>
        <div class="info-content">
          <span class="label">所在地</span>
          <span class="value">{{ personalInfo.location }}</span>
        </div>
      </div>
      <div class="info-item">
        <div class="info-icon">💻</div>
        <div class="info-content">
          <span class="label">GitHub</span>
          <a :href="personalInfo.github" target="_blank" class="value link">{{ personalInfo.github }}</a>
        </div>
      </div>
      <!-- <div class="info-item">
        <div class="info-icon">🔗</div>
        <div class="info-content">
          <span class="label">LinkedIn</span>
          <a :href="personalInfo.linkedin" target="_blank" class="value link">{{ personalInfo.linkedin }}</a>
        </div>
      </div> -->
      <div class="info-item">
        <div class="info-icon">🌐</div>
        <div class="info-content">
          <span class="label">个人网站</span>
          <a :href="personalInfo.website" target="_blank" class="value link">{{ personalInfo.website }}</a>
        </div>
      </div>
      <div class="info-item">
        <div class="info-icon">⏰</div>
        <div class="info-content">
          <span class="label">工作经验</span>
          <span class="value">{{ personalInfo.experience }}</span>
        </div>
      </div>
      <div class="info-item">
        <div class="info-icon">💬</div>
        <div class="info-content">
          <span class="label">微信</span>
          <span class="value">{{ personalInfo.wechat }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.personal-info {
  background-color: #f8f9fa;
  padding: 25px;
  border-radius: 12px;
}

.intro-section {
  margin-bottom: 30px;
  padding: 20px;
  background: linear-gradient(135deg, #667eea15 0%, #764ba215 100%);
  border-radius: 8px;
  border-left: 4px solid #667eea;
}

.introduction {
  font-size: 1.1rem;
  line-height: 1.6;
  color: #555;
  margin: 0;
}

.info-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 20px;
}

.info-item {
  display: flex;
  align-items: flex-start;
  gap: 12px;
  padding: 15px;
  background-color: white;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
  transition: all 0.3s ease;
}

.info-item:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

.info-icon {
  font-size: 1.5rem;
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  border-radius: 50%;
  flex-shrink: 0;
}

.info-content {
  flex: 1;
}

.label {
  display: block;
  font-size: 0.85rem;
  color: #999;
  margin-bottom: 5px;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.value {
  display: block;
  font-size: 1rem;
  color: #333;
  font-weight: 500;
}

.link {
  color: #667eea;
  text-decoration: none;
  transition: all 0.3s ease;
}

.link:hover {
  color: #764ba2;
  text-decoration: underline;
}
</style>
