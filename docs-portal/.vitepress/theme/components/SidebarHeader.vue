<script setup lang="ts">
import { withBase, useData } from 'vitepress'

const { lang } = useData()
const isVi = computed(() => lang.value === 'vi-VN' || lang.value === 'vi')
import { computed } from 'vue'
</script>

<template>
  <div class="synx-sidebar-header">
    <div class="synx-sidebar-brand">
      <img :src="withBase('/logo.png')" alt="SynaptiX IDE Logo" class="synx-sidebar-logo" />
      <div class="synx-sidebar-title-group">
        <span class="synx-sidebar-product-name">SynaptiX IDE</span>
        <span class="synx-sidebar-subtitle">{{ isVi ? 'Tài Liệu Kỹ Thuật' : 'Engineering Wiki' }}</span>
      </div>
    </div>
    
    <div class="synx-sidebar-meta">
      <a 
        href="https://github.com/hoanv-synaptix/SynaptiX-IDE-Releases/releases/tag/v2.11.4" 
        target="_blank" 
        rel="noopener noreferrer"
        class="synx-version-badge"
        title="Official GitHub Release v2.11.4"
      >
        <span class="synx-status-dot"></span>
        <span class="synx-version-text">v2.11.4 [STABLE]</span>
        <svg class="synx-external-icon" viewBox="0 0 24 24" width="12" height="12">
          <path fill="currentColor" d="M14 3v2h3.59l-9.83 9.83 1.41 1.41L19 6.41V10h2V3m-2 16H5V5h7V3H5a2 2 0 0 0-2 2v14a2 2 0 0 0 2 2h14a2 2 0 0 0 2-2v-7h-2v7Z"/>
        </svg>
      </a>
    </div>
  </div>
</template>

<style scoped>
.synx-sidebar-header {
  padding: 18px 18px 14px 18px;
  border-bottom: 1px solid var(--vp-c-divider);
  margin-bottom: 8px;
  background-color: var(--vp-sidebar-bg-color);
}

.synx-sidebar-brand {
  display: flex;
  align-items: center;
  gap: 12px;
}

.synx-sidebar-logo {
  width: 34px;
  height: 34px;
  object-fit: contain;
  flex-shrink: 0;
  border-radius: 4px;
}

.synx-sidebar-title-group {
  display: flex;
  flex-direction: column;
}

.synx-sidebar-product-name {
  font-size: 0.98rem;
  font-weight: 700;
  color: var(--vp-c-text-1);
  letter-spacing: -0.01em;
  line-height: 1.25;
}

.synx-sidebar-subtitle {
  font-size: 0.72rem;
  color: var(--vp-c-text-3);
  text-transform: uppercase;
  letter-spacing: 0.05em;
  font-weight: 600;
  margin-top: 1px;
}

.synx-sidebar-meta {
  margin-top: 10px;
  display: flex;
  align-items: center;
}

.synx-version-badge {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 3px 9px;
  border-radius: 4px;
  background-color: var(--vp-c-bg-soft);
  border: 1px solid var(--vp-c-divider);
  font-family: var(--vp-font-family-mono);
  font-size: 0.73rem;
  font-weight: 600;
  color: var(--vp-c-text-2);
  text-decoration: none !important;
  transition: all 0.16s ease;
}

.synx-version-badge:hover {
  background-color: var(--vp-c-brand-soft);
  color: var(--vp-c-brand-1);
  border-color: var(--vp-c-brand-1);
}

.synx-status-dot {
  width: 6px;
  height: 6px;
  border-radius: 50%;
  background-color: #107c41; /* Operational Green */
  box-shadow: 0 0 6px rgba(16, 124, 65, 0.4);
}

.synx-version-text {
  letter-spacing: 0.02em;
}

.synx-external-icon {
  opacity: 0.65;
}
</style>
