<script setup lang="ts">
const projects = [
  {
    id: 1,
    name: '电商网站前端重构',
    description: '使用Vue 3 + TypeScript重构了传统电商网站的前端部分，提升了页面加载速度和用户体验。',
    techStack: ['Vue 3', 'TypeScript', 'Ant Design Vue', 'Vite'],
    role: '前端开发工程师',
    period: '2023.03 - 2023.08',
    link: 'https://example.com/ecommerce'
  },
  {
    id: 2,
    name: '企业管理系统',
    description: '开发了一套完整的企业管理系统，包括员工管理、项目管理、财务管理等模块。',
    techStack: ['React', 'TypeScript', 'Element Plus', 'Webpack'],
    role: '前端负责人',
    period: '2022.09 - 2023.02',
    link: 'https://example.com/erp'
  },
  {
    id: 3,
    name: '移动应用跨端开发',
    description: '使用Taro框架开发了一款跨端移动应用，同时支持微信小程序、支付宝小程序和H5。',
    techStack: ['Taro', 'React', 'TypeScript', 'Redux'],
    role: '前端开发工程师',
    period: '2021.12 - 2022.08',
    link: 'https://example.com/mobile-app'
  },
  {
    id: 4,
    name: '数据可视化平台',
    description: '开发了一个数据可视化平台，用于展示企业的业务数据和运营情况。',
    techStack: ['Vue 3', 'TypeScript', 'ECharts', 'Vite'],
    role: '前端开发工程师',
    period: '2021.06 - 2021.11',
    link: 'https://example.com/visualization'
  }
]
</script>

<template>
  <div class="projects">
    <div class="projects-list">
      <div v-for="project in projects" :key="project.id" class="project-item">
        <div class="project-header">
          <div class="project-info">
            <h3 class="project-name">{{ project.name }}</h3>
            <p class="project-role">{{ project.role }} | {{ project.period }}</p>
          </div>
          <a :href="project.link" target="_blank" class="project-link">查看项目</a>
        </div>
        <div class="project-description">{{ project.description }}</div>
        <div class="project-tech">
          <span class="tech-label">技术栈：</span>
          <div class="tech-tags">
            <span v-for="tech in project.techStack" :key="tech" class="tech-tag">{{ tech }}</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.projects {
  background-color: #f8f9fa;
  padding: 25px;
  border-radius: 12px;
}

.projects-list {
  display: flex;
  flex-direction: column;
  gap: 30px;
}

.project-item {
  background-color: white;
  padding: 25px;
  border-radius: 12px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}

.project-item::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 4px;
  background: linear-gradient(90deg, #667eea 0%, #764ba2 100%);
}

.project-item:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
}

.project-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  margin-bottom: 15px;
  flex-wrap: wrap;
  gap: 15px;
}

.project-info {
  flex: 1;
  min-width: 250px;
}

.project-name {
  font-size: 1.4rem;
  font-weight: 600;
  margin-bottom: 8px;
  color: #333;
  transition: color 0.3s ease;
}

.project-item:hover .project-name {
  color: #667eea;
}

.project-role {
  font-size: 0.95rem;
  color: #666;
  margin-bottom: 0;
  display: flex;
  gap: 15px;
  align-items: center;
}

.project-role::before {
  content: '👨‍💻';
  margin-right: 5px;
}

.project-link {
  color: white;
  text-decoration: none;
  font-size: 0.95rem;
  padding: 8px 20px;
  background: linear-gradient(90deg, #667eea 0%, #764ba2 100%);
  border-radius: 25px;
  transition: all 0.3s ease;
  font-weight: 500;
  box-shadow: 0 2px 8px rgba(102, 126, 234, 0.3);
}

.project-link:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(102, 126, 234, 0.5);
}

.project-description {
  font-size: 1.05rem;
  color: #555;
  line-height: 1.7;
  margin-bottom: 20px;
  padding: 15px;
  background-color: #f8f9fa;
  border-radius: 8px;
  border-left: 3px solid #667eea;
}

.project-tech {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.tech-label {
  font-size: 0.95rem;
  color: #999;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.tech-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}

.tech-tag {
  font-size: 0.85rem;
  color: #667eea;
  background-color: #667eea15;
  padding: 5px 12px;
  border-radius: 15px;
  font-weight: 500;
  transition: all 0.3s ease;
  border: 1px solid #667eea25;
}

.tech-tag:hover {
  background-color: #667eea;
  color: white;
  transform: translateY(-1px);
}

/* 响应式设计 */
@media (max-width: 768px) {
  .project-header {
    flex-direction: column;
    gap: 10px;
  }
  
  .project-info {
    min-width: auto;
  }
  
  .project-name {
    font-size: 1.2rem;
  }
  
  .project-item {
    padding: 20px;
  }
}
</style>
