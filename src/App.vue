<script setup>
import ProductCard from './components/ProductCard.vue'

const webApps = [
  {
    title: 'FocusTree',
    description: 'Pomodoro-таймер с растущим пиксельным деревом. Чем дольше фокус - тем больше дерево.',
    tags: ['Vue 3', 'PWA', 'Продуктивность'],
    emoji: '🌳',
    link: 'https://pomodoro-tree-cb9a.vercel.app/',
    color: '#22c55e',
  },
  {
    title: 'Habit Tracker',
    description: 'Трекер привычек с тепловой картой и стриками.',
    tags: ['Vue 3', 'PWA', 'Здоровье'],
    emoji: '🔥',
    link: 'https://habit-tracker-tau-lake.vercel.app/',
    color: '#f97316',
  },
  {
    title: 'Positivus',
    description: 'Лендинг маркетингового агентства. Вёрстка по макету, адаптив.',
    tags: ['Лендинг', 'UI/UX'],
    emoji: '🚀',
    link: 'https://evangel57.github.io/st-positivus/index.html',
    color: '#a855f7',
  },
  {
    title: 'Nature Travel',
    description: 'Лендинг турагентства. Параллакс, анимации при скролле, адаптивная навигация.',
    tags: ['Лендинг', 'Параллакс', 'Анимации'],
    emoji: '🌿',
    link: 'https://evangel57.github.io/n1/',
    color: '#16a34a',
  },
  {
    title: 'Drafts',
    description: 'Редактор черновиков для писателей с подсчётом слов.',
    tags: ['Приложение', 'Заметки'],
    emoji: '✍️',
    link: 'https://evangel57.github.io/NoteApp/',
    color: '#0ea5e9',
  },
]

const designProjects = [
  {
    title: 'Parallax Slider',
    description: 'Параллакс-слайдер с многослойной анимацией в Figma.',
    tags: ['Анимация', 'Параллакс', 'Figma'],
    image: '/parallax.gif',
    link: 'https://www.figma.com/proto/6YNyEeLMFWQv1NHlN1wpFN/?node-id=56-143&t=R6tAwWUZdXm0MtVu-1',
  },
  {
    title: 'Fruit Cider',
    description: 'Концепт лендинга для напитков. Анимация в Figma.',
    tags: ['Анимация', 'Лендинг', 'Figma'],
    image: '/fruit-cider.gif',
    link: 'https://www.figma.com/proto/6YNyEeLMFWQv1NHlN1wpFN/?node-id=3011-1671&t=R6tAwWUZdXm0MtVu-1',
  },
  {
    title: 'College Portfolio',
    description: 'Макет портфолио для студентов колледжа. Работал в системе колледжа около года, ~100 студентов вели профили.',
    tags: ['Портфолио', 'Брендинг', 'Figma'],
    image: '/college-portfolio.png',
    link: 'https://www.figma.com/design/B11exBm4dVx9tGmmIbIIAI/',
  },
]

const experience = [
  {
    company: 'Artlogo',
    role: 'Фронтенд-разработчик',
    period: '1.5 года',
    description: 'Интернет-магазин на Shopify. Делала шаблоны визиток и соцсетей, потом собирала генераторы для них.',
    tags: ['Shopify', 'E-commerce', 'Шаблоны'],
  },
  {
    company: 'mpspace',
    role: 'Фронтенд-разработчик',
    period: '1 год',
    description: 'Платформа аналитики для селлеров маркетплейсов. Делала отчёты и графики.',
    tags: ['Vue 3', 'Аналитика', 'Дашборд'],
  },
]
</script>

<template>
  <div class="page">
    <header class="header">
      <div class="header-inner">
        <div class="logo">eva<span class="logo-dot">.</span></div>
        <nav class="nav">
          <a href="https://t.me/EvaAverto" target="_blank" rel="noopener" class="nav-link">Связаться</a>
        </nav>
      </div>
    </header>

    <main class="main">
      <section class="hero">
        <div class="hero-badge">Веб-разработка ✦</div>
        <h1 class="hero-title">
          Идея, дизайн,<br>
          <span class="hero-accent">код.</span>
        </h1>
        <p class="hero-sub">
          Веб-дизайн и фронтенд-разработка.
        </p>
      </section>

      <!-- ========== WEB APPS ========== -->
      <h2 class="section-title">Веб-приложения</h2>
      <section class="products">
        <ProductCard
          v-for="p in webApps"
          :key="p.title"
          v-bind="p"
        />
      </section>

      <!-- ========== DESIGN & ANIMATION ========== -->
      <h2 class="section-title">Дизайн и анимация</h2>
      <section class="products">
        <ProductCard
          v-for="p in designProjects"
          :key="p.title"
          v-bind="p"
        />
      </section>

      <!-- ========== WORK EXPERIENCE ========== -->
      <h2 class="section-title">Опыт работы</h2>
      <section class="experience">
        <div v-for="job in experience" :key="job.company" class="job-card">
          <div class="job-header">
            <div>
              <h3 class="job-company">{{ job.company }}</h3>
              <p class="job-role">{{ job.role }}</p>
            </div>
            <span class="job-period">{{ job.period }}</span>
          </div>
          <p class="job-desc">{{ job.description }}</p>
          <div class="job-tags">
            <span v-for="tag in job.tags" :key="tag" class="tag">{{ tag }}</span>
          </div>
        </div>
      </section>
    </main>

    <footer class="footer">
      <a href="https://t.me/EvaAverto" target="_blank" rel="noopener" class="footer-link">@EvaAverto</a>
    </footer>
  </div>
</template>

<style scoped>
.page {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

/* ========== HEADER ========== */
.header {
  position: sticky;
  top: 0;
  z-index: 10;
  background: rgba(250, 250, 249, 0.85);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid var(--border);
}

.header-inner {
  max-width: 900px;
  margin: 0 auto;
  padding: 0 32px;
  height: 60px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.logo {
  font-size: 22px;
  font-weight: 800;
  letter-spacing: -0.5px;
  color: var(--text);
}

.logo-dot {
  color: var(--accent);
}

.nav-link {
  font-size: 14px;
  font-weight: 500;
  color: var(--text2);
  text-decoration: none;
  padding: 6px 14px;
  border-radius: 100px;
  border: 1px solid var(--border);
  transition: all 0.2s;
}

.nav-link:hover {
  color: var(--accent);
  border-color: var(--accent);
  background: var(--accent-light);
}

/* ========== MAIN ========== */
.main {
  flex: 1;
  max-width: 900px;
  margin: 0 auto;
  padding: 0 32px 80px;
  width: 100%;
}

/* ========== HERO ========== */
.hero {
  padding: 80px 0 64px;
  text-align: center;
}

.hero-badge {
  display: inline-block;
  font-size: 12px;
  font-weight: 600;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: var(--accent);
  background: var(--accent-light);
  border: 1px solid rgba(249, 115, 22, 0.2);
  border-radius: 100px;
  padding: 4px 14px;
  margin-bottom: 28px;
}

.hero-title {
  font-size: clamp(40px, 6vw, 68px);
  font-weight: 800;
  letter-spacing: -2px;
  line-height: 1.08;
  color: var(--text);
  margin-bottom: 20px;
}

.hero-accent {
  color: var(--accent);
}

.hero-sub {
  font-size: 17px;
  color: var(--text2);
  line-height: 1.65;
  max-width: 460px;
  margin: 0 auto;
}

/* ========== SECTIONS ========== */
.section-title {
  font-size: 24px;
  font-weight: 700;
  letter-spacing: -0.5px;
  color: var(--text);
  margin-top: 56px;
  margin-bottom: 24px;
}

/* ========== PRODUCTS ========== */
.products {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 24px;
}

/* ========== EXPERIENCE ========== */
.experience {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.job-card {
  background: var(--bg2);
  border: 1px solid var(--border);
  border-radius: 20px;
  padding: 24px 28px;
  box-shadow: var(--shadow-sm);
}

.job-header {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  margin-bottom: 10px;
}

.job-company {
  font-size: 18px;
  font-weight: 700;
  color: var(--text);
  letter-spacing: -0.3px;
}

.job-role {
  font-size: 14px;
  color: var(--accent);
  font-weight: 500;
  margin-top: 2px;
}

.job-period {
  font-size: 13px;
  color: var(--text3);
  font-weight: 500;
  white-space: nowrap;
}

.job-desc {
  font-size: 14px;
  color: var(--text2);
  line-height: 1.55;
  margin-bottom: 12px;
}

.job-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
}

.job-tags .tag {
  font-size: 12px;
  font-weight: 500;
  padding: 3px 10px;
  border-radius: 100px;
  background: var(--bg3);
  color: var(--text2);
  border: 1px solid var(--border);
}

/* ========== FOOTER ========== */
.footer {
  border-top: 1px solid var(--border);
  padding: 20px 32px;
  text-align: center;
  font-size: 13px;
  color: var(--text3);
}

.footer-link {
  color: var(--text3);
  text-decoration: none;
  transition: color 0.2s;
}

.footer-link:hover {
  color: var(--accent);
}

/* ========== RESPONSIVE ========== */
@media (max-width: 600px) {
  .header-inner { padding: 0 20px; }
  .main { padding: 0 20px 60px; }
  .hero { padding: 52px 0 44px; }
  .hero-title { letter-spacing: -1px; }
  .products { grid-template-columns: 1fr; }
}
</style>
