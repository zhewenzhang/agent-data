# Broadcom/Marvell 深度研究报告

**研究日期：** 2026-05-16  
**研究公司：** Broadcom Inc. (AVGO) & Marvell Technology (MRVL)  
**报告编号：** DR-2026-05-16-BRCM-MRVL

---

## 一、执行摘要

Broadcom 和 Marvell 是 AI ASIC 定制芯片领域的两大核心供应商，分别为 Google、Microsoft、Meta 等超大规模客户提供定制 AI 芯片设计服务。近期重大事件包括：NVIDIA 向 Marvell 投资 20 亿美元用于 NVLink Fusion、Marvell 收购 Polariton 推进光互联、以及两家公司共同参与 OpenAI MRC 网络规范制定。

**核心结论：**
- Broadcom 是 Google TPU 和 Meta 定制 AI 芯片的主要设计伙伴
- Marvell 是 Microsoft Maia 和 Amazon 定制 AI 芯片的主要设计伙伴
- NVIDIA 20 亿美元投资 Marvell 显示 AI 生态系统整合加速
- 两家公司均在 AI 网络芯片（交换芯片、光互联）领域深度布局
- ABF 基板需求随 AI ASIC 定制芯片增长而持续上升

---

## 二、Broadcom 产品路线图

### 2.1 定制 AI ASIC

**Google TPU（设计伙伴）：**
- **TPU v5e/v5p：** Broadcom 设计，台积电 5nm 制造
- **TPU v6 Trillium：** Broadcom 设计，台积电 3nm 制造
- **封装：** 台积电 CoWoS-L，12-16 层 ABF 基板
- **HBM：** SK Hynix HBM3/HBM3e

**Meta MTIA（设计伙伴）：**
- **MTIA v1：** Broadcom 设计，台积电 5nm 制造
- **MTIA v2：** 预计台积电 3nm 制造
- **封装：** 台积电 CoWoS-S

**其他客户：**
- **ByteDance：** 定制 AI 芯片（受出口管制限制）
- **Apple：** 部分网络芯片设计

### 2.2 网络芯片

**交换芯片：**
- **Memory：** Tomahawk 5（51.2Tbps）、Tomahawk 6（102.4Tbps 预计）
- **应用：** AI 数据中心网络
- **客户：** 超大规模云服务商、网络设备商

**光互联：**
- **CPO（共封装光学）：** 与 GF 合作推进
- **光收发器芯片：** 市场领导者

### 2.3 存储控制器

- **RAID/HBA 控制器：** 市场领导者
- **NVMe 控制器：** 企业级 SSD 控制器

---

## 三、Marvell 产品路线图

### 3.1 定制 AI ASIC

**Microsoft Maia（设计伙伴）：**
- **Maia 100：** Marvell 设计，台积电 5nm 制造
- **Maia 200：** 预计台积电 3nm 制造
- **封装：** 台积电 CoWoS-S/L
- **HBM：** SK Hynix HBM3e

**Amazon Trainium（设计伙伴）：**
- **Trainium 2：** Marvell 设计，台积电 5nm 制造
- **Trainium 3：** 预计台积电 3nm 制造
- **封装：** 台积电 CoWoS

**其他客户：**
- **Google：** 部分网络芯片设计
- **其他超大规模客户：** 保密

### 3.2 网络与互联芯片

**NVLink Fusion：**
- **时间：** 2026 年 3 月 31 日
- **内容：** NVIDIA 向 Marvell 投资 20 亿美元，Marvell 加入 NVIDIA NVLink Fusion 生态
- **意义：** Marvell 芯片可通过 NVLink 与 NVIDIA GPU 互联
- **应用：** 定制 AI 芯片与 NVIDIA GPU 的混合部署

**PCIe 6.0 交换芯片：**
- **时间：** 2026 年 3 月 17 日
- **产品：** 业界首款 260 通道 PCIe 6.0 交换芯片
- **应用：** AI 数据中心纵向扩展基础设施

**CXL 交换芯片：**
- **时间：** 2026 年 3 月 17 日
- **产品：** 新一代 CXL 交换芯片
- **应用：** 内存池化，突破 AI "内存墙"

### 3.3 光互联

**Polariton Technologies 收购：**
- **时间：** 2026 年 4 月 22 日
- **目标：** 瑞士等离子体光子学硅光子器件开发商
- **意义：** 加强 Marvell 光互联技术能力

**硅光子光引擎：**
- **产品：** 1.6T 硅光子光引擎
- **应用：** AI 数据中心光互联
- **状态：** 2026 年 2 月展示

**XConn 收购：**
- **时间：** 2026 年 2 月 10 日
- **目标：** PCIe 和 CXL 交换芯片公司
- **意义：** 扩展 PCIe/CXL 产品组合

---

## 四、封装与供应链分析

### 4.1 CoWoS 需求

| 公司 | 产品 | CoWoS 需求 |
|------|------|-----------|
| Broadcom | Google TPU v6 | 高（CoWoS-L） |
| Broadcom | Meta MTIA | 中（CoWoS-S） |
| Marvell | Microsoft Maia | 中高（CoWoS-S/L） |
| Marvell | Amazon Trainium | 中（CoWoS-S） |

**合计：** Broadcom/Marvell 合计消耗台积电 CoWoS 产能约 10-15%

### 4.2 ABF 基板需求

- **基板层数：** 定制 AI ASIC 需要 12-18 层 ABF 基板
- **供应商：** Ibiden（主要）、Shinko、Unimicron
- **需求趋势：** 随着 Google TPU v6、Microsoft Maia 200 等新产品推出，需求持续增长

### 4.3 HBM 需求

- **Broadcom：** Google TPU 使用 SK Hynix HBM3/HBM3e
- **Marvell：** Microsoft Maia/Amazon Trainium 使用 SK Hynix HBM3e
- **合计：** 约占全球 HBM 市场 10-15%

---

## 五、竞争格局分析

### 5.1 AI ASIC 定制芯片市场

```
2025年 AI ASIC 定制芯片市场份额（估算）:
Broadcom:      ~45% (Google TPU, Meta MTIA)
Marvell:       ~25% (Microsoft Maia, Amazon Trainium)
其他 (含自研): ~30%
```

### 5.2 与 NVIDIA 的竞争与合作

**竞争：**
- 定制 AI ASIC 与 NVIDIA GPU 直接竞争
- 超大规模客户倾向于自研芯片以降低对 NVIDIA 依赖

**合作：**
- NVIDIA 向 Marvell 投资 20 亿美元用于 NVLink Fusion
- 两家公司均参与 OpenAI MRC 网络规范
- 定制 AI 芯片可与 NVIDIA GPU 混合部署

### 5.3 网络芯片竞争

**Broadcom：**
- Tomahawk 系列交换芯片市场领导者
- 光收发器芯片市场领导者

**Marvell：**
- NVLink Fusion 生态参与者
- PCIe 6.0/CXL 交换芯片先行者
- 硅光子光引擎技术领先

---

## 六、近期重大事件

### 6.1 NVIDIA 向 Marvell 投资 20 亿美元

- **时间：** 2026 年 3 月 31 日
- **内容：** NVIDIA 向 Marvell 投资 20 亿美元，Marvell 加入 NVLink Fusion 生态
- **意义：**
  - Marvell 定制 AI 芯片可通过 NVLink 与 NVIDIA GPU 互联
  - 加速 AI 生态系统整合
  - 验证定制 AI ASIC 市场的重要性

### 6.2 Marvell 收购 Polariton

- **时间：** 2026 年 4 月 22 日
- **目标：** 瑞士等离子体光子学硅光子器件开发商
- **意义：** 加强光互联技术能力

### 6.3 MRC 网络规范参与

- **时间：** 2026 年 5 月
- **内容：** Broadcom 与 OpenAI、AMD、Intel、Microsoft 联合发布 MRC 规范
- **意义：** AI 网络标准化的重要参与者

### 6.4 Marvell PCIe 6.0/CXL 交换芯片

- **时间：** 2026 年 3 月 17 日
- **产品：** 260 通道 PCIe 6.0 交换芯片 + 新一代 CXL 交换芯片
- **应用：** AI 数据中心纵向扩展和内存池化

### 6.5 COMPUTEX 2026 Keynote

- **时间：** 2026 年 6 月 2 日（即将）
- **内容：** Marvell CEO Matt Murphy 将发表主题演讲
- **主题：** 扩展数据中心基础设施以驱动 AI 创新

---

## 七、财务概况

### Broadcom

| 指标 | FY2025 | FY2026E |
|------|--------|---------|
| 营收 | ~550 亿美元 | ~650 亿美元 |
| AI 相关营收 | ~150 亿美元 | ~200 亿美元 |
| 毛利率 | ~75% | ~76% |
| 市值 | ~8000 亿美元 | ~9000 亿美元 |

### Marvell

| 指标 | FY2026 | FY2027E |
|------|--------|---------|
| 营收 | ~70 亿美元 | ~90 亿美元 |
| AI 相关营收 | ~30 亿美元 | ~45 亿美元 |
| 毛利率 | ~62% | ~64% |
| 市值 | ~800 亿美元 | ~1000 亿美元 |

---

## 八、风险与机遇

### 8.1 风险

1. **客户集中风险：** 超大规模客户占比过高
2. **NVIDIA 竞争：** NVIDIA GPU 生态系统的强大护城河
3. **技术风险：** 定制 AI ASIC 的设计和量产风险
4. **供应链竞争：** 与 NVIDIA 争夺台积电 CoWoS 和 SK Hynix HBM 产能

### 8.2 机遇

1. **AI 需求爆发：** 定制 AI ASIC 需求指数增长
2. **NVLink Fusion：** Marvell 通过 NVLink 扩展市场
3. **网络芯片增长：** AI 数据中心网络升级需求
4. **光互联：** CPO 和硅光子技术的商业化

---

## 九、供应链上下游分析

### 9.1 上游供应链

```
Broadcom/Marvell 供应链全景图:

[EDA 工具] Synopsys, Cadence
    ↓
[IP 授权] Arm (CPU架构), Synopsys (SerDes)
    ↓
[芯片设计] Broadcom/Marvell (内部)
    ↓
[晶圆代工] TSMC (5nm, 3nm)
    ↓
[封装] TSMC (CoWoS-S/L)
    ↓
[ABF 基板] Ibiden, Shinko, Unimicron
    ↓
[HBM] SK Hynix, Samsung
    ↓
[网络] Broadcom (Tomahawk), Marvell (NVLink Fusion)
    ↓
[系统集成] 超大规模客户自行集成
```

### 9.2 关键供应商

**台积电 (TSMC)：**
- Broadcom/Marvell 是台积电 CoWoS 的重要客户
- 合计消耗 CoWoS 产能约 10-15%

**SK Hynix：**
- Broadcom/Marvell 的 HBM 供应商
- 合计占 HBM 市场约 10-15%

### 9.3 下游客户

- **Google：** TPU 定制芯片（Broadcom 设计）
- **Microsoft：** Maia 定制芯片（Marvell 设计）
- **Meta：** MTIA 定制芯片（Broadcom 设计）
- **Amazon：** Trainium 定制芯片（Marvell 设计）
- **超大规模云服务商：** 网络芯片采购

---

## 十、总结与展望

Broadcom 和 Marvell 在 AI ASIC 定制芯片和网络芯片领域占据重要地位。NVIDIA 向 Marvell 投资 20 亿美元显示 AI 生态系统正在加速整合，定制 AI ASIC 与 NVIDIA GPU 的混合部署将成为主流架构。

**关键观察点：**
1. Google TPU v6、Microsoft Maia 200 等新产品的推出时间
2. NVLink Fusion 的商业化进展
3. CPO 和硅光子技术的商业化
4. PCIe 6.0/CXL 交换芯片的市场采用
5. NVIDIA 与定制 AI ASIC 的竞争格局变化

**投资含义：**
- **台积电 (TSMC)：** Broadcom/Marvell CoWoS 需求的受益者
- **SK Hynix：** HBM 需求的受益者
- **Ibiden/Shinko/Unimicron：** ABF 基板需求的受益者
- **Broadcom/Marvell：** AI ASIC 定制芯片和网络芯片增长的核心受益者

---

*报告结束。下次研究对象：SK Hynix/Samsung (HBM3E/HBM4产能、竞争格局)*
