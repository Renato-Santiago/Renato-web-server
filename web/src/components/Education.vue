<script setup lang="ts">
const educationList = [
  {
    id: 1,
    degree: '本科',
    major: '计算机科学与技术',
    school: '北京大学',
    period: '2015.09 - 2019.06',
    description: '主修计算机科学与技术，辅修数学，GPA 3.8/4.0'
  },
  {
    id: 2,
    degree: '硕士',
    major: '软件工程',
    school: '清华大学',
    period: '2019.09 - 2022.06',
    description: '研究方向：前端开发技术，发表论文2篇'
  }
]
</script>

<template>
  <div class="education">
    <div class="education-list">
      <div v-for="edu in educationList" :key="edu.id" class="education-item">
        <div class="education-header">
          <div class="education-info">
            <h3 class="degree">{{ edu.degree }} - {{ edu.major }}</h3>
            <p class="school">{{ edu.school }}</p>
          </div>
          <div class="period">{{ edu.period }}</div>
        </div>
        <div class="description">{{ edu.description }}</div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.education {
  background-color: #f8f9fa;
  padding: 25px;
  border-radius: 12px;
}

.education-list {
  display: flex;
  flex-direction: column;
  gap: 25px;
  position: relative;
}

/* 时间线样式 */
.education-list::before {
  content: '';
  position: absolute;
  left: 20px;
  top: 0;
  bottom: 0;
  width: 2px;
  background: linear-gradient(to bottom, #667eea, #764ba2);
}

.education-item {
  display: flex;
  gap: 20px;
  background-color: white;
  padding: 20px;
  border-radius: 12px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
  transition: all 0.3s ease;
  position: relative;
}

.education-item:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
}

/* 时间点样式 */
.education-item::before {
  content: '';
  position: absolute;
  left: -28px;
  top: 25px;
  width: 16px;
  height: 16px;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  border: 4px solid white;
  border-radius: 50%;
  z-index: 1;
}

.education-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  margin-bottom: 12px;
  width: 100%;
}

.education-info {
  flex: 1;
}

.degree {
  font-size: 1.2rem;
  font-weight: 600;
  margin-bottom: 8px;
  color: #333;
}

.school {
  font-size: 1rem;
  color: #667eea;
  margin-bottom: 8px;
  font-weight: 500;
}

.period {
  font-size: 0.9rem;
  color: #999;
  font-weight: 500;
  background-color: #f0f0f0;
  padding: 4px 12px;
  border-radius: 12px;
  align-self: flex-start;
}

.description {
  font-size: 1rem;
  color: #555;
  line-height: 1.6;
  width: 100%;
}

/* 响应式设计 */
@media (max-width: 768px) {
  .education-list::before {
    left: 15px;
  }
  
  .education-item::before {
    left: -23px;
  }
  
  .education-item {
    padding: 15px;
  }
  
  .education-header {
    flex-direction: column;
    gap: 10px;
  }
  
  .period {
    align-self: flex-start;
  }
}
</style>
