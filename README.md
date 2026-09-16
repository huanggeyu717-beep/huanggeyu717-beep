<div align="center">

## 黄戈语 Geyu Huang

UCL 电信硕士 · 华北电力大学自动化本科 · 2027 届

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square)
![MATLAB](https://img.shields.io/badge/MATLAB-E16737?style=flat-square)

</div>

我的工作分两条线：一条是 AI Agent 工程，做工具调用、权限控制、评测与全栈应用；另一条是电力场景下的建模与优化，包括本科阶段的微电网调度，以及硕士阶段的宽带电力线通信与通感一体化研究。

**快速浏览：** [AI Agent 与软件工程](#ai-agent-与软件工程) · [电力系统与通信研究](#电力系统与通信研究)

### AI Agent 与软件工程

**[sentinel-ops](https://github.com/huanggeyu717-beep/sentinel-ops)** · AI 原生 IoT 事故自动化平台（个人项目）

管理员用一句自然语言写下运营规则，Agent 把它编译成受限 DSL 策略，先在历史数据上回放模拟，再交给另一位管理员审批发布。审批约束写在数据库里：没有审批记录，发布记录就插不进去。项目包含 100 条任务的评测集和五组消融对照，任务成功率从 35% 提到 73%。可以用 Docker Compose 在本地运行。

`FastAPI` `React / TypeScript` `PostgreSQL` `Docker`

**[personal-agent](https://github.com/huanggeyu717-beep/personal-agent)** · 本地优先的桌面 AI 助手 / Codex 受控执行端（个人项目）

作为 MCP Server 接入 Codex，由本地 Runtime 调用用户自己配置的模型，执行 Codex 委派的子任务。上游只能请求动作，不能授予权限；可执行范围取路由候选、任务请求、宿主白名单与既有策略的交集，默认为空。项目改动先生成 diff，经人工批准才写入磁盘。

`Python` `Electron` `MCP` `SQLite / Alembic`

**[aws-iot-smart-spill-detection-system](https://github.com/huanggeyu717-beep/aws-iot-smart-spill-detection-system)** · AWS 无服务器 IoT 系统（UCL 课程六人团队项目，本人负责前端仪表盘）

超市地面漏水监测系统：传感器通过 MQTT 接入 AWS IoT Core，Lambda 把数据写入 RDS PostgreSQL 和 DynamoDB，并通过 SES 发送告警；仪表盘经 S3 + CloudFront 发布。系统曾接入真实硬件运行，云环境因成本原因已注销，仓库保留脱敏后的代码和配置。它也是 sentinel-ops 的前身。

### 电力系统与通信研究

**[microgrid-dispatch](https://github.com/huanggeyu717-beep/microgrid-dispatch)** · 微电网预测、多目标调度与安全强化学习（本科毕设的 Python 重构）

把本科 NSGA-III 微电网调度毕设重构成可复现的实验平台，数据来自比利时电网运营商 Elia 2019–2024 年的真实记录。流程包括：分位数 LSTM 日前概率预测；NSGA-III 调度，同时优化成本、CO₂ 和电网峰值三个目标；再与 SAC 强化学习、规则基线和 MILP 精确解做对比。所有方法都用实测数据回放执行，并逐步检查约束。结果显示，未加约束的强化学习策略在 61 个测试日中有 21–32 天联络线越限。对联络线和末端荷电状态做逐步投影后，两项越限都降到 0/61，每天多出的成本为 27.52 EUR，小于测得的噪声水平。另附 PostgreSQL 数据层和只读的自然语言查询助手。

`PyTorch` `pymoo` `stable-baselines3` `PostgreSQL`

**硕士毕业设计** · 宽带电力线通信的通感一体化（UCL，独立完成，代码暂未公开）

中压电缆的绝缘老化、接头缺陷等问题，通常要靠专门的监测设备才能发现。本课题在宽带电力线通信（PLC，约 2–30 MHz）上，让同一套 OFDM 通信信号既传输数据、又用于电缆故障的检测与分类，不需要另装传感器；并在此基础上研究如何在不削弱感知性能的前提下提升通信性能。

我搭建了仿真平台，包括：三芯中压电缆的多导体传输线信道模型（参数取自公开文献，线路包含电缆接头和端部节点）；参照 IEEE 1901 的 OFDM 物理层；背景噪声、窄带干扰和脉冲噪声模型；以及基于信道频率响应偏差的故障检测与分类基线。

毕设已完成；基于毕设的论文正在撰写，计划投稿 IEEE Communications Letters。

`Python` `NumPy / SciPy` `OFDM` `信道建模`

### 其他仓库

| 仓库 | 内容 |
|---|---|
| [regulated-agent-posttraining-lab](https://github.com/huanggeyu717-beep/regulated-agent-posttraining-lab) | 金融工单 Agent 的数据工程与后训练实验，Qwen2.5-3B LoRA |
| [repoclaw](https://github.com/huanggeyu717-beep/repoclaw) | 基于 Learn-OpenClaw 教学框架扩展的 Coding Agent 执行框架，补充了安全沙箱与工具调用追踪 |
| [airbnb-listing-ranking](https://github.com/huanggeyu717-beep/airbnb-listing-ranking) | TextCNN + BiLSTM 的评论文本排序（课程项目） |
| [Undergraduate_FinalProject](https://github.com/huanggeyu717-beep/Undergraduate_FinalProject) | 本科毕设原件：NSGA-III 的 MATLAB 实现与微电网双目标调度 |

### 技术栈

Python · TypeScript / React · SQL (PostgreSQL) · MATLAB · C/C++

MCP · Tool / Function Calling · 评测集与消融设计 · Docker · GitHub Actions · AWS

PyTorch · 多目标优化 (pymoo) · 强化学习 · OFDM 仿真与信道建模

huanggeyu0717@163.com
