# SK Hynix/Samsung 深度分析报告

**报告日期**: 2026年5月17日  
**分析师**: 分析员（Impact Analyst）  
**数据时间范围**: 2026年1月 - 2026年5月  
**数据来源**: SK Hynix Newsroom、DigiTimes、EE Times、AMD-Samsung MOU、行业公开信息  

---

## 一、执行摘要

### 关键发现

SK Hynix在2026年Q1创下历史最佳业绩，营收52.5763万亿韩元（首次突破50万亿），营业利润37.6103万亿韩元（利润率72%），净利润率高达77%。AI基础设施扩张驱动的HBM需求是核心增长引擎。与此同时，Samsung通过AMD HBM4 MOU和2nm代工突破，正在挑战SK Hynix在HBM市场的主导地位。

**核心观点**:

1. **SK Hynix HBM市场主导地位稳固**: Q1营收同比+198%，营业利润同比+405%，HBM是核心驱动力。12层HBM3E已安装在NVIDIA GB300中，16层48GB HBM4采用台积电先进逻辑基片
2. **定制HBM（cHBM）是技术护城河**: Stream DQ Architecture在基片上实现数据预处理，最大推理吞吐量提升7倍，从供应商转变为技术合作伙伴
3. **Samsung HBM4锁定AMD**: 6代10nm-class DRAM + 4nm逻辑基片，13 Gbps，3.3 TB/s带宽，为MI455X提供主要供应
4. **内存供应缺口延伸至2028年+**: 云厂商$725B CapEx推动需求，供应持续紧张
5. **SK Hynix与台积电战略合作深化**: HBM4基片采用台积电先进逻辑工艺，HBF和3D Stacked DRAM on Logic开辟新赛道

### 关键数据一览

| 指标 | SK Hynix Q1 2026 | 同比 | 环比 |
|------|------------------|------|------|
| 营收 | 52.5763万亿韩元 | +198% | +60% |
| 营业利润 | 37.6103万亿韩元 | +405% | +96% |
| 营业利润率 | 72% | — | — |
| 净利润率 | 77% | — | — |
| 季末现金 | 54.3万亿韩元 | — | — |

---

## 二、HBM产品路线图

### 2.1 HBM3E（当前主力）

- **12层HBM3E**: 已安装在NVIDIA GB300中，GTC 2026上SK Hynix展台展示
- **市场地位**: SK Hynix在HBM市场占据主导份额，是NVIDIA HBM3E的主要供应商

### 2.2 HBM4（下一代）

- **16层48GB HBM4**: 产品展示，3D模型展示内部结构
- **基片工艺**: "Powered by base die in TSMC advanced logic" — 采用台积电先进逻辑工艺制造基片
- **战略意义**: HBM4基片从传统DRAM工艺转向台积电先进逻辑工艺，实现更高的计算密度和灵活性

### 2.3 定制HBM（cHBM）

cHBM是SK Hynix的技术护城河：
- **Stream DQ Architecture**: 在基片上实现数据预处理，减轻GPU负担
- **性能**: 最大推理吞吐量提升约7倍
- **意义**: 从标准化供应商转变为AI芯片性能创新的技术合作伙伴
- **客户**: 面向NVIDIA等头部客户的定制化需求

### 2.4 HBF（High Bandwidth Flash）

- **定位**: 下一代NAND解决方案，增强超高速数据传输能力
- **设计**: 面向大规模计算数据（如KV Cache）的高效处理
- **基片**: 像HBM一样采用逻辑工艺制造基片
- **意义**: 将HBM概念扩展到NAND领域，开辟新的高带宽存储品类

### 2.5 3D Stacked DRAM on Logic

- **技术**: 将DRAM直接垂直堆叠在逻辑半导体（如SoC）上
- **优势**: 显著增加数据通路（I/O），最小化延迟，大幅改善功耗和空间利用率
- **应用**: 特别适合设备端AI应用（边缘AI、AI PC、AI手机）

### 2.6 HBM产品路线图时间线

| 产品 | 状态 | 关键特性 | 目标客户 |
|------|------|----------|----------|
| HBM3E 12层 | 量产 | 已安装NVIDIA GB300 | NVIDIA |
| HBM4 16层 | 展示/开发 | 台积电逻辑基片 | NVIDIA Vera Rubin |
| cHBM | 开发 | Stream DQ，推理7x提升 | NVIDIA（定制） |
| HBF | 开发 | 高带宽Flash，KV Cache | 数据中心 |
| 3D Stacked DRAM | 开发 | DRAM on Logic | 边缘AI |

---

## 三、产能扩张与资本开支

### 3.1 产能扩张

**M15X工厂**: 加速产能爬坡，是SK Hynix当前DRAM产能扩张的核心项目。

**龙仁集群（Yongin Cluster）**: 基础设施准备中，是SK Hynix的长期产能扩张计划。

### 3.2 资本开支

- **2026年**: 投资规模将比前一年大幅增加
- **重点方向**: M15X爬坡、龙仁集群基础设施、EUV关键设备
- **策略**: 通过需求匹配的投资确保稳定供应和稳健财务状况

### 3.3 美国布局

- **AI解决方案子公司**: 2026年1月28日宣布将在美国设立专注于AI解决方案的子公司
- **意义**: 靠近NVIDIA等头部客户，深化AI内存合作

### 3.4 供需平衡

DigiTimes报道内存供应缺口延伸至2028年以后，云厂商$725B资本开支推动需求。Hana Securities分析师Rok-ho Kim指出：
- 内存供应预计保持有限，需求持续增长
- 2026年下半年供需更紧张
- AI需求扩散有望拓宽SK Hynix业务基础

---

## 四、先进封装技术

### 4.1 TSV（Through-Silicon Via）

TSV是HBM的核心封装技术，实现多层DRAM芯片垂直堆叠。SK Hynix在TSV技术上处于行业领先地位，12层HBM3E和16层HBM4均依赖TSV技术。

### 4.2 Hybrid Bonding

Hybrid Bonding是下一代3D堆叠技术，相比传统Microbump可以实现更高的互连密度和更小的间距。台积电SoIC封装技术采用Hybrid Bonding，SK Hynix在HBM和3D Stacked DRAM中应用类似技术。

### 4.3 台积电战略合作

SK Hynix与台积电的战略合作是HBM4的技术基础：
- **HBM4基片**: 采用台积电先进逻辑工艺制造
- **合作范围**: 定制HBM、HBF、3D Stacked DRAM on Logic
- **TSMC Symposium 2026**: SK Hynix CDO Ahn Hyun发表主题演讲，展示合作成果

---

## 五、客户订单分析

### 5.1 NVIDIA（最大客户）

SK Hynix与NVIDIA的关系是HBM市场最核心的供需关系：
- **GTC 2026**: SK Hynix展示AI内存领导力
- **Vera Rubin平台**: SOCAMM2和HBM4为Vera Rubin提供内存解决方案
- **cHBM**: 定制HBM，Stream DQ Architecture提升推理吞吐量7倍
- **eSSD**: Vera Rubin rack需要约9,600 TB存储容量，SK Hynix提供eSSD
- **高层会晤**: SK集团董事长崔泰源与NVIDIA CEO黄仁勋一对一会议，讨论HBM4供应和扩展合作路线图

### 5.2 全球科技巨头"AI内存外交"

崔泰源一周内会见Broadcom、Microsoft、Meta、Google等五家全球科技巨头CEO，讨论：
- 定制化内存解决方案共同设计
- AI数据中心架构合作

这表明SK Hynix正在从标准化供应商转型为定制化技术合作伙伴。

### 5.3 全球CSP客户

- **192GB SOCAMM2**: 面向全球CSP客户，用于NVIDIA Vera Rubin平台
- **性能**: 比传统RDIMM带宽提升2倍以上，功耗改善75%以上

---

## 六、竞争格局分析

### 6.1 SK Hynix vs Samsung vs Micron

| 维度 | SK Hynix | Samsung | Micron |
|------|----------|---------|--------|
| HBM市场份额 | 主导（约50%+） | 第二（约30%） | 第三（约15%） |
| HBM3E | 12层量产 | 8层/12层 | 8层/12层 |
| HBM4 | 台积电逻辑基片 | 4nm逻辑基片 | 开发中 |
| 主要客户 | NVIDIA | AMD | NVIDIA |
| Q1 2026业绩 | 创纪录（利润率72%） | 待公布 | 待公布 |
| 差异化 | cHBM、HBF、3D Stacked | 2nm代工、AMD绑定 | 成本优势 |

### 6.2 Samsung的反击

Samsung正在通过以下策略挑战SK Hynix：
- **HBM4 for AMD**: 6代10nm-class DRAM + 4nm逻辑基片，13 Gbps，3.3 TB/s，锁定AMD MI455X主要供应
- **2nm代工**: 获得AMD部分2nm代工订单（从台积电转单）
- **AMD深度绑定**: HBM4 MOU + 代工合作，形成存储+代工的双重绑定

### 6.3 竞争展望

SK Hynix的技术领先优势（cHBM、HBF、3D Stacked DRAM）和与NVIDIA的深度绑定使其在HBM市场的主导地位短期内难以被撼动。但Samsung通过AMD绑定和2nm代工突破，正在逐步缩小差距。

---

## 七、供应链与ABF基板需求

### 7.1 HBM与ABF基板的关联

HBM是CoWoS封装的核心组件之一，与ABF基板共同构成AI芯片封装的两大基础：
- **HBM供应紧张** → AI芯片出货受限 → ABF基板需求同步受限
- **HBM供应充足** → AI芯片出货放量 → ABF基板需求同步增长

### 7.2 当前供需状态

- **内存供应缺口延伸至2028年+**: HBM供应是AI芯片出货的核心约束之一
- **SK Hynix产能扩张**: M15X爬坡、龙仁集群建设，但扩张速度可能无法完全满足需求
- **Samsung HBM4量产**: 如果按时量产，将缓解HBM供应紧张

### 7.3 对ABF基板需求的影响

**直接关联**: HBM和ABF基板是CoWoS封装的两大核心组件。HBM供应的每一步扩张都意味着AI芯片出货量的增加，从而驱动ABF基板需求的增长。

**SK Hynix影响**: 
- HBM3E 12层已量产（NVIDIA GB300），持续消耗ABF基板
- HBM4 16层预计2027年量产，将驱动下一代ABF基板需求
- cHBM定制化可能需要更高规格的ABF基板

**Samsung影响**:
- HBM4 for AMD MI455X，如果按时量产，将增加AMD产品的ABF基板需求
- 2nm代工突破可能带动Samsung封装生态的ABF基板需求

---

## 八、结论与展望

### 8.1 核心结论

SK Hynix在2026年处于HBM市场的绝对巅峰。Q1创纪录的业绩（营收52.5万亿韩元，利润率72%）证明了AI内存需求的强劲。cHBM、HBF、3D Stacked DRAM on Logic等创新技术正在将SK Hynix从标准化供应商转型为AI芯片性能创新的技术合作伙伴。

**短期展望（2026-2027）**: HBM3E 12层持续放量，192GB SOCAMM2为Vera Rubin平台供货。2026年下半年供需更紧张，定价条件持续有利。

**中期展望（2027-2028）**: HBM4 16层量产是关键里程碑。台积电逻辑基片工艺的成熟度和良率将决定HBM4的量产进度。cHBM定制化将深化与NVIDIA的技术合作。

**长期展望（2028+）**: HBF和3D Stacked DRAM on Logic开辟新的增长赛道。内存供应缺口延伸至2028年+表明HBM市场的增长空间仍然巨大。

### 8.2 关键监测指标

1. **HBM4量产时间表**: 台积电逻辑基片工艺的良率和产能
2. **Samsung HBM4 for AMD进展**: 能否按时为MI455X供货
3. **SK Hynix M15X/龙仁集群产能爬坡**: 2026年下半年能否显著增加供应
4. **cHBM客户采用**: NVIDIA是否在Vera Rubin中采用定制HBM
5. **内存定价趋势**: 2026年下半年是否如预期般更紧张
6. **HBF商业化进度**: 高带宽Flash何时进入量产

---

## 附录: 数据来源与覆盖度评估

### 已覆盖
- ✅ SK Hynix Q1 2026创纪录财报
- ✅ HBM产品线（HBM3E/HBM4/cHBM/HBF/3D Stacked DRAM）
- ✅ 新产品量产（192GB SOCAMM2、321层QLC NAND、LPDDR6）
- ✅ TSMC合作（HBM4基片采用台积电先进逻辑工艺）
- ✅ 产能扩张（M15X、龙仁集群、资本开支增加）
- ✅ 客户动态（NVIDIA Vera Rubin、全球科技巨头"AI内存外交"）
- ✅ 竞争格局（vs Samsung/Micron）
- ✅ Samsung HBM4 for AMD

### 数据缺口
- ⚠️ Samsung Q1 2026详细财报数据
- ⚠️ SK Hynix HBM4具体量产时间表
- ⚠️ Samsung HBM4量产进展
- ⚠️ 具体客户采购量数字
- ⚠️ ASP具体趋势数据

---

**报告完成时间**: 2026-05-17 16:09 (GMT+8)  
**分析师**: 分析员（Impact Analyst）  
**下一步**: 交付审计员（Auditor）质量审查
