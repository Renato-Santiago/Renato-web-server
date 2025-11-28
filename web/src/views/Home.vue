<script setup lang="ts">
import PersonalInfo from '../components/PersonalInfo.vue'
import Education from '../components/Education.vue'
import Skills from '../components/Skills.vue'
import CurrentDirection from '../components/CurrentDirection.vue'
import Projects from '../components/Projects.vue'
</script>

<template>
  <div class="home-container">
    <header class="header">
      <h1 class="name">张三</h1>
      <p class="title">全栈开发工程师</p>
    </header>
    
    <nav class="nav">
      <router-link to="#personal-info" class="nav-item">个人信息</router-link>
      <router-link to="#education" class="nav-item">教育履历</router-link>
      <router-link to="#skills" class="nav-item">技术栈</router-link>
      <router-link to="#direction" class="nav-item">当前方向</router-link>
      <router-link to="#projects" class="nav-item">项目展示</router-link>
    </nav>
    
    <main class="main-content">
      <section id="personal-info" class="section">
        <h2 class="section-title">个人信息</h2>
        <PersonalInfo />
      </section>
      
      <section id="education" class="section">
        <h2 class="section-title">教育履历</h2>
        <Education />
      </section>
      
      <section id="skills" class="section">
        <h2 class="section-title">技术栈</h2>
        <Skills />
      </section>
      
      <section id="direction" class="section">
        <h2 class="section-title">当前技术方向</h2>
        <CurrentDirection />
      </section>
      
      <section id="projects" class="section">
        <h2 class="section-title">项目展示</h2>
        <Projects />
      </section>
    </main>
  </div>
</template>

<style scoped>
.home-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
}

.header {
  text-align: center;
  margin-bottom: 40px;
  padding: 40px 20px;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  border-radius: 12px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
  position: relative;
  z-index: 10;
  opacity: 1;
  transform: translateY(0);
}

.name {
  font-size: 3rem;
  margin-bottom: 15px;
  font-weight: 700;
  letter-spacing: -1px;
}

.title {
  font-size: 1.3rem;
  opacity: 0.9;
  font-weight: 400;
}

.nav {
  display: flex;
  justify-content: center;
  gap: 10px;
  margin-bottom: 50px;
  padding: 15px;
  background-color: white;
  border-radius: 12px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
  flex-wrap: wrap;
  position: relative;
  z-index: 10;
}

.nav-item {
  text-decoration: none;
  color: #666;
  font-weight: 500;
  padding: 10px 20px;
  border-radius: 25px;
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}

.nav-item::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(102, 126, 234, 0.1), transparent);
  transition: left 0.5s ease;
}

.nav-item:hover {
  background-color: #667eea;
  color: white;
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(102, 126, 234, 0.3);
}

.nav-item:hover::before {
  left: 100%;
}

.main-content {
  display: flex;
  flex-direction: column;
  gap: 30px;
  position: relative;
  z-index: 5;
}

.section {
  background-color: white;
  padding: 30px;
  border-radius: 12px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.05);
  transition: all 0.3s ease;
  opacity: 1;
  transform: translateY(0);
}

.section:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
}

.section-title {
  font-size: 1.8rem;
  margin-bottom: 25px;
  color: #333;
  font-weight: 600;
  position: relative;
  padding-bottom: 10px;
}

.section-title::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 60px;
  height: 4px;
  background: linear-gradient(90deg, #667eea 0%, #764ba2 100%);
  border-radius: 2px;
}

/* 动画效果 */
@keyframes fadeInDown {
  from {
    opacity: 0;
    transform: translateY(-30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* 响应式设计 */
@media (max-width: 768px) {
  .home-container {
    padding: 10px;
  }
  
  .name {
    font-size: 2rem;
  }
  
  .title {
    font-size: 1.1rem;
  }
  
  .nav {
    flex-direction: column;
    align-items: center;
    gap: 8px;
  }
  
  .nav-item {
    width: 100%;
    text-align: center;
  }
  
  .section {
    padding: 20px;
  }
}
</style>
