<script setup lang="ts">
const currentDirections = [
  {
    id: 1,
    title: '大模型应用开发',
    description: '研究大模型在前端开发中的应用，包括AI辅助编程、智能代码生成等'
  },
  {
    id: 2,
    title: '跨端开发技术',
    description: '深入研究跨端开发框架，如Taro、UniApp等，实现一套代码多端运行'
  },
  {
    id: 3,
    title: '性能优化',
    description: '专注于前端性能优化，包括加载优化、渲染优化、运行时优化等'
  },
  {
    id: 4,
    title: 'Web3.0技术',
    description: '学习Web3.0相关技术，如区块链、智能合约、去中心化应用等'
  }
]
</script>

<template>
  <div class="current-direction">
    <div class="direction-list">
      <div v-for="direction in currentDirections" :key="direction.id" class="direction-item">
        <h3 class="direction-title">{{ direction.title }}</h3>
        <p class="direction-description">{{ direction.description }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.current-direction {
  background-color: #f8f9fa;
  padding: 25px;
  border-radius: 12px;
}

.direction-list {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 25px;
}

.direction-item {
  background-color: white;
  padding: 25px;
  border-radius: 12px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
  border: 2px solid transparent;
}

.direction-item::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  z-index: -1;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.direction-item:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
  border-color: #667eea;
}

.direction-item:hover::before {
  opacity: 0.05;
}

.direction-title {
  font-size: 1.3rem;
  font-weight: 600;
  margin-bottom: 15px;
  color: #333;
  display: flex;
  align-items: center;
  gap: 10px;
}

.direction-title::before {
  content: '🚀';
  font-size: 1.5rem;
}

.direction-description {
  font-size: 1rem;
  color: #555;
  line-height: 1.7;
  margin: 0;
}

/* 响应式设计 */
@media (max-width: 768px) {
  .direction-list {
    grid-template-columns: 1fr;
  }
  
  .direction-item {
    padding: 20px;
  }
}
</style>
