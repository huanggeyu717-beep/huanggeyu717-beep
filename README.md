# 你好，我是黄戈语 (Geyu / Ellie Huang) 👋

**UCL 电信硕士 · 华北电力大学自动化本科 ｜ 做 AI Agent 工程：Agent Runtime、工具调用、评测与全栈交付 ｜ 2027 届校招**

我做的东西有一个共同点：**不是"跑通了模型"，而是"能证明它可靠"** —— 每个项目都自带评测集、消融对照、失败案例和可复现产物。一条贯穿的主线是：**把 AI 的能力边界做成系统约束，而不是提示词里的承诺。**

---

## 🔭 主力项目

### [sentinel-ops](https://github.com/huanggeyu717-beep/sentinel-ops) — AI 原生 IoT 事故自动化平台
把一套真实部署过的 AWS 漏水监控系统，重构成「Agent 负责理解与编译、确定性引擎负责验证/模拟/执行、人负责审批」的平台。管理员说一句人话，Agent 把它编译成受限 DSL 策略，先在 344 条真实历史读数上回放模拟，再提交人工审批。

- 100 条评测集（正常/边界/对抗/故障）+ 六类确定性 grader，五臂消融把 macro 任务成功率从 **35% 提升到 73%**
- 模型降档对照量化出"省一半成本的代价"：macro 63%，且 **Prompt Injection 得逞率 0/10 → 1/10**
- 策略发布必须由第二个人审批 —— 这条由数据库 NOT NULL 外键**物理强制**，不依赖应用代码自觉
- 63 次提交 · 约 3.4 万行 · 66 个测试文件 · Docker Compose 一键启动 · CI

### [microgrid-dispatch](https://github.com/huanggeyu717-beep/microgrid-dispatch) — 预测 → 优化 → 强化学习 端到端调度
本科毕设的 Python 重构与大幅升级：比利时 Elia 六年真实电网数据上的概率预测、NSGA-III 三目标优化、SAC 强化学习策略三方对比，外加 PostgreSQL 数据层与自然语言→SQL 数据智能体。

- 61 个测试日配对统计：RL 较规则基线 **−98±212 EUR/天**，72% 的天数更便宜；硬投影后 **0/61** 越限
- 用消融戳破自己的漂亮数字：所谓"比基线好 79%"几乎全部来自输入里的官方预报
- **预注册的假设失败了，失败本身写进了 README**：NWP 气象特征在含官方预报时零增益，移除后价值 −75%
- 45 次提交 · 中英双语 README · Docker 一键起预测服务 · CI

### 硕士毕业设计 — 智能电网通信感知一体化（ISAC）仿真系统
宽带电力线通信下的 OFDM 通信感知一体化，独立构建端到端科学计算代码库。正式实验须带审批 ID 与四阶段哈希门控，跑完由独立只读程序回读校验，开发件一律标记为不可引用。一次冻结矩阵含 13,200 个单元。成果之一已整理为 IEEE 格式手稿。（109 次提交，代码仓未公开）

---

## 📦 其他仓库

| 仓库 | 内容 |
|---|---|
| [regulated-agent-posttraining-lab](https://github.com/huanggeyu717-beep/regulated-agent-posttraining-lab) | 金融工单 Agent 的数据工程与后训练：四张注册表 → SFT/DPO/tool-SFT → Qwen2.5-3B LoRA；政策评测 88/91，加推理时 guard 后 91/91 |
| [repoclaw](https://github.com/huanggeyu717-beep/repoclaw) | 轻量 Coding Agent 执行框架：工具执行器、命令级安全沙箱、结构化调用追踪、goal loop |
| [aws-iot-smart-spill-detection-system](https://github.com/huanggeyu717-beep/aws-iot-smart-spill-detection-system) | 真实部署运行过的 AWS 无服务器 IoT 系统（脱敏版），sentinel-ops 的前身 |
| [airbnb-listing-ranking](https://github.com/huanggeyu717-beep/airbnb-listing-ranking) | TextCNN + BiLSTM 两阶段文本排序，含对数据极度偏斜的诚实分析 |
| [Undergraduate_FinalProject](https://github.com/huanggeyu717-beep/Undergraduate_FinalProject) | 从零实现 NSGA-III（MATLAB）+ 微电网调度 + GUI |

---

## 🧰 技术栈

**语言** Python · TypeScript / React · SQL (PostgreSQL) · MATLAB · C/C++
**Agent & LLM** MCP Server 与 Skill 接入 · Tool / Function Calling · 任务规划与工具路由 · 上下文与短期/长期记忆 · 受限 DSL 与结构化输出 · 评测集与消融设计 · Prompt Injection 防护 · Token 与延迟成本核算
**工程** FastAPI · Docker / Compose · GitHub Actions · Alembic · pytest / ruff / mypy · JWT + RBAC · AWS (IoT Core / Lambda / RDS / S3 / CloudFront)
**建模** PyTorch · pymoo · stable-baselines3 · scikit-learn

📫 huanggeyu0717@163.com ｜ 找 2027 届 AI 全栈 / Agent 平台方向的机会（北京 / 上海）
