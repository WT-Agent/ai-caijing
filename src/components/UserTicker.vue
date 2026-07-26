<template>
  <div class="glass-card ticker-card">
    <div class="ticker-wrapper">
      <div v-for="(item, index) in tickerItems" :key="index" class="ticker-item">
        <span>{{ item.text }}</span>
        <span style="color: var(--success-color); font-weight: bold;">[研判生成完成]</span>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const tickerItems = ref([
  { text: '用户 136****4912 完成了降息周期下家庭资产配置理财金字塔规划' },
  { text: '用户 178****8209 完成了新能源汽车产业链财报与竞争壁垒拆解' },
  { text: '用户 181****0193 完成了高股息红利策略防守反击方案分析' },
  { text: '用户 133****5520 解读了央行最新货币政策对房贷与债市影响' },
  { text: '用户 159****9918 生成了通俗商业故事：为什么雪糕刺客消失了' },
]);
</script>
