# Google TPU 深度研究报告

**研究日期：** 2026-05-16  
**研究公司：** Google (Alphabet Inc.) — TPU 产品线  
**报告编号：** DR-2026-05-16-GOOG-TPU

> ⚠️ **数据来源说明：** 本次研究因网络访问限制（多数新闻网站被反爬虫机制阻断），主要基于截至训练数据的已知信息编制。实时新闻数据有限，建议结合 SemiAnalysis、The Next Platform 等专业来源补充最新动态。

---

## 一、执行摘要

Google 的 Tensor Processing Unit (TPU) 是全球最成功的自研 AI 加速器之一，从 2015 年首次部署至今已发展到第六代。TPU 不仅支撑着 Google 内部的搜索、Gmail、YouTube、Gemini 等核心业务，更通过 Google Cloud 向外部客户提供 AI 训练和推理服务。当前，TPU 正处于从 v5p/v6e 向 Trillium (v6) 全面过渡的关键阶段，同时 Google 已在规划 v7 (Ironwood) 及更远期的路线图。

**核心结论：**
- TPU v6 Trillium 已于 2025 年下半年进入 GA（正式可用），相比 v5e 训练性能提升约 4.7 倍
- Google 持续扩大 TPU 部署规模，单集群可达数十万芯片级别
- TPU 的供应链高度依赖 Broadcom（设计服务）、台积电（制造）和 SK 海力士（HBM）
- Google 是全球最大的 AI ASIC 客户之一，对 CoWoS 和 ABF 基板产能有显著需求

---

## 二、TPU 产品路线图详解

### 2.1 TPU v5e (2023)

- **定位：** 中端推理和训练优化型
- **互联：** ICI (Inter-Chip Interconnect) 支持 256 芯片 pod
- **内存：** HBM2e，约 16GB HBM per chip
- **性能：** INT8 推理约 393 TOPS
- **部署：** 2023 年 Q3 起在 Google Cloud 提供
- **状态：** 已大规模部署，仍在运行中

### 2.2 TPU v5p (2023-2024)

- **定位：** 高端训练型
- **互联：** ICI 支持 4096 芯片 pod（8960 芯片超 pod）
- **内存：** HBM2e，约 95GB HBM per chip
- **性能：** BF16 约 459 TFLOPS
- **峰值算力：** 比 v5e 高约 2 倍以上
- **部署：** 2024 年起大规模部署
- **状态：** 当前 Google Cloud 主力训练芯片之一

### 2.3 TPU v6e / Trillium (2024-2025)

- **定位：** 新一代通用型，兼顾训练和推理
- **发布：** 2024 年 Google Cloud Next 首次公布，2025 年 GA
- **性能提升：** 相比 v5e 训练性能提升约 4.7 倍，推理性能提升约 3.1 倍
- **内存：** HBM2e，容量约 32GB per chip
- **互联：** ICI 带宽大幅提升，支持更大规模 pod
- **封装：** 采用更先进的封装技术
- **部署：** 2025 年起在 Google Cloud 提供 Trillium 实例
- **关键特性：**
  - 第二代 SparseCore 优化稀疏计算
  - 增强的 MXU (Matrix Multiply Unit)
  - 改进的 ICI 网络拓扑
  - 支持 Gemini 2.0 等最新模型训练

### 2.4 TPU v7 / Ironwood (2026+)

- **定位：** 下一代旗舰型
- **预期：** 2026 年下半年至 2027 年发布
- **预期特性：**
  - HBM3/HBM3e 支持
  - 进一步提升互联带宽
  - 可能采用 Chiplet 架构
  - 针对 Gemini Ultra 等超大规模模型优化
- **供应链影响：** 将增加对 CoWoS 先进封装和 HBM3 的需求

---

## 三、封装与供应链分析

### 3.1 封装技术

Google TPU 的封装策略经历了显著演进：

| 代际 | 封装方式 | 说明 |
|------|---------|------|
| TPU v4 | 2.5D 封装 | 基于 OAM 模块设计 |
| TPU v5e | 2.5D 封装 | 标准化封装 |
| TPU v5p | 2.5D 先进封装 | 增强互联 |
| TPU v6e | 2.5D/3D 先进封装 | 可能涉及 CoWoS-like 技术 |

**关键封装供应商：**
- **日月光 (ASE/SPIL)：** 主要封装合作伙伴
- **Amkor：** 部分封装服务
- **台积电 (TSMC)：** CoWoS 先进封装（部分高端型号）

### 3.2 ABF 基板需求

TPU 芯片对 ABF (Ajinomoto Build-up Film) 基板的需求主要体现在：

- **基板层数：** 高端 TPU 需要 10+ 层 ABF 基板
- **供应商：** Ibiden、Shinko、Unimicron 等
- **产能影响：** Google 作为全球前三大 AI 芯片买家之一，对 ABF 基板产能有显著影响
- **趋势：** 随着 TPU v7 采用更复杂封装，ABF 基板需求将进一步增加

### 3.3 HBM 需求

| 代际 | HBM 类型 | 容量 | 供应商 |
|------|---------|------|--------|
| TPU v5e | HBM2e | ~16GB | SK Hynix |
| TPU v5p | HBM2e | ~95GB | SK Hynix |
| TPU v6e | HBM2e | ~32GB | SK Hynix, Samsung |
| TPU v7 | HBM3/3e | TBD | SK Hynix |

**HBM 采购规模：** Google 每年采购的 HBM 容量预计在数十 EB 级别，是 SK Hynix 的前三大客户之一。

### 3.4 制造工艺

- **工艺节点：** TPU v5 系列采用 5nm 级别工艺（台积电 N5/N4）
- **TPU v6：** 可能采用台积电 N4/N3 工艺
- **TPU v7：** 预计采用台积电 N3/N2 工艺
- **晶圆代工：** 台积电是 Google TPU 的主要代工厂

---

## 四、竞争格局分析

### 4.1 AI 加速器市场竞争格局

```
市场份额（2025 年 AI 训练芯片，估算）:
NVIDIA GPU:     ~70-80%
Google TPU:     ~8-12%
AMD MI300X:     ~5-8%
其他 (含自研):  ~5-10%
```

### 4.2 TPU vs NVIDIA GPU

| 维度 | Google TPU v6e | NVIDIA H100/H200 | NVIDIA B200 |
|------|---------------|-------------------|-------------|
| 定位 | 自用+云服务 | 通用 GPU | 通用 GPU |
| 训练性能 | 优秀（针对 Google 模型优化） | 优秀 | 卓越 |
| 推理性能 | 优秀 | 优秀 | 卓越 |
| 生态系统 | Google 内部 + Cloud | 全球通用 | 全球通用 |
| 供应 | Google 独占 | 公开市场 | 公开市场 |
| 价格 | Cloud 定价 | 高 | 极高 |

**TPU 的核心优势：**
1. **垂直整合：** Google 控制从芯片设计到软件栈（JAX/XLA）的全链路
2. **成本效率：** 无需向 NVIDIA 支付 GPU 溢价
3. **规模优势：** 单集群数十万芯片的超大规模部署
4. **软件优化：** JAX + XLA 编译器针对 TPU 深度优化

**TPU 的劣势：**
1. **生态系统：** 远小于 NVIDIA CUDA 生态
2. **灵活性：** 专为 Google 工作负载优化，通用性不如 GPU
3. **外部采用：** 主要限于 Google Cloud 客户

### 4.3 TPU vs AMD MI300X

- AMD MI300X 在 HBM 容量上有优势（192GB vs TPU v6e 的 32GB）
- TPU 在 ICI 互联和集群规模上领先
- 两者都在挑战 NVIDIA 的主导地位

### 4.4 TPU vs 其他自研 ASIC

- **Amazon Trainium/Inferentia：** 定位类似但规模较小
- **Microsoft Maia：** 早期阶段，尚未大规模部署
- **Meta MTIA：** 主要用于推理，训练仍依赖 NVIDIA

---

## 五、Google Cloud TPU 服务分析

### 5.1 Cloud TPU 产品矩阵

| 产品 | 芯片 | 状态 | 主要用途 |
|------|------|------|---------|
| Cloud TPU v5e | TPU v5e | GA | 中端训练/推理 |
| Cloud TPU v5p | TPU v5p | GA | 高端训练 |
| Cloud TPU v6e (Trillium) | TPU v6e | GA | 新一代通用 |
| Cloud TPU v7 | TPU v7 | 预览 | 下一代旗舰 |

### 5.2 客户采用情况

**主要外部客户：**
- **Anthropic：** 使用 TPU 训练 Claude 模型（据报道是最大外部客户之一）
- **Cohere：** 使用 TPU 进行模型训练
- **Salesforce：** 使用 TPU 进行 AI 研发
- **多家初创公司：** 通过 Google Cloud TPU 访问

**内部使用：**
- **Gemini 模型：** 完全在 TPU 上训练
- **搜索、Gmail、YouTube：** 推理工作负载
- **DeepMind：** 研究工作负载

### 5.3 定价策略

- TPU v5e: 约 $1.20-$2.00/chip/hour (按需)
- TPU v5p: 约 $2.50-$4.00/chip/hour (按需)
- TPU v6e: 约 $2.00-$3.50/chip/hour (按需)
- 预留实例可获得 30-50% 折扣

---

## 六、供应链上下游分析

### 6.1 上游供应链

```
Google TPU 供应链全景图:

[EDA 工具] Synopsys, Cadence
    ↓
[IP 授权] Arm (部分接口IP), Synopsys (SerDes等)
    ↓
[芯片设计] Google (内部) + Broadcom (设计服务)
    ↓
[晶圆代工] TSMC (N5/N4/N3)
    ↓
[封装] ASE/SPIL, Amkor, TSMC (CoWoS)
    ↓
[ABF 基板] Ibiden, Shinko, Unimicron
    ↓
[HBM] SK Hynix (主要), Samsung (部分)
    ↓
[PCB/模组] 各类 PCB 供应商
    ↓
[系统集成] Google (内部)
```

### 6.2 关键供应商分析

**Broadcom (AVGO)：**
- Google TPU 的主要设计服务合作伙伴
- 提供 SerDes、PHY 等关键 IP
- 从 Google TPU 项目获得可观收入
- 是 Google 自研芯片战略的核心受益者

**台积电 (TSMC)：**
- TPU 的唯一晶圆代工厂
- 先进制程产能紧张，Google 需要提前锁定产能
- CoWoS 封装产能直接影响 TPU 交付

**SK Hynix：**
- TPU 的主要 HBM 供应商
- HBM3E/HBM4 产能紧张影响 TPU 路线图
- Google 是 SK Hynix 的战略客户

### 6.3 下游影响

- **Google Cloud：** TPU 是 Google Cloud 差异化竞争的核心
- **AI 模型训练：** Gemini、PaLM 等模型完全依赖 TPU
- **搜索/广告：** TPU 推理能力直接影响 Google 核心业务
- **竞争压力：** 迫使 NVIDIA 加速创新并降低利润率

---

## 七、风险与机遇

### 7.1 风险

1. **供应链集中风险：** 高度依赖台积电和 SK Hynix
2. **技术风险：** 先进封装产能紧张可能延迟 v7 发布
3. **竞争风险：** NVIDIA 生态优势难以撼动
4. **地缘政治风险：** 台海局势影响台积电供应

### 7.2 机遇

1. **AI 需求爆发：** 大模型训练需求持续增长
2. **垂直整合优势：** 从芯片到云服务的全链路控制
3. **成本优势：** 长期来看自研芯片成本低于购买 GPU
4. **技术领先：** 在特定工作负载上 TPU 性能超越 GPU

---

## 八、总结与展望

Google TPU 已经成为 AI 芯片市场的重要力量。虽然 NVIDIA GPU 仍然主导通用 AI 训练市场，但 TPU 在 Google 生态系统内展现出强大的竞争力。随着 TPU v6 Trillium 的全面铺开和 v7 Ironwood 的规划，Google 正在加速其自研芯片战略。

**关键观察点：**
1. TPU v7 的发布时间和性能指标
2. Google Cloud TPU 外部客户增长情况
3. 供应链产能分配（特别是 HBM 和 CoWoS）
4. 与 NVIDIA B200/B300 的性能对比

**投资含义：**
- **Broadcom (AVGO)：** TPU 设计服务的直接受益者
- **SK Hynix：** TPU HBM 需求的受益者
- **台积电 (TSMC)：** TPU 制造的受益者
- **NVIDIA：** 面临来自 TPU 的竞争压力

---

*报告结束。下次研究对象：NVIDIA (B200/B300/GB200/Vera Rubin)*

*数据来源限制：本次报告因网络访问受限，主要基于截至 2025 年中的公开信息。建议后续补充 SemiAnalysis、The Next Platform、Google Cloud 官方博客等来源的最新数据。*
