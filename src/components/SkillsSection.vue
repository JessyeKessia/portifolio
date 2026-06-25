<template>
  <section id="skills" class="skills-section">
    <div class="section-inner">
      <div class="section-header">
        <span class="section-tag">Tecnologias</span>
        <h2 class="section-title">Minhas <span class="gradient-text">Skills</span></h2>
        <p class="section-desc">Tecnologias e ferramentas que utilizo no dia a dia para construir soluções completas.</p>
      </div>

      <div class="skills-grid">
        <div class="skill-group">
          <div class="group-header">
            <span class="group-icon">🚀</span>
            <h3>Linguagens de Programação</h3>
          </div>
          <div class="skills-list">
            <div v-for="skill in languages" :key="skill.name" class="skill-card">
              <span class="skill-emoji">{{ skill.icon }}</span>
              <div class="skill-info">
                <span class="skill-name">{{ skill.name }}</span>
                <span class="skill-level" :class="skill.level">{{ skill.levelText }}</span>
              </div>
            </div>
          </div>
        </div>

        <div class="skill-group">
          <div class="group-header">
            <span class="group-icon">☁️</span>
            <h3>Cloud & DevOps</h3>
          </div>
          <div class="skills-list">
            <div v-for="skill in cloud" :key="skill.name" class="skill-card">
              <span class="skill-emoji">{{ skill.icon }}</span>
              <div class="skill-info">
                <span class="skill-name">{{ skill.name }}</span>
                <span class="skill-level" :class="skill.level">{{ skill.levelText }}</span>
              </div>
            </div>
          </div>
        </div>

        <div class="skill-group">
          <div class="group-header">
            <span class="group-icon">🎲</span>
            <h3>Bancos de Dados</h3>
          </div>
          <div class="skills-list">
            <div v-for="skill in databases" :key="skill.name" class="skill-card">
              <span class="skill-emoji">{{ skill.icon }}</span>
              <div class="skill-info">
                <span class="skill-name">{{ skill.name }}</span>
                <span class="skill-level" :class="skill.level">{{ skill.levelText }}</span>
              </div>
            </div>
          </div>
        </div>

        <div class="skill-group">
          <div class="group-header">
            <span class="group-icon">🛠️</span>
            <h3>Frameworks & Ferramentas</h3>
          </div>
          <div class="skills-list">
            <div v-for="skill in tools" :key="skill.name" class="skill-card">
              <span class="skill-emoji">{{ skill.icon }}</span>
              <div class="skill-info">
                <span class="skill-name">{{ skill.name }}</span>
                <span class="skill-level" :class="skill.level">{{ skill.levelText }}</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const languages = [
  { name: 'Java', icon: '☕', level: 'advanced', levelText: 'Avançado' },
  { name: 'Python', icon: '🐍', level: 'advanced', levelText: 'Avançado' },
  { name: 'JavaScript', icon: '🟨', level: 'advanced', levelText: 'Avançado' },
  { name: 'TypeScript', icon: '🟦', level: 'intermediate', levelText: 'Intermediário' },
]

const cloud = [
  { name: 'Microsoft Azure', icon: '🔷', level: 'intermediate', levelText: 'Intermediário' },
  { name: 'AWS', icon: '🟠', level: 'intermediate', levelText: 'Intermediário' },
  { name: 'Docker', icon: '🐳', level: 'intermediate', levelText: 'Intermediário' },
]

const databases = [
  { name: 'PostgreSQL', icon: '🐘', level: 'advanced', levelText: 'Avançado' },
  { name: 'MongoDB', icon: '🍃', level: 'intermediate', levelText: 'Intermediário' },
  { name: 'MySQL', icon: '🐬', level: 'advanced', levelText: 'Avançado' },
]

const tools = [
  { name: 'Spring Boot', icon: '🌱', level: 'advanced', levelText: 'Avançado' },
  { name: 'Vue.js', icon: '💚', level: 'intermediate', levelText: 'Intermediário' },
  { name: 'Git & GitHub', icon: '🐙', level: 'advanced', levelText: 'Avançado' },
  { name: 'REST APIs', icon: '🔗', level: 'advanced', levelText: 'Avançado' },
]
</script>

<style scoped>
.skills-section {
  padding: 100px 32px;
  background: var(--bg-card);
  border-top: 1px solid var(--border);
  border-bottom: 1px solid var(--border);
}

.section-inner {
  max-width: 1100px;
  margin: 0 auto;
}

.section-header {
  text-align: center;
  margin-bottom: 64px;
}

.section-tag {
  display: inline-block;
  background: var(--accent-light);
  color: var(--accent);
  padding: 5px 14px;
  border-radius: 100px;
  font-size: 12px;
  font-weight: 600;
  letter-spacing: 0.5px;
  text-transform: uppercase;
  margin-bottom: 16px;
  border: 1px solid rgba(124, 58, 237, 0.3);
}

.section-title {
  font-size: clamp(28px, 4vw, 44px);
  font-weight: 700;
  color: var(--text-h);
  letter-spacing: -1px;
  margin-bottom: 14px;
}

.gradient-text {
  background: linear-gradient(135deg, #c084fc, #e879f9, #f9a8d4);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.section-desc {
  color: var(--text);
  font-size: 16px;
  line-height: 1.6;
  max-width: 520px;
  margin: 0 auto;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 24px;
}

.skill-group {
  background: var(--bg);
  border: 1px solid var(--border);
  border-radius: 16px;
  padding: 28px;
  transition: border-color 0.2s;
}

.skill-group:hover {
  border-color: rgba(192, 132, 252, 0.4);
}

.group-header {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-bottom: 20px;
  padding-bottom: 16px;
  border-bottom: 1px solid var(--border);
}

.group-icon {
  font-size: 20px;
}

.group-header h3 {
  font-size: 15px;
  font-weight: 600;
  color: var(--text-h);
}

.skills-list {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.skill-card {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 10px 14px;
  background: var(--bg-card);
  border-radius: 10px;
  border: 1px solid transparent;
  transition: all 0.2s;
  cursor: default;
}

.skill-card:hover {
  border-color: rgba(192, 132, 252, 0.35);
  background: var(--bg-card2);
  transform: translateX(4px);
}

.skill-emoji {
  font-size: 20px;
  flex-shrink: 0;
}

.skill-info {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex: 1;
}

.skill-name {
  font-size: 14px;
  font-weight: 500;
  color: var(--text-h);
}

.skill-level {
  font-size: 11px;
  font-weight: 600;
  padding: 3px 10px;
  border-radius: 100px;
  letter-spacing: 0.3px;
}

.skill-level.advanced {
  background: rgba(232, 121, 249, 0.12);
  color: #e879f9;
  border: 1px solid rgba(232, 121, 249, 0.3);
}

.skill-level.intermediate {
  background: rgba(192, 132, 252, 0.12);
  color: #c084fc;
  border: 1px solid rgba(192, 132, 252, 0.3);
}

@media (max-width: 768px) {
  .skills-section { padding: 64px 20px; }
  .skills-grid { grid-template-columns: 1fr; }
}
</style>
