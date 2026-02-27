---
name: multi-agent-teams
version: "2.0"
description: |
  Advanced multi-agent team coordination with dynamic role composition, workflow templates, cross-team collaboration, and intelligent task decomposition. This skill should be used when the user asks to "create multi-agent teams", "setup team collaboration", "organize multiple teams", "coordinate cross-team projects", "build agent swarms", "implement multi-team orchestration", "setup complex agent coordination", or needs guidance on dynamic team formation, workflow composition, member pooling, cross-team communication, or advanced Agent Teams best practices. Also handles complex task decomposition and capability identification for optimal team assignment.
metadata:
  author: mbots-teams
  version: "2.0.0"
---

# Multi-Agent Teams 协作框架

高级多Agent团队协作框架，支持动态角色组合、工作流模板、跨团队协作和智能任务分解。

## 核心能力

### 1. 智能任务分解 (Intelligent Task Decomposition)
- **任务分析**: 自动分解复杂用户请求为可执行子任务
- **能力识别**: 识别每个子任务所需的技能类型
- **技能匹配**: 搜索现有技能或创建新技能来填补能力缺口
- **工作流生成**: 基于任务特征自动生成最优工作流

### 2. 动态角色系统
- **角色模板**: 预定义的角色能力模板（discoverer, triage-owner, execution-agent等）
- **动态实例化**: 角色名称可自定义，摆脱固定命名限制
- **成员池**: 全局成员池支持跨团队成员重用

### 3. 可组合工作流
- **共享工作流模板**: linear-intake, parallel-analysis, multi-team-collab, adaptive-coordination
- **项目特定覆盖**: 项目可自定义或覆盖全局工作流
- **自适应选择**: 根据任务复杂度自动选择最佳工作流

### 4. 多团队协作
- **团队模板**: 可复用的团队配置模板
- **跨团队协调**: 支持多个团队同时处理大型项目
- **成员重组**: 动态从成员池组合不同专家

### 5. 状态管理
- **标准化状态文件**: BACKLOG.md, STATUS.md, OPPORTUNITIES.md
- **心跳驱动**: HEARTBEAT.md 实现自持续运行
- **文件持久化**: 所有状态通过文件持久化，支持断点续传

## 智能任务分解工作流

```
User Request → Task Decomposition → Capability Identification → Team Assignment → Execution Plan → Multi-Team Coordination
```

### 阶段1: 任务分析与分解
当接收用户请求时，执行以下步骤：

#### 步骤1: 理解用户意图
- 分析请求的复杂性和范围
- 识别主要目标和约束条件
- 确定成功标准

#### 步骤2: 任务分解
- 将复杂请求分解为原子子任务
- 确定任务间的依赖关系
- 评估每个子任务的复杂度

#### 步骤3: 能力识别
- 为每个子任务识别所需的能力类型
- 参考能力类型分类体系（见下文）
- 确定是否需要外部技能

## 能力类型参考 (Capability Types)

基于 Universal Capability Types Reference，以下是主要能力分类：

### 1. 浏览器自动化 (`browser_automation`)
- **描述**: 网页自动化交互，包括导航、点击、表单填写和数据提取
- **适用场景**: 登录网站、填写提交表单、网页数据提取、截图、重复性网页任务
- **相关成员**: 所有成员均可使用，但需配合 browser 工具

### 2. 网络搜索 (`web_search`)
- **描述**: 使用搜索引擎查找信息
- **适用场景**: 查找文档、研究主题、获取最新新闻、寻找资源和链接
- **相关成员**: Discoverer 角色优先使用

### 3. API 集成 (`api_integration`)
- **描述**: 通过 REST、GraphQL 或其他 API 与第三方服务通信
- **适用场景**: GitHub 操作、Notion 数据库管理、云服务集成、SaaS 平台自动化
- **相关成员**: SecuritySam, ArchitectAva, ReviewerRachel

### 4. 数据提取 (`data_extraction`)
- **描述**: 从各种来源解析和提取结构化数据
- **适用场景**: PDF 文本提取、HTML 解析、图像 OCR、JSON/XML 解析
- **相关成员**: QualityQuinn, ArchitectAva

### 5. 数据转换 (`data_transformation`)
- **描述**: 在格式之间转换、清理和转换数据
- **适用场景**: 格式转换（CSV 到 JSON）、数据清理和规范化、模式转换、ETL 操作
- **相关成员**: 所有成员（内置能力）

### 6. 内容生成 (`content_generation`)
- **描述**: 创建文本、图像或其他内容
- **适用场景**: 文本摘要、翻译、写作辅助、图像生成
- **相关成员**: 所有成员（内置 LLM 能力）

### 7. 文件操作 (`file_operations`)
- **描述**: 读取、写入和操作各种格式的文件
- **适用场景**: 读写文本文件、处理 CSV/Excel 文件、处理 JSON/YAML 配置、文件压缩/解压
- **相关成员**: 所有成员

### 8. 消息传递 (`message_delivery`)
- **描述**: 向外部服务发送通知或消息
- **适用场景**: Slack 通知、发送邮件、Discord 消息、SMS/推送通知
- **相关成员**: Facilitator 角色

### 9. 身份验证 (`authentication`)
- **描述**: 处理身份验证和访问管理
- **适用场景**: OAuth 流程、API 密钥管理、会话处理、凭据存储
- **相关成员**: SecuritySam

### 10. 数据库操作 (`database_operations`)
- **描述**: 与数据库交互进行数据存储和检索
- **适用场景**: SQL 查询、NoSQL 操作、数据持久化、数据库迁移
- **相关成员**: ArchitectAva, StructureSteve

### 11. 版本控制 (`version_control`)
- **描述**: 管理代码仓库和版本控制操作
- **适用场景**: Git 操作、PR/MR 管理、代码审查自动化、仓库管理
- **相关成员**: ReviewerRachel, ArchitectAva

### 12. 测试 (`testing`)
- **描述**: 自动化测试和质量保证
- **适用场景**: 单元测试、集成测试、端到端测试、测试生成
- **相关成员**: QualityQuinn, ReviewerRachel

### 13. 部署 (`deployment`)
- **描述**: 应用部署和 CI/CD 操作
- **适用场景**: Docker 操作、云部署、CI/CD 管道、发布管理
- **相关成员**: StructureSteve

## 智能团队组建策略

### 团队选择算法
根据任务分解结果和能力需求，自动选择最优团队组合：

#### 简单任务 (Simple Tasks)
- **触发条件**: 单一能力类型，低复杂度
- **团队组成**: 单个专家成员
- **工作流**: linear-intake

#### 复杂分析任务 (Complex Analysis)
- **触发条件**: 多个能力类型，中等复杂度
- **团队组成**: 相关领域的2-3名专家
- **工作流**: parallel-analysis

#### 大型多领域项目 (Large Multi-domain Projects)
- **触发条件**: 跨多个能力领域，高复杂度
- **团队组成**: 完整的多团队协作（安全+架构+质量）
- **工作流**: multi-team-collab

#### 不确定复杂度任务 (Uncertain Complexity)
- **触发条件**: 无法预判复杂度的任务
- **团队组成**: 自适应团队，根据执行情况动态调整
- **工作流**: adaptive-coordination

## 成员池架构

### Security Experts Pool
- **SecuritySam**: 安全与合规审计 (browser_automation, api_integration, authentication)
- **ComplianceChris**: 合规性专家 (content_generation, file_operations, web_search)

### Architecture Experts Pool  
- **ArchitectAva**: 架构分析师 (data_extraction, database_operations, version_control, api_integration)
- **StructureSteve**: 系统结构师 (deployment, database_operations, testing, api_integration)

### Quality Experts Pool
- **QualityQuinn**: 代码质量专家 (testing, data_extraction, file_operations, content_generation)
- **ReviewerRachel**: 代码审查专家 (version_control, testing, api_integration, content_generation)

## 目录结构

```
.openclaw/workspace/
├── workflow-templates/           # 共享工作流模板
├── role-templates/              # 共享角色模板  
├── member-pool/                 # 全局成员池
├── teams/                       # 团队模板
├── references/                  # 能力类型参考文档
└── projects/                    # 项目实例
    └── {project-name}/
        ├── team-config/         # 项目特定配置
        └── process/            # 运行时状态文件
```

## 使用场景

| 场景 | 触发词 | 工作流选择 | 团队组成 |
|------|--------|-----------|----------|
| 简单项目分析 | "拉个团队分析项目" | linear-intake | 单专家 |
| 复杂安全审计 | "启动安全和架构团队" | parallel-analysis | 安全+架构 |
| 大型多团队项目 | "为这个项目启动多团队协作" | multi-team-collab | 完整三团队 |
| 自适应任务 | "帮我处理这个复杂任务" | adaptive-coordination | 动态调整 |

## 工作流模板

### Linear Intake Workflow
兼容 reflectt/agent-team-kit 的5阶段工作流：
```
DISCOVER → TRIAGE → READY → EXECUTE → FEEDBACK
```

### Parallel Analysis Workflow  
并行处理模式，适合复杂分析任务：
```
ANALYZE (parallel) → EXECUTE → REVIEW
```

### Multi-Team Collaboration Workflow
多团队协作模式，支持团队间依赖：
```
Team1: ANALYZE → Team2: SECURITY-AUDIT → Team3: QUALITY-REVIEW
```

### Adaptive Coordination Workflow
自适应模式，根据任务特征动态选择策略。

## 状态文件规范

### BACKLOG.md
- **Ready**: 可自服务的任务队列
- **Blocked**: 需要依赖解决的任务
- **Parked**: 暂缓处理的任务

### STATUS.md  
- **Active Work**: 当前执行中的任务
- **Completed**: 已完成的任务
- **Stale Tasks**: 超时未更新的任务

### OPPORTUNITIES.md
- **Raw Discoveries**: 任何成员可添加的新机会
- **Structured Format**: 统一的发现记录格式

### HEARTBEAT.md
- **Automated Checks**: 定期检查队列健康度
- **Proactive Actions**: 自动触发工作流步骤
- **Escalation Rules**: 问题升级机制

## 团队编排器

主协调器负责：
1. **任务分解**: 分析用户请求并分解为子任务
2. **能力识别**: 识别每个子任务所需的能力类型
3. **工作流选择**: 根据任务特征选择最佳工作流
4. **成员分配**: 从成员池动态分配合适专家
5. **进度监控**: 实时跟踪所有团队状态
6. **冲突解决**: 处理团队间资源竞争
7. **结果汇总**: 生成综合报告

## 执行流程

### 阶段1: 智能分析
- 接收用户请求
- 执行任务分解和能力识别
- 选择最优工作流和团队组成

### 阶段2: 团队组建  
- 根据工作流需求选择团队模板
- 从成员池分配具体成员
- 生成项目特定的 BACKLOG/STATUS 文件

### 阶段3: 并行执行
- 启动多个团队或并行任务
- 实时更新 STATUS.md
- 心跳驱动的自动化检查

### 阶段4: 质量保证
- 交叉验证各团队结果
- 确保符合验收标准
- 处理失败和重试

### 阶段5: 结果交付
- 生成综合分析报告
- 提供改进建议
- 清理临时状态

## 最佳实践

### 角色设计原则
- **单一职责**: 每个角色专注一个领域
- **清晰边界**: 明确的职责划分
- **可替换性**: 角色可被同类型成员替换

### 工作流选择指南
- **简单任务**: Linear Intake
- **分析密集**: Parallel Analysis  
- **多领域协作**: Multi-Team Collaboration
- **不确定复杂度**: Adaptive Coordination

### 状态管理规范
- **及时更新**: 任务状态实时同步
- **完整记录**: 所有操作都有日志
- **清理机制**: 完成后自动清理临时文件

## 故障处理

| 故障类型 | 处理策略 |
|---------|---------|
| 成员不可用 | 从成员池选择替代成员 |
| 工作流阻塞 | 心跳检测 + 自动升级 |
| 跨团队冲突 | 协调器介入 + 重新分配 |
| 质量不达标 | 打回重做 + 专家介入 |
| 能力缺口 | 自动创建新技能或调整团队 |

## 模型配置策略

### 默认模型分配规则
- **通用成员**: 使用主模型 (`bailian/qwen3-max-2026-01-23`)
- **安全专家 & 质量专家**: 优先使用编码专用模型 (`bailian/qwen3-coder-plus`)
- **回退机制**: 当编码专用模型不可用时，自动回退到主模型

### 当前成员模型配置
| 成员 | 类型 | 模型配置 | 主要能力类型 |
|------|------|----------|-------------|
| SecuritySam | 安全专家 | `bailian/qwen3-coder-plus` | browser_automation, api_integration, authentication |
| ComplianceChris | 合规专家 | `bailian/qwen3-max-2026-01-23` | content_generation, file_operations, web_search |
| ArchitectAva | 架构分析师 | `bailian/qwen3-coder-plus` | data_extraction, database_operations, version_control |
| StructureSteve | 系统结构师 | `bailian/qwen3-coder-plus` | deployment, database_operations, testing |
| QualityQuinn | 代码质量专家 | `bailian/qwen3-coder-plus` | testing, data_extraction, file_operations |
| ReviewerRachel | 代码审查专家 | `bailian/qwen3-coder-plus` | version_control, testing, api_integration |

## 与现有技能集成

- **agent-teams-playbook**: 作为基础工作流引擎
- **healthcheck**: 用于安全审计成员
- **github**: 用于代码审查成员  
- **summarize**: 用于报告生成成员
- **task-decomposer**: 用于复杂任务分解
- **find-skills**: 用于技能发现和匹配

## 向后兼容性

完全兼容 reflectt/agent-team-kit 的核心理念：
- 自服务队列
- 文件驱动状态
- 无瓶颈设计
- 心跳驱动自动化

但提供了更灵活的角色命名、工作流组合、多团队协作能力和智能任务分解功能。