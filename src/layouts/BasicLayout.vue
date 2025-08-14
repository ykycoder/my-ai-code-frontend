<template>
  <a-layout class="layout">
    <GlobalHeader />
    <a-layout-content class="content">
      <router-view />
    </a-layout-content>
    <GlobalFooter />
  </a-layout>
</template>

<script setup lang="ts">
import GlobalHeader from '@/components/GlobalHeader.vue'
import GlobalFooter from '@/components/GlobalFooter.vue'
</script>

<style scoped>
.layout {
  min-height: 100vh;
}

.content {
  padding: 24px;
  flex: 1;
  background: #fff;
}
</style>