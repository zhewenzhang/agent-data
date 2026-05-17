# Google TPU 深度分析报告（第二轮）

**报告日期**: 2026年5月18日  
**分析师**: 分析员（Impact Analyst）  
**数据时间范围**: 2026年4月 - 2026年5月  
**数据来源**: DigiTimes、SK Hynix Newsroom、Marvell Newsroom、EE Times、行业公开信息  
**注意**: Google Cloud和Google IR页面被Cloudflare拦截，部分数据来自第三方来源  

---

## 一、执行摘要

### 关键发现

Google TPU作为全球最成功的定制AI加速器，在第二轮研究中获得了更多供应链和竞争格局层面的细节。联发科-Marvell-TPU三代合作确认了Google TPU供应链的亚洲化趋势，SK Hynix的"AI内存外交"表明Google正在与内存供应商深化定制化合作。

**核心观点**:

1. **TPU供应链深度亚洲化**: 联发科为Marvell供应未来三代TPU关键组件，Marvell负责ASIC设计，台积电代工——亚洲半导体供应链在AI基础设施中的角色持续深化
2. **Marvell是TPU的核心ASIC设计合作伙伴**: 同时获得NVIDIA $2B NVLink Fusion投资，Marvell在定制ASIC市场的地位进一步巩固
3. **SK Hynix定制HBM为TPU提供内存创新**: cHBM的Stream DQ Architecture可提升推理吞吐量7倍，Google正在与SK Hynix共同设计定制化内存方案
4. **竞争格局多元化**: Cerebras IPO（$66B市值）和Nvidia-Groq $20B交易验证了非GPU AI芯片市场的可行性
5. **数据缺口仍然显著**: Google Cloud TPU页面和Google IR页面被Cloudflare拦截，具体性能指标、财报数据和客户案例缺失

---

## 二、TPU产品路线图更新

### 2.1 当前产品线

| 产品 | 状态 | 定位 |
|------|------|------|
| TPU v5p | 已量产，GCP可用 | 大规模AI训练和推理 |
| TPU v6e (Trillium) | 已发布，GCP可用 | 下一代性能提升 |
| Ironwood | 研发中/预发布 | 最新架构 |

### 2.2 R2新增信息

第二轮研究未能获取TPU具体性能指标（Google Cloud页面被Cloudflare拦截）。但供应链层面的信息补充显著：
- **联发科-Marvell合作**: 三代TPU的关键组件供应确认
- **SK Hynix cHBM**: 定制HBM可能应用于未来TPU
- **台积电先进制程**: TPU采用台积电N3/N2制程和CoWoS封装

### 2.3 Ironwood展望

Ironwood作为Google最新TPU架构，目前处于研发中/预发布状态。具体技术规格和量产时间表仍缺失。考虑到联发科-Marvell三代合作的时间跨度，Ironwood可能是三代中的第一代。

---

## 三、封装与供应链分析

### 3.1 供应链架构

Google TPU的供应链呈现多层架构：

```
联发科（关键组件）→ Marvell（ASIC设计）→ 台积电（代工+CoWoS封装）→ Google（系统集成）
```

这一架构的特点：
- **设计与制造分离**: Marvell负责ASIC设计，台积电负责制造和封装
- **组件多元化**: 联发科供应关键组件，降低单一供应商风险
- **亚洲供应链主导**: 设计（Marvell/联发科）和制造（台积电）均在亚洲

### 3.2 CoWoS/ABF需求

TPU采用台积电CoWoS先进封装，是CoWoS产能的重要消费者：
- **封装类型**: CoWoS-S或CoWoS-L（取决于芯片尺寸）
- **ABF基板**: 高层数ABF基板（12-18层）
- **HBM集成**: SK Hynix HBM3E/HBM4

### 3.3 SK Hynix内存合作

SK Hynix与Google的内存合作在第二轮中获得更多细节：
- **"AI内存外交"**: SK集团董事长崔泰源一周内会见Google等五家全球科技巨头CEO
- **定制化内存方案**: 讨论共同设计定制化内存解决方案
- **cHBM潜力**: Stream DQ Architecture可提升推理吞吐量7倍，可能应用于未来TPU

---

## 四、Cloud TPU服务动态

### 4.1 GCP TPU可用性

- **TPU v5p/v6e**: GCP可用，按需和预留实例定价
- **具体客户案例**: 数据缺失（Google Cloud页面被Cloudflare拦截）

### 4.2 数据中心扩张

Google持续扩张AI数据中心，云厂商$725B资本开支推动内存需求。Google作为九大CSP之一，其CapEx增长直接驱动TPU部署量和CoWoS/ABF基板需求。

---

## 五、竞争格局分析

### 5.1 竞争格局多元化（R2新增）

第二轮研究中，竞争格局出现了新的重要动态：

**Cerebras IPO**:
- $66B市值IPO，OpenAI $20B合同
- 验证投资者对非GPU AI硬件的兴趣
- WSE-3晶圆级芯片与TPU形成差异化竞争

**Nvidia-Groq $20B交易**:
- Groq LP30集成NVIDIA Vera Rubin
- 每GW收入机会$300B
- Groq LPU在推理延迟方面与TPU竞争

### 5.2 定制ASIC竞争格局

| 芯片 | 公司 | ASIC设计伙伴 | 制程 | 目标 |
|------|------|-------------|------|------|
| Google TPU | Google | Marvell/Broadcom | N3/N2 | 云端AI |
| AWS Trainium | Amazon | Broadcom | N3 | 云端AI训练 |
| Azure Maia | Microsoft | Broadcom | N3 | 云端AI推理 |
| Meta MTIA | Meta | Broadcom | N3 | 云端AI推理 |
| Cerebras WSE-3 | Cerebras | 自研 | 晶圆级 | 大规模AI |

### 5.3 NVIDIA的反击

NVIDIA通过NVLink Fusion策略将Marvell（TPU的核心ASIC合作伙伴）纳入自身生态：
- 投资Marvell $2B
- 允许定制ASIC通过NVLink连接到NVIDIA GPU/CPU
- 在NVIDIA生态内工作而非完全独立竞争

---

## 六、软件生态发展

### 6.1 Google AI软件栈

| 组件 | 定位 | 与TPU关系 |
|------|------|----------|
| JAX | 深度学习框架 | 为TPU深度优化 |
| TensorFlow | 深度学习框架 | TPU原生支持 |
| XLA | AI编译器 | TPU性能优化 |
| Pax | LLM训练框架 | TPU专用 |
| MaxText | 开源LLM | TPU优化 |

### 6.2 生态优势与劣势

**优势**:
- JAX + XLA为TPU提供深度优化的软件栈
- TensorFlow拥有庞大的开发者社区
- Pax/MaxText在大语言模型训练中表现出色

**劣势**:
- PyTorch（最流行的AI框架）对TPU支持有限
- 开发者生态规模远小于CUDA
- 企业级工具和支持不如NVIDIA成熟

---

## 七、与第一轮对比（新发现）

### 7.1 R2新增信息

| 维度 | 第一轮 | 第二轮新增 |
|------|--------|-----------|
| 供应链 | 台积电代工 | 联发科-Marvell三代合作确认 |
| 内存供应 | 未详述 | SK Hynix cHBM + "AI内存外交" |
| 竞争格局 | vs NVIDIA/AMD | +Cerebras IPO、Nvidia-Groq交易 |
| NVLink Fusion | 未涉及 | Marvell获NVIDIA $2B投资 |
| 存储需求 | 未涉及 | Vera Rubin ICMS 9,600 TB/rack |

### 7.2 仍缺失的数据

- Google Cloud Q1 2026详细财报
- TPU v5p/v6e/Ironwood具体性能指标
- GCP TPU具体客户案例
- Ironwood量产时间表
- Google数据中心扩张具体数字

---

## 八、结论与展望

### 8.1 核心结论

Google TPU在定制ASIC市场中占据独特地位——它是唯一一个由超大规模云厂商自研并大规模部署的AI加速器。联发科-Marvell-TPU三代合作确认了供应链的亚洲化趋势，SK Hynix的定制化内存合作表明TPU正在从标准化方案向深度定制化演进。

**短期展望（2026-2027）**: TPU v6e (Trillium)继续放量，Ironwood可能在Google I/O 2026或后续活动中正式发布。联发科-Marvell三代合作的第一代产品可能开始出货。

**中期展望（2027-2028）**: TPU供应链的亚洲化趋势将深化，Marvell和联发科的角色将更加重要。SK Hynix cHBM如果应用于TPU，将显著提升推理性能。

**长期展望（2028+）**: TPU的命运取决于Google Cloud的市场份额增长和AI工作负载的演变。NVIDIA NVLink Fusion策略可能改变竞争格局——如果TPU可以通过NVLink与NVIDIA GPU互连，竞争关系可能部分转化为合作关系。

### 8.2 对ABF基板需求的影响

- **TPU是CoWoS产能的重要消费者**: 每颗TPU芯片需要高层数ABF基板（12-18层）
- **三代合作意味着持续需求**: 联发科-Marvell三代合作确保未来数年的ABF基板需求
- **Google CapEx增长驱动**: 云厂商$725B资本开支中Google的份额直接驱动TPU部署量
- **竞争格局多元化**: Cerebras等新玩家也可能消耗CoWoS/ABF产能
- **整体影响**: TPU是全球ABF基板需求的重要增量来源之一

### 8.3 关键监测指标

1. **Ironwood发布时间**: Google I/O 2026或后续活动
2. **联发科-Marvell第一代TPU组件出货时间**
3. **SK Hynix cHBM是否应用于TPU**
4. **Google Cloud Q1 2026财报**: AI业务营收增长
5. **NVLink Fusion对TPU竞争格局的影响**

---

## 附录: 数据来源与覆盖度评估

### R2新增覆盖
- ✅ 联发科-Marvell-TPU三代合作
- ✅ Marvell NVLink Fusion $2B投资
- ✅ SK Hynix cHBM + "AI内存外交"
- ✅ Cerebras IPO竞争影响
- ✅ Nvidia-Groq $20B交易竞争影响

### 仍缺失
- ⚠️ Google Cloud Q1 2026详细财报
- ⚠️ TPU具体性能指标
- ⚠️ GCP TPU客户案例
- ⚠️ Ironwood量产时间表

---

**报告完成时间**: 2026-05-18 00:08 (GMT+8)  
**分析师**: 分析员（Impact Analyst）
