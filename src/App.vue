<script setup>
import ProductCard from './components/ProductCard.vue'

const products = [
  {
    title: 'FocusTree',
    description: 'Pomodoro timer with a growing pixel art tree. Stay focused, watch your tree bloom.',
    tags: ['Productivity', 'Pomodoro', 'PWA'],
    emoji: '🌳',
    link: 'https://pomodoro-tree-cb9a.vercel.app/',
    color: '#22c55e',
  },
  {
    title: 'Habit Tracker',
    description: 'Build habits that stick. Visual heatmap, streaks, and offline support.',
    tags: ['Habits', 'Wellness', 'PWA'],
    emoji: '🔥',
    link: 'https://habit-tracker-tau-lake.vercel.app/',
    color: '#f97316',
  },
  {
    title: 'Positivus',
    description: 'Modern marketing agency landing page. Clean layout, bold typography, smooth sections.',
    tags: ['Landing', 'UI/UX', 'Payments'],
    emoji: '🚀',
    link: 'https://evangel57.github.io/st-positivus/index.html',
    color: '#a855f7',
  },
  {
    title: 'Drafts',
    description: 'A writing app for those who think in drafts. Distraction-free, minimal, and built for writers.',
    tags: ['Writing', 'Notes', 'App'],
    emoji: '✍️',
    link: 'https://evangel57.github.io/NoteApp/',
    color: '#0ea5e9',
  },
]
</script>

<template>
  <div class="page">
    <header class="header">
      <div class="header-inner">
        <div class="logo">eva<span class="logo-dot">.</span></div>
        <nav class="nav">
          <a href="https://t.me/EvaAverto" target="_blank" rel="noopener" class="nav-link">Contact</a>
        </nav>
      </div>
    </header>

    <main class="main">
      <section class="hero">
        <div class="hero-badge">Mini Apps ✦</div>
        <h1 class="hero-title">
          Small apps,<br>
          <span class="hero-accent">big ideas.</span>
        </h1>
        <p class="hero-sub">
          A collection of focused web tools built with care.<br>
          Each one does one thing — and does it well.
        </p>
      </section>

      <section class="products">
        <ProductCard
          v-for="p in products"
          :key="p.title"
          v-bind="p"
        />
      </section>

      <section class="more">
        <div class="more-inner">
          <span class="more-icon">🚧</span>
          <p>More apps coming soon</p>
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

/* ========== PRODUCTS ========== */
.products {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 24px;
}

/* ========== MORE ========== */
.more {
  margin-top: 24px;
}

.more-inner {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  padding: 28px;
  border: 1.5px dashed var(--border);
  border-radius: 20px;
  color: var(--text3);
  font-size: 14px;
  font-weight: 500;
}

.more-icon {
  font-size: 20px;
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
