<script setup>import { ref } from 'vue'

// 从环境变量读取完整公安备案号
const PublicSecurityFullcode = ref(import.meta.env.VITE_PUBLIC_SECURITY_FULLCODE)

// 使用正则提取纯数字部分
const PublicSecurityCode = ref('')
if (PublicSecurityFullcode.value) {
  // 匹配连续12位以上数字（公安备案号数字部分通常为18位）
  const match = PublicSecurityFullcode.value.match(/\d{12,}/)
  PublicSecurityCode.value = match ? match[0] : ''
}

const ICPCode = ref(import.meta.env.VITE_ICP_CODE)
</script>
<template>
  <footer>
    <p>
      <!-- ICP备案链接 -->
      <a
          :href="`https://beian.miit.gov.cn`"
          target="_blank"
      >
        {{ ICPCode }}
      </a>
      <!-- 公安备案链接 -->
      <a
          :href="`https://www.beian.gov.cn/portal/registerSystemInfo?recordcode=${PublicSecurityCode}`"
          target="_blank"
      >
        {{ PublicSecurityFullcode }}
      </a>

      <!-- SSL 图标保持原样 -->
      <span class="ssl-icon">
        <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none"
             stroke="#4CAF50" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <rect x="3" y="11" width="18" height="11" rx="2" ry="2"></rect>
          <path d="M7 11V7a5 5 0 0 1 10 0v4"></path>
        </svg>
      </span>
    </p>
  </footer>
</template>

<style scoped>
/* 备案号链接样式 */
footer a {
  color: #999;
  text-decoration: none;
  transition: color 0.3s ease;
}

footer a:hover {
  color: #e74c3c;
  text-decoration: underline;
}

/* SSL 图标样式 */
.ssl-icon {
  display: inline-block;
  vertical-align: middle;
  margin-left: 10px;
  width: 20px;
  height: 20px;
}

/* 页脚样式 */
footer {
  position: absolute;
  bottom: 20px;
  width: 100%;
  text-align: center;
  font-size: 0.9rem;
  color: #999;
}

</style>