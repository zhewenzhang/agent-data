# NVIDIA 深度研究报告

**研究日期：** 2026-05-16  
**研究公司：** NVIDIA Corporation (NVDA)  
**报告编号：** DR-2026-05-16-NVDA

---

## 一、执行摘要

NVIDIA 继续主导全球 AI 加速器市场，市占率约 70-80%。公司已完成 Blackwell 架构（B200/B300/GB200）的大规模量产交付，并开始预告下一代 Vera Rubin 架构。近期重大事件包括：以 200 亿美元收购 Groq（快速推理芯片公司）、与 SAP 扩展企业 AI Agent 合作、以及 Cerebras IPO 后市场竞争格局的变化。

**核心结论：**
- Blackwell 架构（B200/B300/GB200）已进入全面交付阶段
- Vera Rubin 架构预计 2026 年下半年至 2027 年发布
- 200 亿美元收购 Groq 标志着 NVIDIA 补齐快速推理短板
- CoWoS 和 HBM 供应链持续紧张，NVIDIA 是台积电和 SK 海力士最大客户之一
- 竞争格局正在演变：Cerebras IPO（660 亿美元市值）、AMD MI300X/MI400、Google TPU v6

---

## 二、产品路线图详解

### 2.1 Blackwell 架构 (2024-2026)

#### B200
- **工艺：** 台积电 4NP
- **晶体管：** 2080 亿
- **HBM：** 192GB HBM3e（8 个堆叠）
- **内存带宽：** 8 TB/s
- **FP8 训练性能：** 约 9 PFLOPS
- **TDP：** 1000W
- **封装：** CoWoS-L（双 die 设计）
- **状态：** 2025 年起大规模交付

#### B300
- **定位：** Blackwell 增强版
- **HBM：** 288GB HBM3e（12 个堆叠）
- **内存带宽：** 12 TB/s
- **FP4 推理性能：** 进一步提升
- **状态：** 2025 年下半年起交付

#### GB200 NVL72
- **配置：** 72 个 B200 GPU + 36 个 Grace CPU
- **总 HBM：** 13.8 TB
- **互联：** NVLink 5.0（900 GB/s per GPU）
- **机柜功率：** 约 120 kW
- **定位：** 超大规模 AI 训练和推理
- **状态：** 2025 年起交付给超大规模客户

#### GB300 NVL72
- **配置：** 72 个 B300 GPU + 36 个 Grace CPU
- **总 HBM：** 20.7 TB
- **定位：** 下一代旗舰
- **状态：** 2025 年末至 2026 年交付

### 2.2 Vera Rubin 架构 (2026-2027)

- **代号：** Vera Rubin（以天文学家命名）
- **工艺：** 预计台积电 N3 或更先进
- **CPU：** Vera（自研 ARM 架构 CPU，替代 Grace）
- **GPU：** Rubin（下一代 GPU 架构）
- **HBM：** HBM4 预计首次采用
- **内存容量：** 预计 384GB+ per GPU
- **互联：** NVLink 6.0
- **预期发布：** 2026 年下半年公布细节，2027 年量产
- **关键特性：**
  - 可能采用 Chiplet 架构
  - 针对超万亿参数模型优化
  - 增强推理能力（FP4/FP2 支持）
  - 更高的内存带宽和容量

### 2.3 更远期路线图

- **Rubin Ultra：** Vera Rubin 的增强版本
- **下一代架构：** 代号未知，预计 2028+
- **光互联：** 正在研究芯片间光互联技术

---

## 三、封装与供应链分析

### 3.1 CoWoS 需求

NVIDIA 是台积电 CoWoS 封装的最大客户：

| 产品 | 封装类型 | CoWoS 需求 |
|------|---------|-----------|
| B200 | CoWoS-L | 高（双 die 设计） |
| B300 | CoWoS-L | 高（更多 HBM 堆叠） |
| GB200 NVL72 | CoWoS-L | 极高（72 GPU 系统） |
| Vera Rubin | CoWoS-L/3D | 极高（预计） |

**CoWoS 产能影响：**
- NVIDIA 每月消耗台积电 CoWoS 产能的 40-50%
- 2026 年 CoWoS 产能预计增长 60-80%，但仍供不应求
- NVIDIA 提前 12-18 个月锁定 CoWoS 产能

### 3.2 HBM 需求

| 产品 | HBM 类型 | 容量 | 供应商 |
|------|---------|------|--------|
| H100 | HBM3 | 80GB | SK Hynix |
| H200 | HBM3e | 141GB | SK Hynix |
| B200 | HBM3e | 192GB | SK Hynix, Samsung |
| B300 | HBM3e | 288GB | SK Hynix |
| Vera Rubin | HBM4 | 384GB+ | SK Hynix (预计) |

**HBM 采购规模：**
- NVIDIA 是全球最大的 HBM 买家，占 HBM 市场约 50%
- 2026 年 HBM 采购量预计增长 80-100%
- SK Hynix 是主要供应商（约 70%），Samsung 为次要（约 30%）

### 3.3 ABF 基板需求

- **基板层数：** Blackwell 需要 12-16 层 ABF 基板
- **供应商：** Ibiden（主要）、Shinko、Unimicron
- **需求趋势：** 随着 HBM 堆叠数增加和 CoWoS 复杂度提升，ABF 基板需求持续增长
- **瓶颈：** 高端 ABF 基板产能紧张，交期延长至 16-20 周

### 3.4 制造工艺

- **Blackwell：** 台积电 4NP
- **Vera Rubin：** 预计台积电 N3/N3P
- **封装：** 台积电 CoWoS-L（主要），日月光（部分后端）

---

## 四、竞争格局分析

### 4.1 市场份额

```
2025年 AI 训练芯片市场份额（估算）:
NVIDIA:          ~75%
AMD:             ~8%
Google TPU:      ~10%
其他 (含自研):   ~7%
```

### 4.2 竞争对手动态

**AMD MI300X/MI400：**
- MI300X：192GB HBM3，已量产
- MI400：预计 2026 年发布，采用 CDNA 4 架构
- 客户采用增长：Microsoft Azure、Oracle Cloud
- OpenAI 与 AMD 的投资/供应循环交易

**Google TPU v6 Trillium：**
- 已进入 GA 阶段
- 完全自用 + Google Cloud
- Gemini 模型完全在 TPU 上训练

**Cerebras WSE-3：**
- 2026 年 5 月 14 日 IPO，市值 660 亿美元
- 与 OpenAI 签署 200 亿美元计算供应协议
- wafer-scale 架构，SRAM-based，快速推理
- 技术限制：44GB SRAM 不足以容纳大模型

**Groq（已被 NVIDIA 收购）：**
- 200 亿美元收购完成
- LPU（Language Processing Unit）架构
- 超快单用户 token 生成速度
- 将整合到 NVIDIA 推理产品线

### 4.3 NVIDIA 的护城河

1. **CUDA 生态系统：** 全球超过 400 万开发者
2. **全栈能力：** 从芯片到软件到云服务
3. **供应链锁定：** 提前锁定台积电和 SK Hynix 产能
4. **收购策略：** Mellanox（网络）、Groq（推理）
5. **研发投入：** 2025 财年研发支出约 120 亿美元

---

## 五、近期重大事件

### 5.1 NVIDIA 收购 Groq（200 亿美元）

- **时间：** 2026 年初完成
- **目标：** 补齐快速推理能力
- **意义：**
  - Groq 的 LPU 架构在单用户 token 速度上领先
  - 将整合到 NVIDIA 推理产品线
  - 消除了一个主要竞争对手
  - 为 agentic AI 工作负载提供低延迟推理

### 5.2 与 SAP 扩展合作

- **时间：** 2026 年 5 月 12 日
- **内容：** SAP 将 NVIDIA OpenShell（AI Agent 安全运行时）嵌入 SAP Business AI Platform
- **意义：**
  - NVIDIA 进入企业 AI Agent 市场
  - NemoClaw 将在 Joule Studio 中提供
  - 建立企业级 AI Agent 治理标准

### 5.3 Cerebras IPO 的影响

- Cerebras 以 660 亿美元市值上市
- 与 OpenAI 的 200 亿美元交易
- 验证了非 GPU AI 硬件市场
- 但 NVIDIA 收购 Groq 后，在快速推理领域形成直接竞争

### 5.4 GeForce NOW 和游戏业务

- 持续扩展云游戏库
- RTX 50 系列 GPU 发布
- 游戏业务保持稳定增长

---

## 六、财务概况

| 指标 | FY2025 (截至2025年1月) | FY2026E |
|------|----------------------|---------|
| 营收 | ~1300 亿美元 | ~1800 亿美元 |
| 数据中心营收 | ~1150 亿美元 | ~1600 亿美元 |
| 毛利率 | ~73% | ~74% |
| 研发支出 | ~120 亿美元 | ~150 亿美元 |
| 市值 | ~3 万亿美元 | ~3.5 万亿美元 |

---

## 七、风险与机遇

### 7.1 风险

1. **供应链集中风险：** 高度依赖台积电（制造）和 SK Hynix（HBM）
2. **地缘政治风险：** 对华出口限制影响营收（约 10-15%）
3. **竞争加剧：** AMD、Google TPU、Cerebras 等竞争对手崛起
4. **估值风险：** 当前估值隐含极高增长预期
5. **客户集中风险：** 超大规模客户（Microsoft、Google、Meta）占比过高

### 7.2 机遇

1. **AI 需求爆发：** 大模型训练和推理需求持续指数增长
2. **推理市场扩大：** Agentic AI 推动推理需求超过训练
3. **企业 AI 采用：** 企业级 AI Agent 部署加速
4. **软件和服务：** NVIDIA AI Enterprise 软件订阅收入增长
5. **收购整合：** Groq 和 Mellanox 的协同效应

---

## 八、供应链上下游分析

### 8.1 上游供应链

```
NVIDIA 供应链全景图:

[EDA 工具] Synopsys, Cadence, Siemens EDA
    ↓
[IP 授权] Arm (CPU架构), Synopsys (SerDes)
    ↓
[GPU 设计] NVIDIA (内部)
    ↓
[晶圆代工] TSMC (4NP, N3)
    ↓
[封装] TSMC (CoWoS-L), 日月光 (后端)
    ↓
[ABF 基板] Ibiden (主要), Shinko, Unimicron
    ↓
[HBM] SK Hynix (主要 ~70%), Samsung (~30%)
    ↓
[网络] NVIDIA (Mellanox) - NVLink, InfiniBand
    ↓
[系统集成] NVIDIA (DGX, HGX), Foxconn, Quanta
```

### 8.2 关键供应商

**台积电 (TSMC)：**
- NVIDIA 是台积电最大客户之一
- CoWoS 产能的 40-50% 分配给 NVIDIA
- 先进制程（4NP, N3）的优先客户

**SK Hynix：**
- NVIDIA 是 SK Hynix 最大 HBM 客户
- HBM3e 产能的约 50% 分配给 NVIDIA
- HBM4 预计 2027 年首次供货

**Ibiden：**
- NVIDIA 的主要 ABF 基板供应商
- 高端基板产能紧张，NVIDIA 提前锁定

### 8.3 下游客户

- **超大规模云服务商：** Microsoft Azure、Google Cloud、AWS、Meta
- **企业客户：** 通过 OEM（Dell、HPE、Lenovo）销售
- **主权 AI：** 各国政府 AI 基础设施项目
- **消费者：** GeForce GPU、GeForce NOW

---

## 九、总结与展望

NVIDIA 在 AI 芯片市场的主导地位短期内难以撼动。Blackwell 架构的大规模交付和 Vera Rubin 的预告显示公司保持着 18-24 个月的产品迭代节奏。200 亿美元收购 Groq 补齐了快速推理短板，与 SAP 的合作拓展了企业 AI Agent 市场。

**关键观察点：**
1. Vera Rubin 的发布时间和性能指标
2. HBM4 供应链的可用性
3. Cerebras 和 AMD 的竞争进展
4. 对华出口限制政策的变化
5. Agentic AI 工作负载对推理芯片需求的影响

**投资含义：**
- **台积电 (TSMC)：** NVIDIA CoWoS 需求的直接受益者
- **SK Hynix：** NVIDIA HBM 需求的直接受益者
- **Ibiden：** ABF 基板需求的受益者
- **NVIDIA：** 短期增长确定性高，长期需关注竞争格局变化

---

*报告结束。下次研究对象：AMD (MI300X/MI400、CDNA架构、客户采用)*
