<template>
  <a-layout-header class="header">
    <div class="logo-container">
      <img alt="logo" src="@/assets/logo.png" class="logo" />
      <span class="title">我的网站</span>
    </div>
    <a-menu
      v-model:selectedKeys="selectedKeys"
      theme="light"
      mode="horizontal"
      :items="menuItems"
      class="menu"
      @click="handleMenuClick"
    />
    <div class="user-info">
      <a-button type="primary" @click="handleLogin">登录</a-button>
    </div>
  </a-layout-header>
</template>

<script setup lang="ts">
import { ref, watch } from 'vue'
import { useRouter, useRoute } from 'vue-router'

const router = useRouter()
const route = useRoute()

const selectedKeys = ref<string[]>([route.name as string])

const menuItems = ref([
  {
    key: 'home',
    label: '首页',
  },
  {
    key: 'about',
    label: '关于',
  },
])

// 监听路由变化，更新选中的菜单项
watch(route, () => {
  selectedKeys.value = [route.name as string]
})

const handleMenuClick = ({ key }: { key: string }) => {
  if (key === 'home') {
    router.push({ name: 'home' })
  } else if (key === 'about') {
    router.push({ name: 'about' })
  }
}

const handleLogin = () => {
  console.log('登录')
}
</script>

<style scoped>
.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 24px;
  background: #fff;
  box-shadow: 0 2px 8px #f0f1f2;
}

.logo-container {
  display: flex;
  align-items: center;
}

.logo {
  height: 48px;
  margin-right: 16px;
}

.title {
  color: #000;
  font-size: 18px;
  font-weight: bold;
}

.menu {
  flex: 1;
  margin: 0 24px;
  border-bottom: none;
}

.user-info {
  display: flex;
  align-items: center;
}
</style>