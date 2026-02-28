---
name: multi-agent-teams
version: "1.0"
description: |
  Advanced multi-agent team coordination with dynamic role composition, workflow templates, and cross-team collaboration. This skill should be used when the user asks to "create multi-agent teams", "setup team collaboration", "organize multiple teams", "coordinate cross-team projects", "build agent swarms", "implement multi-team orchestration", "setup complex agent coordination", or needs guidance on dynamic team formation, workflow composition, member pooling, cross-team communication, or advanced Agent Teams best practices. 或者当用户说"多团队协作"、"跨团队协调"、"动态组队"、"复杂agent协作"、"多团队项目"、"agent群体"、"灵活组队"、"团队模板"、"工作流编排"时也应使用此技能。
metadata:
  author: mbots-teams
  version: "1.0.0"
---

# Multi-Agent Teams 协作框架

高级多Agent团队协作框架，支持动态角色组合、工作流模板和跨团队协作。

## 核心能力

### 1. 动态角色系统
- **角色模板**: 预定义的角色能力模板（discoverer, triage-owner, execution-agent等）
- **动态实例化**: 角色名称可自定义，摆脱固定命名限制
- **成员池**: 全局成员池支持跨团队成员重用

### 2. 可组合工作流
- **共享工作流模板**: linear-intake, parallel-analysis, multi-team-collab, adaptive-coordination
- **项目特定覆盖**: 项目可自定义或覆盖全局工作流
- **自适应选择**: 根据任务复杂度自动选择最佳工作流

### 3. 多团队协作
- **团队模板**: 可复用的团队配置模板
- **跨团队协调**: 支持多个团队同时处理大型项目
- **成员重组**: 动态从成员池组合不同专家

### 4. 状态管理
- **标准化状态文件**: BACKLOG.md, STATUS.md, OPPORTUNITIES.md
- **心跳驱动**: HEARTBEAT.md 实现自持续运行
- **文件持久化**: 所有状态通过文件持久化，支持断点续传

## 目录结构

```
.openclaw/workspace/
├── workflow-templates/           # 共享工作流模板
├── role-templates/              # 共享角色模板  
├── member-pool/                 # 全局成员池
├── teams/                       # 团队模板
└── projects/                    # 项目实例
    └── {project-name}/
        ├── team-config/         # 项目特定配置
        └── process/            # 运行时状态文件
```

## 使用场景

| 场景 | 触发词 | 工作流选择 |
|------|--------|-----------|
| 简单项目分析 | "拉个团队分析项目" | linear-intake |
| 复杂安全审计 | "启动安全和架构团队" | parallel-analysis |
| 大型多团队项目 | "为这个项目启动多团队协作" | multi-team-collab |
| 自适应任务 | "帮我处理这个复杂任务" | adaptive-coordination |

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

## 成员池架构

### Security Experts Pool
- SecuritySam: 安全与合规审计
- ComplianceChris: 合规性专家

### Architecture Experts Pool  
- ArchitectAva: 架构分析师
- StructureSteve: 系统结构师

### Quality Experts Pool
- QualityQuinn: 代码质量专家
- ReviewerRachel: 代码审查专家

### Development Experts Pool
- DevBuilderAlex: 软件开发和实现专家
- DevCoderSam: 编码和部署专家

## 团队编排器

主协调器负责：
1. **工作流选择**: 根据任务特征选择最佳工作流
2. **成员分配**: 从成员池动态分配合适专家
3. **进度监控**: 实时跟踪所有团队状态
4. **冲突解决**: 处理团队间资源竞争
5. **结果汇总**: 生成综合报告

## 执行流程

### 阶段1: 配置检测
- 检查项目是否存在 team-config/
- 加载项目特定或全局工作流模板
- 识别可用的成员池

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

## 模型配置策略

### 默认模型分配规则
- **通用成员**: 使用 **主模型** (primary-model)
- **开发/安全/质量专家**: 优先使用 **编码专用模型** (coding-specialized-model)
- **回退机制**: 当编码专用模型不可用时，自动回退到主模型

### 模型占位符说明
在实际使用中，请根据您的环境和需求替换以下占位符：

- **主模型** (`primary-model`): 适用于通用任务、文本处理、架构分析等
- **编码专用模型** (`coding-specialized-model`): 适用于代码生成、代码审查、开发实现等

### 成员模型配置（使用占位符）
| 成员 | 类型 | 模型配置 |
|------|------|----------|
| SecuritySam | 安全专家 | `coding-specialized-model` |
| ComplianceChris | 合规专家 | `primary-model` |
| ArchitectAva | 架构分析师 | `primary-model` |
| StructureSteve | 系统结构师 | `primary-model` |
| QualityQuinn | 代码质量专家 | `coding-specialized-model` |
| ReviewerRachel | 代码审查专家 | `coding-specialized-model` |
| DevBuilderAlex | 开发构建专家 | `coding-specialized-model` |
| DevCoderSam | 开发编码专家 | `coding-specialized-model` |

### 模型选择指南
当您拉取团队或修改团队配置时，请根据以下原则选择合适的模型：

1. **评估任务性质**: 
   - 代码相关任务 → 编码专用模型
   - 文本/分析/设计任务 → 主模型

2. **考虑模型可用性**:
   - 检查您的环境中哪些模型可用
   - 确保所选模型支持所需的输入/输出格式

3. **性能与成本平衡**:
   - 编码专用模型通常更适合代码任务但可能成本更高
   - 主模型适合通用任务且通常更经济

4. **测试和验证**:
   - 在关键任务前测试模型效果
   - 根据实际表现调整模型分配

## 与现有技能集成

- **agent-teams-playbook**: 作为基础工作流引擎
- **healthcheck**: 用于安全审计成员
- **github**: 用于代码审查成员  
- **summarize**: 用于报告生成成员

## 向后兼容性

完全兼容 reflectt/agent-team-kit 的核心理念：
- 自服务队列
- 文件驱动状态
- 无瓶颈设计
- 心跳驱动自动化

但提供了更灵活的角色命名、工作流组合和多团队协作能力。