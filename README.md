# Multi-Agent Teams Skill

## 概述
Multi-Agent Teams 是一个高级的多团队协作技能，支持动态角色组合、可组合工作流、成员池架构和项目级别的自定义配置。现在集成了任务分解和能力识别功能，能够智能分析用户需求并自动组建最合适的专家团队。

## 核心特性

### 🧩 动态角色系统
- **角色模板**: 预定义的角色模板（Discoverer, TriageOwner, ExecutionAgent, Facilitator）
- **动态命名**: 角色实例可以使用自定义名称（如 ArchitectAva, SecuritySam）
- **松耦合**: 角色与具体职责解耦，支持灵活重组

### 🔁 可组合工作流
- **Linear Intake**: 兼容 reflectt/agent-team-kit 的5阶段工作流
- **Parallel Analysis**: 并行处理复杂任务
- **Multi-Team Collaboration**: 多个团队协同工作
- **Adaptive Coordination**: 自适应选择最适合的工作流

### 👥 成员池架构
- **全局成员池**: 按专业领域组织的成员池
- **动态组合**: 从池中选择合适的成员组成团队
- **技能匹配**: 成员与所需技能自动匹配

### 🧠 智能任务分解
- **需求分析**: 自动分解复杂用户请求为可执行子任务
- **能力识别**: 识别每个子任务所需的技能类型
- **团队推荐**: 基于能力需求推荐最佳专家组合
- **技能发现**: 自动搜索现有技能或创建新技能

### 📁 项目级配置
- **共享模板**: 全局工作流和角色模板
- **项目覆盖**: 项目可以自定义或覆盖全局配置
- **状态标准化**: 统一的 BACKLOG.md, STATUS.md, OPPORTUNITIES.md, HEARTBEAT.md

## 使用场景

### 基本触发词
- "拉个团队"
- "多agent协作"  
- "组建专家团队"
- "启动多团队分析"
- "multi-agent teams"

### 中文触发词
- "多agent"
- "agent协作"
- "agent编排"
- "并行agent"
- "分工协作"
- "拉团队"
- "拉个团队"
- "多代理协作"
- "swarm编排"
- "agent团队"

## 工作目录结构

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

## 安装和使用

### 安装
```bash
npx skills add multi-agent-teams -g -y
```

### 使用
1. 在项目目录中创建 `team-config/` 目录
2. 配置工作流、角色和成员
3. 使用触发词启动团队
4. 系统会自动进行任务分解和能力匹配

## 能力类型支持

基于 Universal Capability Types Reference，支持以下能力类型：
- **Browser Automation**: Web自动化和数据提取
- **Web Search**: 互联网信息搜索
- **API Integration**: 第三方服务集成
- **Data Extraction**: 数据解析和提取
- **Data Transformation**: 数据转换和清洗
- **Content Generation**: 内容生成（通常由LLM原生处理）
- **File Operations**: 文件操作
- **Message Delivery**: 消息传递
- **Scheduling**: 任务调度
- **Authentication**: 身份验证
- **Database Operations**: 数据库操作
- **Code Execution**: 代码执行
- **Version Control**: 版本控制
- **Testing**: 测试自动化
- **Deployment**: 部署操作
- **Monitoring**: 监控和告警

## 模型配置策略

### 默认模型分配
- **通用成员**: 使用主模型 (`bailian/qwen3-max-2026-01-23`)
- **安全专家 & 质量专家**: 优先使用编码专用模型 (`bailian/qwen3-coder-plus`)
- **回退机制**: 当编码专用模型不可用时，自动使用主模型

### 当前成员模型配置
- **SecuritySam**: `bailian/qwen3-coder-plus` (安全审计涉及代码分析)
- **ComplianceChris**: `bailian/qwen3-max-2026-01-23` (合规检查主要为文本处理)
- **ArchitectAva**: `bailian/qwen3-max-2026-01-23` (架构分析主要为系统设计)
- **StructureSteve**: `bailian/qwen3-max-2026-01-23` (系统结构主要为架构设计)
- **QualityQuinn**: `bailian/qwen3-coder-plus` (代码质量分析需要编码能力)
- **ReviewerRachel**: `bailian/qwen3-coder-plus` (代码审查需要编码能力)

## 兼容性

- **完全兼容** reflectt/agent-team-kit 的文件格式
- **向后兼容** 现有的 Agent Teams 工作流
- **支持** OpenClaw 所有版本
- **集成** super-skills 的任务分解和能力识别功能