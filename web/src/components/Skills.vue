<script setup lang="ts">
const skills = [
  { name: 'Vue 3', level: '精通', category: '前端框架' },
  { name: 'TypeScript', level: '精通', category: '编程语言' },
  { name: 'React', level: '熟练', category: '前端框架' },
  { name: 'JavaScript', level: '精通', category: '编程语言' },
  { name: 'HTML5', level: '精通', category: '前端技术' },
  { name: 'CSS3', level: '精通', category: '前端技术' },
  { name: 'Ant Design Vue', level: '熟练', category: 'UI框架' },
  { name: 'Element Plus', level: '熟练', category: 'UI框架' },
  { name: 'Vite', level: '熟练', category: '构建工具' },
  { name: 'Webpack', level: '熟练', category: '构建工具' },
  { name: 'Git', level: '精通', category: '版本控制' },
  { name: 'Node.js', level: '熟练', category: '后端技术' }
]
</script>

<template>
  <div class="skills">
    <div class="skills-grid">
      <div v-for="skill in skills" :key="skill.name" class="skill-item">
        <div class="skill-header">
          <h3 class="skill-name">{{ skill.name }}</h3>
          <span class="skill-category">{{ skill.category }}</span>
        </div>
        <div class="skill-level">
          <div class="level-info">
            <span class="level-label">熟练度</span>
            <span class="level-value">{{ skill.level }}</span>
          </div>
          <div class="level-bar">
            <div class="level-progress"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.skills {
  background-color: #f8f9fa;
  padding: 25px;
  border-radius: 12px;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 20px;
}

.skill-item {
  background-color: white;
  padding: 20px;
  border-radius: 12px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}

.skill-item::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 4px;
  background: linear-gradient(90deg, #667eea 0%, #764ba2 100%);
}

.skill-item:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
}

.skill-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 15px;
}

.skill-name {
  font-size: 1.1rem;
  font-weight: 600;
  color: #333;
  margin: 0;
}

.skill-category {
  font-size: 0.85rem;
  color: #667eea;
  background-color: #667eea15;
  padding: 4px 12px;
  border-radius: 12px;
  font-weight: 500;
}

.skill-level {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.level-info {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.level-label {
  font-size: 0.9rem;
  color: #999;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.level-value {
  font-size: 1rem;
  color: #333;
  font-weight: 600;
}

/* 熟练度进度条 */
.level-bar {
  height: 6px;
  background-color: #f0f0f0;
  border-radius: 3px;
  overflow: hidden;
  margin-top: 8px;
}

.level-progress {
  height: 100%;
  background: linear-gradient(90deg, #667eea 0%, #764ba2 100%);
  border-radius: 3px;
  transition: width 0.5s ease;
}

/* 根据熟练度设置进度条宽度 */
.skill-item:nth-child(1) .level-progress, /* Vue 3 */
.skill-item:nth-child(2) .level-progress, /* TypeScript */
.skill-item:nth-child(4) .level-progress, /* JavaScript */
.skill-item:nth-child(5) .level-progress, /* HTML5 */
.skill-item:nth-child(6) .level-progress, /* CSS3 */
.skill-item:nth-child(13) .level-progress /* Git */
  {
  width: 95%;
}

.skill-item:nth-child(3) .level-progress, /* React */
.skill-item:nth-child(7) .level-progress, /* Ant Design Vue */
.skill-item:nth-child(8) .level-progress, /* Element Plus */
.skill-item:nth-child(9) .level-progress, /* Vite */
.skill-item:nth-child(10) .level-progress, /* Webpack */
.skill-item:nth-child(14) .level-progress /* Node.js */
  {
  width: 85%;
}
</style>
