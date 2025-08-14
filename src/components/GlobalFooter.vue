<template>
  <a-layout-footer class="footer">
    <div class="copyright">
      原创项目 by <a href="https://www.baidu.com" target="_blank">杨强</a>
    </div>
  </a-layout-footer>
</template>

<script setup lang="ts">
</script>

<style scoped>
.footer {
  text-align: center;
  padding: 12px 0;
  background: #f0f2f5;
  position: fixed;
  bottom: 0;
  width: 100%;
}

.copyright {
  color: #666;
}

.copyright a {
  color: #1890ff;
  text-decoration: none;
}

.copyright a:hover {
  text-decoration: underline;
}
</style>