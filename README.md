## 黄戈语 (Geyu Huang)

UCL 电信硕士，华北电力大学自动化本科。现在做 Agent 工程：MCP 接入、工具调用、评测与消融、全栈交付。2027 届校招，方向为 AI 全栈 / Agent 平台。

### 主要项目

**[sentinel-ops](https://github.com/huanggeyu717-beep/sentinel-ops)** · AI 原生 IoT 事故自动化平台

管理员的一句自然语言运营规则被编译成受限 DSL 策略，先在历史数据上回放模拟，再交人工审批发布。建了 100 条任务的评测集与五组消融对照，任务成功率从 35% 提到 73%。关键约束写在数据库里：没有审批记录，发布记录插不进去。

`FastAPI` `React / TypeScript` `PostgreSQL` `Docker`

**[personal-agent](https://github.com/huanggeyu717-beep/personal-agent)** · 桌面 AI 助手与 Codex 受控执行端

以 MCP Server 接入 Codex，委派出来的子任务由本地 Runtime 用自配模型执行。上游只能请求动作、不能授予权限，可执行范围取路由候选、任务请求、宿主白名单与既有策略的交集，默认为空。项目改动先出 diff，人工批准后落盘。

`Python` `Electron` `MCP` `SQLite / Alembic`

**[microgrid-dispatch](https://github.com/huanggeyu717-beep/microgrid-dispatch)** · 微电网预测与调度

在六年真实电网数据上用分位数 LSTM 做日前概率预测，光伏误差低于电网调度机构公开的官方预报。NSGA-III 三目标调度、强化学习策略与规则基线在 61 个测试日上同条件对比。附 PostgreSQL 数据层与自然语言问数助手。

`PyTorch` `pymoo` `stable-baselines3` `PostgreSQL`

**硕士毕业设计** · 智能电网的通信感知一体化（代码未公开）

宽带电力线通信下的 OFDM 通信感知一体化，让通信设备顺带承担感知任务，在不加装传感器的前提下识别中压电缆缺陷。成果之一已整理为 IEEE 格式手稿。

### 其他仓库

| 仓库 | 内容 |
|---|---|
| [regulated-agent-posttraining-lab](https://github.com/huanggeyu717-beep/regulated-agent-posttraining-lab) | 金融工单 Agent 的数据工程与后训练，Qwen2.5-3B LoRA |
| [repoclaw](https://github.com/huanggeyu717-beep/repoclaw) | 轻量 Coding Agent 执行框架，含安全沙箱与工具调用追踪 |
| [aws-iot-smart-spill-detection-system](https://github.com/huanggeyu717-beep/aws-iot-smart-spill-detection-system) | 真实部署运行过的 AWS 无服务器 IoT 系统，sentinel-ops 的前身 |
| [airbnb-listing-ranking](https://github.com/huanggeyu717-beep/airbnb-listing-ranking) | TextCNN + BiLSTM 的评论文本排序 |
| [Undergraduate_FinalProject](https://github.com/huanggeyu717-beep/Undergraduate_FinalProject) | NSGA-III 的 MATLAB 实现与微电网双目标调度 |

### 技术栈

Python · TypeScript / React · SQL (PostgreSQL) · MATLAB · C/C++

MCP · Tool / Function Calling · 评测集与消融设计 · PyTorch · Docker · GitHub Actions · AWS

huanggeyu0717@163.com
