# AMD 深度研究报告

**研究日期：** 2026-05-16  
**研究公司：** Advanced Micro Devices, Inc. (AMD)  
**报告编号：** DR-2026-05-16-AMD

---

## 一、执行摘要

AMD 在 AI 加速器市场正加速追赶 NVIDIA，凭借 MI300X 的成功量产和即将推出的 MI400，公司在数据中心 AI 芯片领域的市占率持续提升。近期重大事件包括：与 OpenAI 签署投资/供应循环协议、参与 OpenAI MRC 网络规范制定、以及在推理市场与 NVIDIA-Groq 组合的竞争加剧。

**核心结论：**
- MI300X 已量产交付，192GB HBM3 是其核心卖点
- MI400 预计 2026 年下半年至 2027 年发布，采用 CDNA 4 架构
- 与 OpenAI 的循环交易（投资+供应）是重要里程碑
- ROCm 软件生态持续改善但仍落后 CUDA
- 推理市场是 AMD 的机会窗口，尤其是 NVIDIA-Groq 整合期间

---

## 二、产品路线图详解

### 2.1 MI300X (2023-2026)

- **架构：** CDNA 3
- **工艺：** 台积电 5nm + 6nm（Chiplet 设计）
- **HBM：** 192GB HBM3（8 个堆叠）
- **内存带宽：** 5.3 TB/s
- **FP16 性能：** 约 1.3 PFLOPS
- **TDP：** 750W
- **封装：** 台积电 CoWoS-S
- **状态：** 2024 年起大规模交付

**关键优势：**
- 192GB HBM3 容量超过 NVIDIA H100（80GB）和 H200（141GB）
- 内存带宽 5.3 TB/s 高于 H100 的 3.35 TB/s
- 性价比优势：价格约为 H100 的 60-70%

**客户采用：**
- Microsoft Azure（主要客户）
- Oracle Cloud
- Meta（测试部署）
- 字节跳动（受限于出口管制）

### 2.2 MI350X (2025-2026)

- **架构：** CDNA 3+（增强版）
- **HBM：** 288GB HBM3e（12 个堆叠）
- **内存带宽：** 8 TB/s
- **FP8 性能：** 进一步提升
- **状态：** 2025 年下半年起交付

### 2.3 MI400 (2026-2027)

- **架构：** CDNA 4（全新架构）
- **工艺：** 预计台积电 N3 或 N3P
- **HBM：** HBM3e 或 HBM4
- **内存容量：** 预计 384GB+
- **关键特性：**
  - 全新计算架构，针对大模型优化
  - 增强推理能力（FP4/FP2 支持）
  - 改进的芯片间互联
  - 更高的内存带宽和容量
- **预期发布：** 2026 年下半年公布细节，2027 年量产

### 2.4 更远期路线图

- **MI500：** 代号未知，预计 2028+
- **CDNA 5：** 下一代架构，可能采用 Chiplet + 3D 封装

---

## 三、封装与供应链分析

### 3.1 CoWoS 需求

| 产品 | 封装类型 | CoWoS 需求 |
|------|---------|-----------|
| MI300X | CoWoS-S | 中（8 HBM 堆叠） |
| MI350X | CoWoS-S/L | 中高（12 HBM 堆叠） |
| MI400 | CoWoS-L | 高（预计） |

**CoWoS 产能影响：**
- AMD 每月消耗台积电 CoWoS 产能的约 10-15%
- 2026 年 CoWoS 产能预计增长，但仍供不应求
- AMD 是台积电 CoWoS 的第二大客户（仅次于 NVIDIA）

### 3.2 HBM 需求

| 产品 | HBM 类型 | 容量 | 供应商 |
|------|---------|------|--------|
| MI300X | HBM3 | 192GB | SK Hynix, Samsung |
| MI350X | HBM3e | 288GB | SK Hynix |
| MI400 | HBM3e/HBM4 | 384GB+ | SK Hynix (预计) |

**HBM 采购规模：**
- AMD 是全球第二大 HBM 买家，占 HBM 市场约 15-20%
- 2026 年 HBM 采购量预计增长 100%+
- SK Hynix 是主要供应商

### 3.3 ABF 基板需求

- **基板层数：** MI300X 需要 10-14 层 ABF 基板
- **供应商：** Ibiden（主要）、Shinko、Unimicron
- **需求趋势：** 随着 MI400 发布和 HBM 堆叠数增加，ABF 基板需求将持续增长
- **瓶颈：** 高端 ABF 基板产能紧张

### 3.4 制造工艺

- **MI300X：** 台积电 5nm + 6nm（Chiplet）
- **MI400：** 预计台积电 N3/N3P
- **封装：** 台积电 CoWoS-S（MI300X）、CoWoS-L（MI400 预计）

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

### 4.2 与 NVIDIA 的竞争

**NVIDIA 的优势：**
- CUDA 生态系统（400 万+ 开发者）
- 全栈能力（芯片+软件+云服务）
- 供应链锁定（台积电+SK Hynix）
- 收购 Groq 补齐推理短板

**AMD 的优势：**
- 192GB HBM3 容量优势（vs H100 80GB）
- 性价比优势（价格约 60-70% of H100）
- 开放软件生态（ROCm）
- 与 OpenAI 的战略合作

### 4.3 推理市场机会

NVIDIA 收购 Groq 后，推理市场格局发生变化：
- **NVIDIA-Groq 组合：** Vera Rubin + Groq LP30，35x token 吞吐量提升
- **AMD 的机会：** 在 NVIDIA-Groq 整合期间（预计 Q3 2026 GA），AMD 可以抢占推理市场
- **OpenAI 的信号：** OpenAI 与 AMD 的投资/供应协议显示非 GPU 推理市场存在机会

### 4.4 其他竞争对手

**Cerebras：**
- 660 亿美元市值 IPO
- 与 OpenAI 200 亿美元协议
- wafer-scale 架构，快速推理

**SambaNova：**
- 拒绝 Intel 16 亿美元收购
- 获得 3.5 亿美元 E 轮融资
- 推理市场定位

**D-Matrix：**
- 低延迟推理定位
- 与 Infineon 合作优化

---

## 五、近期重大事件

### 5.1 与 OpenAI 的战略合作

- **投资/供应循环交易：** AMD 与 OpenAI 签署协议，OpenAI 投资 AMD 同时 AMD 供应芯片
- **意义：**
  - 验证 AMD 在 AI 芯片市场的地位
  - 与 NVIDIA 的类似交易（NVIDIA-Groq）形成呼应
  - 为 AMD 提供稳定的高端客户

### 5.2 MRC 网络规范参与

- **时间：** 2026 年 5 月
- **内容：** AMD 与 OpenAI、Microsoft、Broadcom、Intel 联合发布 MRC 规范
- **AMD 的贡献：**
  - 联合主导 MRC 规范编写
  - 贡献拥塞控制技术
  - 在 AMD Pensando Pollara 400 AI NIC 上实现 MRC
  - 计划在下一代 Vulcano 800G AI NIC 上支持 MRC
- **意义：** AMD 在 AI 网络标准化中发挥领导作用

### 5.3 ROCm 软件生态改善

- ROCm 6.x 版本持续发布
- 对 PyTorch、TensorFlow 的支持改善
- 与 NVIDIA CUDA 的差距在缩小
- 但生态系统仍远落后于 CUDA

### 5.4 出口管制影响

- AMD 对华出口受限制
- MI300X 对中国客户销售受限
- 但已获得部分许可

---

## 六、财务概况

| 指标 | FY2025 | FY2026E |
|------|--------|---------|
| 营收 | ~280 亿美元 | ~350 亿美元 |
| 数据中心营收 | ~150 亿美元 | ~200 亿美元 |
| 毛利率 | ~52% | ~54% |
| 研发支出 | ~65 亿美元 | ~80 亿美元 |
| 市值 | ~2500 亿美元 | ~3000 亿美元 |

**数据中心 AI 芯片营收：**
- 2025 年：约 80-100 亿美元
- 2026 年预计：约 120-150 亿美元
- 增长率：约 50-60%

---

## 七、风险与机遇

### 7.1 风险

1. **软件生态劣势：** ROCm 远落后于 CUDA，开发者 adoption 慢
2. **供应链竞争：** 与 NVIDIA 争夺台积电 CoWoS 和 SK Hynix HBM 产能
3. **客户集中风险：** Microsoft Azure 占 AMD AI 芯片营收的 40%+
4. **出口管制：** 对华出口限制影响营收
5. **NVIDIA-Groq 竞争：** 推理市场面临新竞争压力

### 7.2 机遇

1. **性价比优势：** MI300X 价格约为 H100 的 60-70%
2. **内存容量优势：** 192GB HBM3 容量超过竞品
3. **OpenAI 合作：** 稳定的高端客户和投资支持
4. **推理市场增长：** Agentic AI 推动推理需求爆发
5. **开放生态：** 部分客户偏好非锁定方案

---

## 八、供应链上下游分析

### 8.1 上游供应链

```
AMD 供应链全景图:

[EDA 工具] Synopsys, Cadence
    ↓
[IP 授权] Arm (CPU架构), Synopsys (SerDes)
    ↓
[GPU 设计] AMD (内部)
    ↓
[晶圆代工] TSMC (5nm, 6nm, N3)
    ↓
[封装] TSMC (CoWoS-S/L)
    ↓
[ABF 基板] Ibiden (主要), Shinko, Unimicron
    ↓
[HBM] SK Hynix (主要), Samsung
    ↓
[网络] AMD Pensando (AI NIC)
    ↓
[系统集成] AMD (Instinct), Dell, HPE, Lenovo
```

### 8.2 关键供应商

**台积电 (TSMC)：**
- AMD 是台积电 CoWoS 的第二大客户
- 先进制程（5nm, N3）的重要客户
- CoWoS 产能的约 10-15% 分配给 AMD

**SK Hynix：**
- AMD 是 SK Hynix 第二大 HBM 客户
- HBM3/HBM3e 产能的约 15-20% 分配给 AMD

**Ibiden：**
- AMD 的主要 ABF 基板供应商
- 高端基板产能紧张

### 8.3 下游客户

- **超大规模云服务商：** Microsoft Azure（主要）、Oracle Cloud
- **企业客户：** 通过 OEM（Dell、HPE、Lenovo）销售
- **AI 公司：** OpenAI（战略合作）
- **主权 AI：** 部分政府项目

---

## 九、总结与展望

AMD 在 AI 加速器市场正加速追赶，MI300X 的成功量产和与 OpenAI 的战略合作是重要里程碑。MI400 的推出将是 AMD 能否缩小与 NVIDIA 差距的关键。

**关键观察点：**
1. MI400 的发布时间和性能指标
2. ROCm 软件生态的改善速度
3. 与 OpenAI 合作的深度和广度
4. NVIDIA-Groq 整合后的竞争格局变化
5. HBM4 供应链的可用性

**投资含义：**
- **台积电 (TSMC)：** AMD CoWoS 需求的直接受益者
- **SK Hynix：** AMD HBM 需求的直接受益者
- **AMD：** 短期增长确定性高，长期需关注 ROCm 生态和竞争格局

---

*报告结束。下次研究对象：TSMC (先进制程N3/N2、CoWoS产能、ABF基板)*
