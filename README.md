<div align="center">

# 网腾无限AI - 财经分析与投资理财专家

**基于大语言模型构建的智能财经研判与资产配置专家，提供宏观政策解读、财报拆解、理财规划与黑天鹅风险预警**

[Vue 3] · [TypeScript] · [Vite] · [Vanilla CSS] · [开源协议 MIT]

[![GitHub stars](https://img.shields.io/github/stars/WT-Agent/ai-caijing?style=social)](https://github.com/WT-Agent/ai-caijing)
[![GitHub license](https://img.shields.io/github/license/WT-Agent/ai-caijing)](https://github.com/WT-Agent/ai-caijing/blob/main/LICENSE)

[在线演示](#在线演示) · [快速启动](#快速启动) · [参与贡献](#参与贡献) · [支持一下](#支持一下)

</div>

## 关于我们

团队成员均来自 C9 等顶尖学府，在字节、腾讯、阿里的工程师组成，全职创业研发开源 AI 应用产品，让所有人感受 AI 的魅力。

本项目是网腾无限 AI 微应用的标准开发模版，内置了毛玻璃深色主题样式系统、移动端与 PC 端自适应响应式框架、API 中转代理配置与流量裂变逻辑。

**我们不搞概念，不卖课，只写能跑起来的代码。**

欢迎 Star、Fork、提 Issue，一起让这个项目变得更好用。

## 4 大核心功能模块

1. **宏观背景与行业商业逻辑诊断**：深入剖析宏观政策环境、利率周期演变及特定商业模式的核心盈利驱动因子。
2. **财务数据拆解与核心竞争壁垒**：量化分析营收、净利润、自由现金流等关键财务指标，解构企业护城河与竞争格局。
3. **资产配置策略与风险收益性价比**：针对不同风险偏好定制理财金字塔比例、仓位管理方案与合理收益预期。
4. **黑天鹅风险预警与投资避坑指南**：全面识别政策调整、市场剧烈波动与高杠杆防范警戒线，提供实操避坑建议。

## 5 大 AI 评估指标

1. **数据准确度 (dataAccuracy)**：评估财务数据引用、商业逻辑拆解与行业知识的精准度。
2. **宏观洞察力 (macroInsight)**：衡量宏观经济趋势判断、利率周期理解与政策解读的前瞻性。
3. **风险预警敏感度 (riskWarningSensitivity)**：考核对市场潜在黑天鹅、高杠杆风险与投资误区识别的敏感程度。
4. **资产配置严谨度 (assetAllocationRigor)**：评价资产组合比例、仓位管理及风险收益比推导的科学性与严谨度。
5. **内容易懂度 (comprehensibility)**：评估复杂金融概念与专业财报术语向通俗易懂决策建议转换的能力。

## 核心特性

- **极简自适应交互**：提供毛玻璃质感的深色玻璃拟态自适应 Web 界面，高度适配移动端 H5 微信浏览器与 PC 体验。
- **一键零成本部署**：纯静态前端结构，支持零成本部署于 Vercel、GitHub Pages 或 CDN/OSS 静态托管服务。
- **安全开发代理**：本地开发支持使用个人 API 密钥发起代理请求，密钥由 Vite 服务器中转，无需担心前端泄露。
- **裂变解锁与留存**：内置微信朋友圈扫码分享拦截与额度重置机制，提升流量转化与留存。

## 快速启动

### 1. 克隆项目
```bash
git clone https://github.com/WT-Agent/ai-caijing.git
cd ai-caijing
```

### 2. 安装依赖
项目强制使用 pnpm 作为包管理器：
```bash
pnpm install
```

### 3. 配置本地开发环境变量
复制并修改环境变量配置文件：
```bash
cp .env.example .env
```
根据微应用的功能类型，在 `.env` 中配置您的开发者密钥：
- `DEEPSEEK_API_KEY`: 您的 DeepSeek 开发者 API 密钥（用于文本生成任务）
- `DASHSCOPE_API_KEY`: 您的通义千问/通义万相开发者 API 密钥（用于多模态与生图任务）

### 4. 启动本地开发服务
```bash
pnpm dev
```
启动成功后在浏览器访问控制台输出的地址即可。

### 5. 生产构建打包
```bash
pnpm build
```
打包后生成的 `dist` 目录即为纯静态网页资源，可直接上传部署。

## 脚手架集成说明

本模板由私有总控仓库 `ai-.wuxian.xyz` 中的 `@wuxian/cli` 脚手架统一管理，支持以下批量运维操作：

### 初始化或更新单个子项目

```bash
node bin/cli.js ai-caijing
# 示例：node bin/cli.js ai-caijing
```

脚手架将自动：
1. 读取子仓库的 `README.md` 首行作为 Prompt 主题。
2. 注入 Vue 3 静态页面结构及标准配置文件。
3. 保留原有的 `.git` 配置与 `README.md`，不覆盖个性化内容。

### 批量同步所有子项目

```bash
node bin/cli.js all
```

将模板的最新变更（如 SSO 逻辑、额度控制）一键同步至全部 31 个子项目。

### Agent 配置维护接口

```bash
# 读取子项目配置
node bin/cli.js get ai-caijing

# 写入/更新配置（支持热更新 prompt、model、title、temperature 等）
node bin/cli.js set ai-caijing prompt "你是一位特许金融分析师(CFA)..."
node bin/cli.js set ai-caijing model deepseek-chat
```

## 联系方式

- GitHub Issues: [提交反馈](https://github.com/WT-Agent/ai-caijing/issues)
- 邮箱: us@wuxian.xyz

## 打赏支持

如果本项目对您有帮助，欢迎请作者喝杯咖啡。您的支持是持续维护与更新的动力。

<div align="center">

**微信支付** | **支付宝**
:---:|:---:
<img src="https://ai.wuxian.xyz/assets/tenpay.png" width="200" alt="微信支付"> | <img src="https://ai.wuxian.xyz/assets/alipay.png" width="200" alt="支付宝">

</div>

## 版权与许可

本项目基于 MIT License 开源协议。

Copyright (c) 2026. All rights reserved.
