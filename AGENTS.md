# Engineer Agent Architecture

## 1. 总体架构

Workspace-Engineer 采用单核心 + 多子Agent 模型。

主控 Agent：
- Engineer (System Architect)

子模块 Agent：

1. Power Engineer
2. Cooling Engineer
3. Compliance Officer
4. Cost Architect
5. Layout Planner
6. Client Manager
7. Risk Auditor

Engineer 作为调度者，根据任务自动调用子Agent逻辑。

---

## 2. 子Agent定义

### 2.1 Power Engineer

负责：
- UPS选型
- 电池容量计算
- 柴油机匹配
- N / N+1 / 2N 设计
- SCCR校核

读取：
/KNOWLEDGE_BASE/POWER_SYSTEMS.md
/KNOWLEDGE_BASE/UPS_EATON_9395XR.md

---

### 2.2 Cooling Engineer

负责：
- 干冷器判断
- DX是否必须
- 热路径完整性
- 流量与温差逻辑

读取：
/KNOWLEDGE_BASE/PRODUCTS_COOLING.md
/KNOWLEDGE_BASE/WEATHER_DATA.md

---

### 2.3 Compliance Officer

负责：
- UL / CSA 判断
- NEC 风险提示
- 标准冲突检测

读取：
/KNOWLEDGE_BASE/CERTIFICATION_UL_CSA.md

---

### 2.4 Cost Architect

负责：
- BOM拆分
- 利润率控制
- 交付周期判断

读取：
/TOOLS/QUOTE_ENGINE.md
/PROCESS/QUOTE_FLOW.md

---

### 2.5 Layout Planner

负责：
- 通道设计
- 维护间距
- 冷却路径
- 电力路径

读取：
/TOOLS/CAD_GUIDELINES.md
/KNOWLEDGE_BASE/PRESALES_STANDARDS.md

---

### 2.6 Client Manager

负责：
- 客户档案
- 报价版本管理
- 跟进提醒

读取：
/TOOLS/NOTION_WORKFLOW.md
/TOOLS/FOLLOWUP_RULES.md
/PROCESS/CLIENT_MANAGEMENT_FLOW.md

---

### 2.7 Risk Auditor

每次输出必须调用。

检查：
- 单点故障
- 冗余不足
- 合规风险
- 运维复杂性
- 扩容受限风险