<script setup lang="ts">
import { onMounted, onUnmounted, ref } from 'vue'

const props = defineProps<{
  id: string
  code: string
}>()

const svgHtml = ref<string>('')
const errorText = ref<string>('')
let observer: MutationObserver | null = null

async function renderDiagram() {
  try {
    const { default: mermaid } = await import('mermaid')
    const isDark = document.documentElement.classList.contains('dark')
    mermaid.initialize({
      startOnLoad: false,
      securityLevel: 'loose',
      theme: isDark ? 'dark' : 'default',
      fontFamily: 'Segoe UI, Inter, system-ui, sans-serif'
    })
    const decoded = decodeURIComponent(props.code)
    const uniqueId = `${props.id}-${Math.random().toString(36).slice(2, 8)}`
    const { svg } = await mermaid.render(uniqueId, decoded)
    svgHtml.value = svg
    errorText.value = ''
  } catch (err) {
    errorText.value = err instanceof Error ? err.message : String(err)
  }
}

onMounted(async () => {
  await renderDiagram()
  observer = new MutationObserver(() => {
    void renderDiagram()
  })
  observer.observe(document.documentElement, {
    attributes: true,
    attributeFilter: ['class']
  })
})

onUnmounted(() => {
  observer?.disconnect()
})
</script>

<template>
  <div class="synx-mermaid-container">
    <div v-if="svgHtml" class="synx-mermaid-svg" v-html="svgHtml" />
    <pre v-else-if="errorText" class="synx-mermaid-fallback">{{ decodeURIComponent(code) }}</pre>
    <div v-else class="synx-mermaid-loading">Rendering diagram…</div>
  </div>
</template>
