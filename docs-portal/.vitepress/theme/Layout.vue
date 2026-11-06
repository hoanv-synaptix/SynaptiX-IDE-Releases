<script setup lang="ts">
import DefaultTheme from 'vitepress/theme'
import SidebarHeader from './components/SidebarHeader.vue'
import DocBreadcrumb from './components/DocBreadcrumb.vue'

const { Layout } = DefaultTheme
</script>

<template>
  <Layout>
    <template #sidebar-nav-before>
      <SidebarHeader />
    </template>
    <template #doc-before>
      <DocBreadcrumb />
    </template>
  </Layout>
</template>
