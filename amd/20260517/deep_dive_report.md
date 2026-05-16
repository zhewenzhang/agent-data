# AMD 深度分析报告

**报告日期**: 2026年5月17日  
**分析师**: 分析员（Impact Analyst）  
**数据时间范围**: 2025年11月 - 2026年5月  
**数据来源**: AMD官方投资者关系、AMD新闻室、AMD博客、公开财务报告、MLPerf Inference 6.0基准测试  

---

## 一、执行摘要

### 关键发现

AMD正处于AI加速器业务的关键转折点。Q1 FY2026营收$10.253B（+38% YoY），其中Data Center分部$5.8B（+57% YoY），已占总营收56.6%。公司从传统CPU/GPU供应商向AI基础设施平台转型的路径日益清晰，Meta的6GW战略合作协议是这一转型的标志性事件。

**核心观点**:

1. **Meta 6GW大单是AMD AI业务的里程碑**: 多年多代合作，首批1GW使用定制MI450 GPU，2026下半年开始出货，配合1.6亿股业绩挂钩认股权证，表明Meta对AMD AI能力的深度认可
2. **MI355X在MLPerf推理中首次与NVIDIA B200/B300正面对标**: 单节点Llama 2 70B Offline平手B200，Interactive场景119%领先，GPT-OSS-120B全面领先B200，证明AMD在推理场景已具备竞争力
3. **HBM4供应链锁定Samsung**: MI455X获得Samsung HBM4主要供应（13 Gbps、3.3 TB/s带宽），在HBM4时代抢占先机
4. **Helios机架级架构补齐系统级短板**: 与Meta联合开发的Open Compute Project标准机架架构，覆盖GPU+CPU+NIC+软件全栈
5. **软件生态仍是最大瓶颈**: ROCm虽在进步，但与CUDA的生态差距仍需数年弥合

### 关键数据一览

| 指标 | Q1 FY2026 | Q4 FY2025 | FY2025 全年 | Q2 FY2026 展望 |
|------|-----------|-----------|-------------|----------------|
| 营收 | $10.253B | $10.27B | $34.639B | ~$11.2B |
| Data Center | $5.8B | — | $16.6B | — |
| Non-GAAP 毛利率 | 55% | 57% | 52% | ~56% |
| Non-GAAP 净利润 | $2.265B | $2.519B | $6.831B | — |
| Non-GAAP EPS | $1.37 | — | — | — |

---

## 二、产品路线图分析

### 2.1 AMD Instinct MI300X（当前在售，CDNA 3）

MI300X是AMD进入AI加速器市场的首款大规模成功产品，已获得Meta、Microsoft、Oracle等头部客户部署。值得注意的是，Zyphra ZAYA1成为首个完全在AMD Instinct MI300X GPU + Pensando网络 + ROCm上训练的大规模MoE模型，证明AMD全栈方案的可行性。

### 2.2 AMD Instinct MI350X / MI355X（当前旗舰推理，CDNA 4）

MI355X是AMD在AI推理领域的关键产品，基于CDNA 4架构、3nm工艺、185B晶体管，最高288GB HBM3E内存，10 PFLOPS FP4/FP6算力。

**MLPerf Inference 6.0 成绩**（首次正面对标NVIDIA）:

| 基准 | MI355X vs B200 | MI355X vs B300 |
|------|----------------|----------------|
| Llama 2 70B Offline | 平手 (100%) | 92% |
| Llama 2 70B Server | 97% | 93% |
| Llama 2 70B Interactive | **119%** | **104%** |
| GPT-OSS-120B Offline | **111%** | 91% |
| GPT-OSS-120B Server | **115%** | 82% |
| Wan-2.2-t2v Single Stream | 93%（调优后108%） | 87%（调优后100%） |

**关键解读**:
- **推理场景已具备竞争力**: 在Interactive场景中MI355X全面领先B200（119%），在GPT-OSS-120B模型上Offline和Server均领先B200
- **vs B300仍有差距**: 在Server场景中落后B300约7-18%，表明在高并发服务场景中NVIDIA仍有优势
- **代际提升显著**: MI355X vs MI325X，Llama 2 70B Server吞吐量提升3.1x（仅6个月）
- **多节点扩展效率高**: Offline 93%、Server 93%、Interactive 98%，证明AMD多节点互联方案的成熟度

### 2.3 AMD Instinct MI450 Series（下一代旗舰）

MI450是AMD与Meta战略合作的核心产品:

- **定制版本**: Meta首批1GW部署使用定制MI450 GPU
- **配套**: 6th Gen EPYC "Venice" CPU + AMD Helios机架级架构
- **出货时间**: 2026下半年开始
- **客户反馈**: Lisa Su表示"leading customer forecasts exceeding our initial expectations"
- **战略意义**: MI450的成功将决定AMD能否在AI加速器市场从"挑战者"转变为"主流玩家"

### 2.4 AMD Instinct MI455X（下下代旗舰）

MI455X代表AMD在HBM4时代的先发优势:

- **HBM4供应**: Samsung签署MOU提供主要供应，基于6代10nm-class DRAM (1c) + 4nm逻辑基片，速度13 Gbps，带宽3.3 TB/s
- **早期访问**: NAVER Cloud已获得MI455X早期访问权限
- **部署计划**: TCS合作的印度200MW AI基础设施将使用MI455X GPU
- **竞争意义**: 如果MI455X按计划量产，AMD将在HBM4时代与NVIDIA Vera Rubin同期竞争

### 2.5 产品路线图时间线

| 代际 | 架构 | 预计量产 | 关键特性 |
|------|------|----------|----------|
| MI300X | CDNA 3 | 2023-2024 | 首款大规模AI加速器 |
| MI350X/MI355X | CDNA 4 | 2025-2026 | 3nm、185B晶体管、288GB HBM3E |
| MI440X | — | 2026 | 企业AI加速器 |
| MI450 | 下一代 | 2026H2 | 定制版本用于Meta、Helios平台 |
| MI455X | — | 2027 | HBM4、Samsung供应、3.3 TB/s带宽 |

---

## 三、先进封装与供应链分析

### 3.1 封装技术

AMD的AI加速器同样依赖台积电CoWoS封装技术:
- MI300X/MI350X/MI355X: 由台积电代工，采用CoWoS封装
- 具体CoWoS产能数据AMD未直接披露，需从台积电获取
- MI450/MI455X预计将继续使用台积电先进封装

### 3.2 Helios 机架级架构

Helios是AMD补齐系统级短板的关键举措:

- **发布时间**: OCP Global Summit 2025（2025年10月），CES 2026详细展示
- **定位**: yotta-scale AI基础设施蓝图
- **组件**: MI455X GPU + EPYC "Venice" CPU + Pensando Vulcano NIC + ROCm软件
- **设计**: 与Meta通过Open Compute Project联合开发
- **部署案例**:
  - Meta: 首批1GW，定制MI450 + Venice
  - TCS: 印度200MW AI基础设施
  - Cisco/HUMAIN: 到2030年1GW AI基础设施
  - HPE: Herder超级计算机（MI430X + Venice）

**战略意义**: Helios使AMD从单一芯片供应商升级为系统级解决方案提供商，与NVIDIA的NVL72/Vera Rubin DSX直接竞争。

### 3.3 供应链风险

1. **台积电依赖**: AMD所有先进AI加速器均由台积电代工，产能分配受制于台积电的整体产能规划
2. **CoWoS产能竞争**: 与NVIDIA、Apple等大客户竞争台积电CoWoS产能
3. **HBM4量产风险**: Samsung HBM4的量产时间和良率是关键变量
4. **MI450定制化风险**: Meta定制版本的大规模量产良率需要验证

---

## 四、HBM 供应分析

### 4.1 当前HBM配置

| 产品 | HBM代际 | 容量 | 供应商 |
|------|---------|------|--------|
| MI300X | HBM3 | 192GB | Samsung/SK Hynix |
| MI325X | HBM3E | 256GB | Samsung |
| MI350X/MI355X | HBM3E | 288GB | Samsung |
| MI455X | HBM4 | 待定 | Samsung（MOU） |

### 4.2 Samsung HBM4 合作的战略意义

2026年3月18日签署的Samsung HBM4 MOU是AMD供应链策略的重要突破:

- **技术领先**: Samsung HBM4基于6代10nm-class DRAM (1c) + 4nm逻辑基片，速度13 Gbps，带宽3.3 TB/s，超越行业标准
- **供应锁定**: Samsung为MI455X提供"主要供应"，确保AMD在HBM4时代的供应安全
- **深化合作**: 除HBM4外，Samsung还为EPYC "Venice"提供高性能DDR5，并讨论代工合作机会
- **历史延续**: Samsung已是MI350X和MI355X的主要HBM3E合作伙伴

### 4.3 与NVIDIA的HBM供应竞争

NVIDIA的HBM供应主要依赖SK Hynix（约50%+份额），AMD通过锁定Samsung的HBM4供应，在HBM4时代形成差异化供应策略。这降低了AMD与NVIDIA在HBM供应上的直接竞争，但也意味着AMD对Samsung的依赖度增加。

---

## 五、竞争格局分析（vs NVIDIA）

### 5.1 财务规模对比

| 指标 | AMD (Q1 FY2026) | NVIDIA (Q4 FY2026) | 倍数 |
|------|-----------------|---------------------|------|
| 总营收 | $10.253B | $68.1B | 6.6x |
| Data Center | $5.8B | $62.3B | 10.7x |
| Non-GAAP 毛利率 | 55% | 75.2% | — |
| Non-GAAP 净利润 | $2.265B | $42.96B | 19.0x |

NVIDIA在Data Center领域的营收规模是AMD的10.7倍，毛利率高出20个百分点，这一差距反映了CUDA生态的定价权。

### 5.2 产品性能对比

**MI355X vs B200/B300（MLPerf Inference 6.0）**:
- 推理场景（Interactive）: MI355X领先B200约19%
- 训练/大模型（GPT-OSS-120B）: MI355X领先B200约11-15%
- vs B300: MI355X落后约7-18%（Server场景）
- 多节点扩展: AMD效率93-98%，与NVIDIA接近

**关键差异**:
- NVIDIA Blackwell Ultra agentic AI性能领先Hopper 50x，AMD尚未公布对标数据
- NVIDIA Vera Rubin token成本再降10x，AMD MI455X的具体性能提升倍数待定
- NVIDIA Dynamo推理操作系统是软件层面的重大优势，ROCm尚无对标产品

### 5.3 生态系统对比

| 维度 | AMD | NVIDIA |
|------|-----|--------|
| 软件栈 | ROCm（开放） | CUDA（锁定） |
| 推理框架 | ROCm + 开源工具 | Dynamo 1.0（专有） |
| Agent生态 | Nutanix合作 | Agent Toolkit + OpenShell（30+合作伙伴） |
| 系统级 | Helios（OCP标准） | NVL72 / Vera Rubin DSX（专有） |
| 互联 | Pensando Vulcano | NVLink / NVLink Fusion |
| 客户规模 | Meta 6GW + 新兴客户 | 九大CSP、Meta数百万颗 |

NVIDIA在软件生态、系统级集成、客户规模上全面领先。AMD的优势在于开放生态（ROCm + OCP）、性价比、以及Meta的深度绑定。

### 5.4 竞争定位

AMD的定位是"第二选择"——为不愿完全依赖NVIDIA的客户提供替代方案。Meta的6GW协议表明，头部客户有强烈的多供应商需求，这为AMD创造了战略窗口。

---

## 六、客户采用与市场动态

### 6.1 Meta（最大客户，6GW协议）

Meta是AMD AI业务的战略支点:

- **协议规模**: 多年多代合作，部署最高6GW的AMD Instinct GPU
- **首批部署**: 1GW，使用定制MI450 GPU + EPYC "Venice" CPU，2026下半年开始出货
- **认股权证**: AMD向Meta发放最多1.6亿股业绩挂钩认股权证，与GPU出货里程碑挂钩
- **CPU合作**: Meta已部署数百万颗EPYC CPU + MI300/MI350系列GPU
- **Mark Zuckerberg**: "We're excited to form a long-term partnership with AMD to deploy efficient inference compute and deliver personal superintelligence"

**战略意义**: Meta的6GW协议不仅为AMD提供了巨大的营收确定性，更重要的是，Meta作为开源AI（LLaMA系列）的主要推动者，其大规模采用AMD硬件将显著提升ROCm生态的成熟度。

### 6.2 云厂商EPYC部署

AMD CPU业务在云厂商中持续扩展:
- **AWS**: 5th Gen EPYC新实例，最高x86性能
- **Google Cloud**: H4D VMs for HPC
- **Microsoft Azure**: 多种实例类型（通用/内存优化/计算优化）
- **Tencent**: 5th Gen EPYC云实例

### 6.3 新兴市场合作

- **NAVER Cloud**: 扩展AMD EPYC部署，获得MI455X早期访问权限，支持韩国主权AI
- **TCS / HyperVault**: 印度200MW AI基础设施，使用Helios + MI455X
- **Cisco / HUMAIN**: 沙特合资企业，到2030年1GW AI基础设施
- **Nutanix**: $150M股权投资 + $100M研发合作，ROCm集成到Nutanix Cloud Platform，首批产品2026年底上市
- **GSMA Open Telco AI**: AMD加入GSMA领导的Open Telco AI倡议

### 6.4 客户多元化趋势

AMD正在从"单一大客户"（Meta）向多元化客户基础扩展:
- **主权AI**: 韩国（NAVER Cloud、Upstage）、印度（TCS）、沙特（Cisco/HUMAIN）
- **企业AI**: Nutanix合作、MI440X定位企业市场
- **云厂商**: AWS、Google Cloud、Azure、Tencent的EPYC实例

---

## 七、风险与机遇

### 7.1 核心风险

1. **软件生态瓶颈**: ROCm与CUDA的生态差距仍是最大障碍。NVIDIA Dynamo、Agent Toolkit、OpenShell构成了完整的AI推理与agent软件栈，AMD尚无对标产品
2. **NVIDIA代际领先**: Blackwell Ultra性能领先Hopper 50x，Vera Rubin token成本再降10x，AMD MI450/MI455X的具体性能倍数待定
3. **Meta依赖风险**: 6GW协议虽然规模巨大，但AMD AI业务对Meta的依赖度过高。如果Meta调整采购策略，影响将非常显著
4. **台积电产能竞争**: 与NVIDIA、Apple等大客户竞争台积电CoWoS产能，AMD的产能分配可能受限
5. **HBM4量产风险**: Samsung HBM4的量产时间和良率直接影响MI455X的出货节奏
6. **毛利率压力**: AMD Non-GAAP毛利率55% vs NVIDIA 75.2%，价格竞争可能进一步压缩利润空间

### 7.2 增长机遇

1. **Meta 6GW协议执行**: 如果MI450按计划出货并获得Meta认股权证行权，AMD AI加速器营收可能在FY2027实现数倍增长
2. **推理市场爆发**: MI355X在MLPerf推理中证明竞争力，企业AI agent采用率飙升将驱动推理需求
3. **主权AI需求**: 韩国、印度、沙特等国的主权AI建设为AMD提供新的增长市场
4. **HBM4先发优势**: 锁定Samsung HBM4主要供应，在HBM4时代可能获得先发优势
5. **Helios系统级竞争力**: Helios使AMD从芯片供应商升级为系统级方案提供商，提升单客户价值
6. **Nutanix企业AI**: $250M总投入，ROCm集成到企业云平台，打开企业AI市场
7. **Advancing AI 2026**: 2026年7月23日活动可能发布MI450系列更多细节，提振市场信心

### 7.3 关键里程碑

| 时间 | 事件 | 影响 |
|------|------|------|
| 2026年7月23日 | Advancing AI 2026活动 | MI450/Helios/Venice详情发布 |
| 2026下半年 | MI450 Meta首批出货 | 6GW协议执行验证 |
| 2026年底 | Nutanix首批产品上市 | 企业AI市场验证 |
| 2027 | MI455X量产 | HBM4时代竞争验证 |
| 持续 | ROCm生态建设 | 长期竞争力关键 |

---

## 八、结论与展望

### 8.1 核心结论

AMD在2026年正处于AI加速器业务的拐点。Meta的6GW战略合作协议是公司历史上最大的AI订单，证明AMD已成为NVIDIA的实质性替代选择。MI355X在MLPerf推理中的表现表明，在特定推理场景中AMD已具备与NVIDIA正面竞争的能力。

**短期展望（2026-2027）**: MI450 Meta首批出货是关键验证点。如果按计划执行，AMD AI加速器营收可能在FY2027实现显著增长。Q2 FY2026展望$11.2B（+46% YoY）表明增长势头正在加速。

**中期展望（2027-2028）**: MI455X + HBM4 + Helios将决定AMD能否在AI基础设施市场站稳脚跟。Samsung HBM4的先发优势和Meta的深度绑定是两个关键有利因素。

**长期展望（2028+）**: AMD面临的最大挑战是软件生态。ROCm需要在企业级AI agent部署中证明其成熟度，否则硬件性能优势将被生态劣势抵消。Nutanix合作是企业AI生态建设的重要一步，但距离CUDA的生态规模仍有很大差距。

### 8.2 对ABF基板需求的影响

从ABF基板需求角度分析:

- **MI350X/MI355X**: CDNA 4架构、3nm工艺、185B晶体管，采用高层数ABF基板（14-18层），单颗GPU的ABF面积较大
- **MI450/MI455X**: 下一代架构，预计采用更高层数的ABF基板，单颗GPU的ABF需求可能进一步增加
- **Helios系统**: 每个机架包含多颗GPU + CPU + NIC，对ABF基板的系统级需求量巨大
- **整体趋势**: AMD AI加速器出货量的增长（Meta 6GW + 新兴客户）将驱动ABF基板需求的显著增长
- **供应风险**: AMD与NVIDIA竞争台积电CoWoS产能的同时，也在竞争高层数ABF基板的供应

### 8.3 关键监测指标

1. **MI450 Meta出货进度**: 2026下半年是否按计划开始出货
2. **Meta认股权证行权情况**: 1.6亿股认股权证与GPU出货里程碑挂钩
3. **ROCm生态进展**: 企业级AI agent部署案例数量和质量
4. **MI455X量产时间表**: HBM4供应是否按计划到位
5. **Advancing AI 2026发布内容**: MI450详细规格、Helios进展
6. **毛利率趋势**: 能否从55%向60%提升
7. **客户多元化**: 除Meta外的AI加速器营收占比

---

## 附录: 数据来源与覆盖度评估

### 已充分覆盖
- ✅ 财务数据（Q1 FY2026 + Q4 FY2025全年 + Q2展望）
- ✅ AI加速器路线图（MI300X → MI350X/MI355X → MI450 → MI455X）
- ✅ CPU路线图（EPYC Venice/Verano）
- ✅ Helios机架级架构
- ✅ HBM4供应链（Samsung MOU）
- ✅ 客户合作（Meta 6GW、NAVER Cloud、TCS、Cisco/HUMAIN、Nutanix）
- ✅ 竞争格局（MLPerf vs B200/B300对比数据）
- ✅ 软件生态（ROCm、MLPerf成绩）

### 数据缺口
- ⚠️ CoWoS封装具体产能（AMD不直接披露，需台积电数据）
- ⚠️ MI450/MI455X详细规格（晶体管数、TDP等）
- ⚠️ 与NVIDIA全面竞争分析（需更多第三方基准测试）
- ⚠️ Google TPU / 定制ASIC竞争格局
- ⚠️ 具体云厂商采购量
- ⚠️ ABF基板供应详情

---

**报告完成时间**: 2026-05-17 04:14 (GMT+8)  
**分析师**: 分析员（Impact Analyst）  
**下一步**: 交付审计员（Auditor）质量审查
