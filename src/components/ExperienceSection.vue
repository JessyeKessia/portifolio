<template>
  <section id="experiencia" class="exp-section">
    <div class="section-inner">
      <div class="section-header">
        <span class="section-tag">Trajetória</span>
        <h2 class="section-title">Experiência <span class="gradient-text">Profissional</span></h2>
        <p class="section-desc">Empresas onde desenvolvi soluções reais e cresci como desenvolvedora.</p>
      </div>

      <div class="timeline">
        <div v-for="(job, index) in jobs" :key="index" class="timeline-item">
          <div class="timeline-left">
            <div class="company-logo" :style="{ background: job.color }">
              {{ job.initials }}
            </div>
            <div v-if="index < jobs.length - 1" class="timeline-line"></div>
          </div>
          <div class="timeline-card">
            <div class="card-header">
              <div>
                <h3 class="job-title">{{ job.title }}</h3>
                <span class="company-name">{{ job.company }}</span>
              </div>
              <div class="job-meta">
                <span class="job-period">{{ job.period }}</span>
                <span class="job-type" :class="job.type">{{ job.typeText }}</span>
              </div>
            </div>
            <p class="job-desc">{{ job.desc }}</p>
            <div class="job-tags">
              <span v-for="tag in job.tags" :key="tag" class="tag">{{ tag }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const jobs = [
  {
    company: 'CODATA',
    initials: 'CO',
    color: 'linear-gradient(135deg, #a78bfa, #e879f9)',
    title: 'Desenvolvedora Full Stack',
    period: '2026 — Presente',
    type: 'contract',
    typeText: 'Estágio',
    desc: 'Desenvolvimento e manutenção de sistemas governamentais com Java no back-end e TypeScript/JavaScript no front-end. Integração com banco de dados PostgreSQL e participação em equipes multidisciplinares.',
    tags: ['Java', 'TypeScript', 'JavaScript', 'PostgreSQL', 'Spring Boot', 'Git'],
  },
  {
    company: 'Compass UOL',
    initials: 'CU',
    color: 'linear-gradient(135deg, #f97316, #fb923c)',
    title: 'Desenvolvedora de ML/IA',
    period: '2024 — 2025',
    type: 'full',
    typeText: 'Estágio → Desenvolvedora',
    desc: 'Iniciei como estagiária e evoluí para desenvolvedora. Desenvolvimento de aplicações com foco em Machine Learning e IA, integração com serviços de Cloud (AWS), trabalhei com microsserviços e metodologias ágeis.',
    tags: ['AWS', 'Python', 'Flask', 'Azure', 'Scrum', 'Git', 'MongoDB'],
  },
]
</script>

<style scoped>
.exp-section {
  padding: 100px 32px;
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

.timeline {
  max-width: 800px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: 0;
}

.timeline-item {
  display: flex;
  gap: 24px;
  align-items: flex-start;
}

.timeline-left {
  display: flex;
  flex-direction: column;
  align-items: center;
  flex-shrink: 0;
}

.company-logo {
  width: 52px;
  height: 52px;
  border-radius: 14px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 16px;
  font-weight: 700;
  color: #fff;
  flex-shrink: 0;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
}

.timeline-line {
  width: 2px;
  flex: 1;
  min-height: 40px;
  background: linear-gradient(to bottom, var(--border), transparent);
  margin: 8px 0;
}

.timeline-card {
  flex: 1;
  background: var(--bg-card);
  border: 1px solid var(--border);
  border-radius: 16px;
  padding: 28px;
  margin-bottom: 32px;
  transition: border-color 0.2s, transform 0.2s;
}

.timeline-card:hover {
  border-color: rgba(192, 132, 252, 0.4);
  transform: translateY(-2px);
}

.card-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  gap: 16px;
  margin-bottom: 16px;
  flex-wrap: wrap;
}

.job-title {
  font-size: 18px;
  font-weight: 600;
  color: var(--text-h);
  margin-bottom: 4px;
}

.company-name {
  font-size: 14px;
  font-weight: 600;
  color: var(--accent);
}

.job-meta {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  gap: 6px;
}

.job-period {
  font-size: 13px;
  color: var(--text);
  font-weight: 500;
}

.job-type {
  font-size: 11px;
  font-weight: 600;
  padding: 3px 10px;
  border-radius: 100px;
  letter-spacing: 0.3px;
}

.job-type.contract {
  background: rgba(232, 121, 249, 0.12);
  color: #e879f9;
  border: 1px solid rgba(232, 121, 249, 0.3);
}

.job-type.full {
  background: rgba(192, 132, 252, 0.12);
  color: #c084fc;
  border: 1px solid rgba(192, 132, 252, 0.3);
}

.job-desc {
  font-size: 14px;
  line-height: 1.7;
  color: var(--text);
  margin-bottom: 20px;
}

.job-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.tag {
  font-size: 12px;
  font-weight: 500;
  padding: 4px 12px;
  border-radius: 6px;
  background: var(--bg-card2);
  color: var(--text-h);
  border: 1px solid var(--border);
  transition: all 0.2s;
}

.tag:hover {
  border-color: #e879f9;
  color: #e879f9;
}

@media (max-width: 768px) {
  .exp-section { padding: 64px 20px; }
  .timeline-left { display: none; }
  .timeline-item { flex-direction: column; }
  .card-header { flex-direction: column; }
  .job-meta { align-items: flex-start; }
  .timeline-card { margin-bottom: 20px; }
}
</style>
