<template>
  <section class="nomads-showcase-section">
    <div class="showcase-header">
      <div class="header-left">
        <h2 class="showcase-title">财经研判与投资理财实战模板库</h2>
        <p class="showcase-subtitle">精选宏观解读、财报拆解与家庭资产配置，点击“一键套用”生成专业分析</p>
      </div>
      <span class="showcase-badge">已收录 {{ showcaseItems.length }} 个财经研判模板</span>
    </div>

    <div class="showcase-grid">
      <div 
        v-for="item in showcaseItems" 
        :key="item.id" 
        class="glass-card showcase-card"
      >
        <div class="card-header">
          <span class="scenario-tag">{{ item.tag }}</span>
          <span class="usage-count">{{ item.usageCount }} 次研判</span>
        </div>

        <div class="card-content">
          <h3 class="item-title">{{ item.title }}</h3>
          <p class="item-prompt">“{{ item.prompt }}”</p>
        </div>

        <div class="card-action">
          <button class="apply-btn" @click="applyTemplate(item)">
            <span>一键套用</span>
            <svg class="arrow-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
              <line x1="5" y1="12" x2="19" y2="12"></line>
              <polyline points="12 5 19 12 12 19"></polyline>
            </svg>
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { computed } from 'vue';

const emit = defineEmits<{
  (e: 'apply-template', payload: { prompt: string; analysisType?: string; riskPreference?: string }): void;
}>();

export interface ShowcaseItem {
  id: string;
  tag: string;
  title: string;
  prompt: string;
  analysisType?: string;
  riskPreference?: string;
  usageCount: string;
}

const showcaseItems = computed<ShowcaseItem[]>(() => [
  {
    id: 'caijing-1',
    tag: '宏观资产',
    title: '降息周期下 50 万家庭理财金字塔配置',
    prompt: '分析在低利率与降息宏观环境下，家庭拥有 50 万可投资资金，如何按照“流动性/安全边际/长期增值”建构理财金字塔。',
    analysisType: '个人与家庭资产配置理财',
    riskPreference: '保守稳健型',
    usageCount: '58.9k'
  },
  {
    id: 'caijing-2',
    tag: '赛道财报',
    title: '新能源汽车龙头财报与盈利壁垒拆解',
    prompt: '从营收增速、毛利率、自由现金流与研发投入四个视角，深入剖析新能源汽车龙头企业的商业护城河与潜在估值压力。',
    analysisType: '行业赛道与财报商业拆解',
    riskPreference: '平衡收益型',
    usageCount: '49.2k'
  },
  {
    id: 'caijing-3',
    tag: '红利策略',
    title: '高股息资产 (银行/煤炭/电力) 避坑风控',
    prompt: '评估高股息红利策略的防守价值，分析“股息率陷阱”形成原因（如分红不可持续或基本面恶化）及风控指标体系。',
    analysisType: '行业赛道与财报商业拆解',
    riskPreference: '保守稳健型',
    usageCount: '41.6k'
  },
  {
    id: 'caijing-4',
    tag: '商业模式',
    title: '即时零售颠覆传统便利店的商业逻辑',
    prompt: '从履约成本、SKU 丰富度及前置仓坪效角度，拆解美团/京东即时零售对传统线下零售的商业重构。',
    analysisType: '自媒体爆款财经科普文案',
    riskPreference: '平衡收益型',
    usageCount: '35.4k'
  },
  {
    id: 'caijing-5',
    tag: '宏观政策',
    title: '央行降准与货币政策对债市股市传导',
    prompt: '解读央行最新降准与降息信号，分析资金面充裕对国债收益率曲线、银行净息差及权益市场的传导链条。',
    analysisType: '宏观经济与政策趋势解读',
    riskPreference: '平衡收益型',
    usageCount: '38.1k'
  },
  {
    id: 'caijing-6',
    tag: '财商科普',
    title: '普通人如何辨别 P2P 与高息非法集资陷阱',
    prompt: '用通俗生动的商业比喻，向小白用户揭秘资金盘与庞氏骗局的特征，总结“保本高收益必然是诈骗”的避坑铁律。',
    analysisType: '自媒体爆款财经科普文案',
    riskPreference: '保守稳健型',
    usageCount: '52.7k'
  }
]);

function applyTemplate(item: ShowcaseItem) {
  emit('apply-template', {
    prompt: item.prompt,
    analysisType: item.analysisType,
    riskPreference: item.riskPreference
  });
}
</script>

<style scoped>
.nomads-showcase-section {
  margin-top: 2rem;
  width: 100%;
}

.showcase-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  margin-bottom: 1.25rem;
  padding-bottom: 0.75rem;
  border-bottom: 1px solid var(--card-border);
}

.showcase-title {
  font-size: 1.2rem;
  font-weight: 700;
  color: var(--text-primary);
  background: var(--primary-gradient);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.showcase-subtitle {
  font-size: 0.825rem;
  color: var(--text-secondary);
  margin-top: 0.25rem;
}

.showcase-badge {
  font-size: 0.75rem;
  color: #a5b4fc;
  background: rgba(99, 102, 241, 0.12);
  border: 1px solid rgba(99, 102, 241, 0.25);
  padding: 4px 10px;
  border-radius: 20px;
}

.showcase-grid {
  display: grid;
  grid-template-columns: repeat(1, 1fr);
  gap: 1.25rem;
}

@media (min-width: 640px) {
  .showcase-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .showcase-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}

.showcase-card {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100%;
  padding: 1.25rem;
  background: rgba(255, 255, 255, 0.02);
  border: 1px solid var(--card-border);
  border-radius: 14px;
  transition: all 0.25s ease;
}

.showcase-card:hover {
  background: rgba(255, 255, 255, 0.05);
  border-color: rgba(99, 102, 241, 0.4);
  transform: translateY(-3px);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.4);
}

.card-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 0.75rem;
}

.scenario-tag {
  font-size: 0.75rem;
  font-weight: 600;
  padding: 3px 8px;
  border-radius: 6px;
  background: rgba(168, 85, 247, 0.15);
  color: #c084fc;
  border: 1px solid rgba(168, 85, 247, 0.3);
}

.usage-count {
  font-size: 0.75rem;
  color: var(--text-secondary);
}

.card-content {
  margin-bottom: 1rem;
  flex: 1;
}

.item-title {
  font-size: 0.95rem;
  font-weight: 600;
  color: var(--text-primary);
  margin-bottom: 0.4rem;
}

.item-prompt {
  font-size: 0.825rem;
  color: var(--text-secondary);
  line-height: 1.45;
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
  font-style: italic;
}

.card-action {
  padding-top: 0.75rem;
  border-top: 1px solid rgba(255, 255, 255, 0.04);
}

.apply-btn {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 6px;
  padding: 0.5rem 1rem;
  background: rgba(99, 102, 241, 0.1);
  border: 1px solid rgba(99, 102, 241, 0.3);
  border-radius: 8px;
  color: #a5b4fc;
  font-size: 0.825rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.2s ease;
}

.showcase-card:hover .apply-btn {
  background: var(--primary-gradient);
  border-color: transparent;
  color: white;
}

.arrow-icon {
  width: 14px;
  height: 14px;
  transition: transform 0.2s ease;
}

.apply-btn:hover .arrow-icon {
  transform: translateX(3px);
}
</style>
