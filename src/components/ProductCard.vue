<script setup>
defineProps({
  title: String,
  description: String,
  tags: Array,
  emoji: String,
  link: String,
  color: { type: String, default: '#f97316' },
})
</script>

<template>
  <a :href="link" target="_blank" rel="noopener" class="card">
    <div class="card-preview" :style="{ '--card-color': color }">
      <span class="card-emoji">{{ emoji }}</span>
      <div class="card-glow" />
    </div>
    <div class="card-body">
      <div class="card-top">
        <h3 class="card-title">{{ title }}</h3>
        <span class="card-arrow">↗</span>
      </div>
      <p class="card-desc">{{ description }}</p>
      <div class="card-tags">
        <span v-for="tag in tags" :key="tag" class="tag">{{ tag }}</span>
      </div>
    </div>
  </a>
</template>

<style scoped>
.card {
  display: flex;
  flex-direction: column;
  background: var(--bg2);
  border: 1px solid var(--border);
  border-radius: 20px;
  overflow: hidden;
  text-decoration: none;
  color: inherit;
  box-shadow: var(--shadow-sm);
  transition: transform 0.35s cubic-bezier(0.34, 1.56, 0.64, 1),
              box-shadow 0.35s ease,
              border-color 0.25s ease;
  cursor: pointer;
}

.card:hover {
  transform: translateY(-8px) scale(1.02);
  box-shadow: var(--shadow-lg);
  border-color: rgba(249, 115, 22, 0.2);
}

.card-preview {
  position: relative;
  height: 180px;
  background: linear-gradient(135deg, var(--card-color) 0%, color-mix(in srgb, var(--card-color) 60%, #fff) 100%);
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}

.card-emoji {
  font-size: 64px;
  position: relative;
  z-index: 1;
  transition: transform 0.35s cubic-bezier(0.34, 1.56, 0.64, 1);
  filter: drop-shadow(0 4px 12px rgba(0,0,0,0.15));
}

.card:hover .card-emoji {
  transform: scale(1.15) translateY(-4px);
}

.card-glow {
  position: absolute;
  inset: 0;
  background: radial-gradient(ellipse at 50% 120%, rgba(255,255,255,0.4) 0%, transparent 65%);
  opacity: 0;
  transition: opacity 0.35s ease;
}

.card:hover .card-glow {
  opacity: 1;
}

.card-body {
  padding: 20px 22px 22px;
  display: flex;
  flex-direction: column;
  gap: 8px;
  flex: 1;
}

.card-top {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.card-title {
  font-size: 18px;
  font-weight: 700;
  letter-spacing: -0.3px;
  color: var(--text);
}

.card-arrow {
  font-size: 18px;
  color: var(--text3);
  transition: color 0.2s ease, transform 0.25s ease;
}

.card:hover .card-arrow {
  color: var(--accent);
  transform: translate(2px, -2px);
}

.card-desc {
  font-size: 14px;
  color: var(--text2);
  line-height: 1.55;
}

.card-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
  margin-top: 4px;
}

.tag {
  font-size: 12px;
  font-weight: 500;
  padding: 3px 10px;
  border-radius: 100px;
  background: var(--bg3);
  color: var(--text2);
  border: 1px solid var(--border);
}
</style>
