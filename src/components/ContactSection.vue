<template>
  <section id="contato" class="contact-section">
    <div class="section-inner">
      <div class="contact-card">
        <div class="contact-glow"></div>
        <span class="section-tag">Contato</span>
        <h2 class="contact-title">Vamos <span class="gradient-text">trabalhar juntos?</span></h2>
        <p class="contact-desc">
          Estou aberta a novas oportunidades e projetos interessantes. 
          Se quiser bater um papo, é só me chamar!
        </p>
        <div class="contact-links">
          <a
            v-for="link in links"
            :key="link.label"
            :href="link.href"
            target="_blank"
            rel="noopener"
            class="contact-btn"
          >
            <span class="link-icon">{{ link.icon }}</span>
            <span>{{ link.label }}</span>
          </a>
        </div>
      </div>
    </div>
    <footer class="footer">
      <p>Desenvolvido por <strong>Jessye Késsia</strong> — {{ new Date().getFullYear() }}</p>
    </footer>
  </section>
</template>

<script setup lang="ts">
const links = [
  {
    label: 'LinkedIn',
    icon: '💼',
    href: 'https://linkedin.com/in/jessye-kessia',
  },
  {
    label: 'GitHub',
    icon: '🐙',
    href: 'https://github.com/JessyeKessia',
  },
  {
    label: 'E-mail',
    icon: '✉️',
    href: 'mailto:jessye@email.com',
  },
]
</script>

<style scoped>
.contact-section {
  padding: 100px 32px 0;
  background: var(--bg-card);
  border-top: 1px solid var(--border);
}

.section-inner {
  max-width: 1100px;
  margin: 0 auto;
}

.contact-card {
  position: relative;
  overflow: hidden;
  background: var(--bg);
  border: 1px solid var(--border);
  border-radius: 24px;
  padding: 72px 48px;
  text-align: center;
  transition: border-color 0.3s;
}

.contact-card:hover {
  border-color: rgba(124, 58, 237, 0.4);
}

.contact-glow {
  position: absolute;
  top: -60px;
  left: 50%;
  transform: translateX(-50%);
  width: 400px;
  height: 200px;
  background: radial-gradient(ellipse, rgba(232, 121, 249, 0.18) 0%, rgba(192, 132, 252, 0.08) 50%, transparent 70%);
  pointer-events: none;
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
  margin-bottom: 20px;
  border: 1px solid rgba(124, 58, 237, 0.3);
}

.contact-title {
  font-size: clamp(28px, 4vw, 48px);
  font-weight: 700;
  color: var(--text-h);
  letter-spacing: -1.2px;
  margin-bottom: 16px;
  line-height: 1.15;
}

.gradient-text {
  background: linear-gradient(135deg, #c084fc, #e879f9, #f9a8d4);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.contact-desc {
  font-size: 16px;
  color: var(--text);
  line-height: 1.7;
  max-width: 460px;
  margin: 0 auto 40px;
}

.contact-links {
  display: flex;
  justify-content: center;
  gap: 16px;
  flex-wrap: wrap;
}

.contact-btn {
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 13px 28px;
  border-radius: 12px;
  text-decoration: none;
  font-size: 15px;
  font-weight: 600;
  border: 1px solid var(--border);
  color: var(--text-h);
  background: var(--bg-card);
  transition: all 0.2s;
}

.contact-btn:hover {
  border-color: #e879f9;
  color: #e879f9;
  transform: translateY(-2px);
  box-shadow: 0 4px 20px rgba(232, 121, 249, 0.2);
}

.link-icon {
  font-size: 18px;
}

.footer {
  max-width: 1100px;
  margin: 0 auto;
  padding: 32px 0;
  text-align: center;
  font-size: 13px;
  color: var(--text);
  border-top: 1px solid var(--border);
  margin-top: 48px;
}

.footer strong {
  color: var(--text-h);
}

@media (max-width: 768px) {
  .contact-section { padding: 64px 20px 0; }
  .contact-card { padding: 48px 24px; }
}
</style>
