<script setup>

</script>

<template>
  <!-- 右下角 SVG 图案 -->
  <div class="background-icon">
    <svg xmlns="http://www.w3.org/2000/svg" width="250" height="250" viewBox="0 0 24 24" fill="none" stroke="#e74c3c" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
      <!-- 盾牌 -->
      <path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z" />
      <!-- 叉 -->
      <line x1="15" y1="9" x2="9" y2="15" />
      <line x1="9" y1="9" x2="15" y2="15" /></svg>
  </div>
</template>

<style scoped>
/* 右下角图案容器 */
.background-icon {
  position: absolute;
  opacity: 0.2; /* 降低图案透明度 */
  z-index: 0;
  bottom: -70px;
  right: -70px;
  transform: scale(0.9); /* 缩小图案 */
}
</style>