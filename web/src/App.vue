<script setup lang="ts">
</script>

<template>
  <div class="app-container">
    <router-view />
    <footer class="footer">
      <p>© 2025 张三. All rights reserved.</p>
    </footer>
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  background: linear-gradient(135deg, #667eea10 0%, #764ba210 100%);
  color: #333;
  line-height: 1.6;
  overflow-x: hidden;
}

.app-container {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

/* 全局动画效果 */
@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

@keyframes slideInUp {
  from {
    opacity: 0;
    transform: translateY(50px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes pulse {
  0%, 100% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.05);
  }
}

/* 平滑滚动 */
html {
  scroll-behavior: smooth;
}

/* 全局链接样式 */
a {
  text-decoration: none;
  transition: all 0.3s ease;
}

/* 全局按钮样式 */
button {
  cursor: pointer;
  transition: all 0.3s ease;
}

/* 全局卡片阴影效果 */
.card {
  background-color: white;
  border-radius: 12px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
  transition: all 0.3s ease;
}

.card:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
}

/* 页脚样式 */
.footer {
  text-align: center;
  padding: 20px;
  margin-top: 50px;
  background-color: white;
  color: #666;
  font-size: 0.9rem;
  border-top: 1px solid #eee;
}

/* 响应式设计 */
@media (max-width: 768px) {
  body {
    font-size: 14px;
  }
}
</style>

