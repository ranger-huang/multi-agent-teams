# AIDevOps Multi-Team Collaboration Workflow

Advanced multi-team collaboration workflow specifically designed for AIDevOps projects, incorporating Discovery/Coordination layer and complete Executor teams.

## Workflow Structure

### Phase 1: Discovery & Coordination (Linear Intake)
```
CloudExplorerAlex (Discoverer) → DevOpsPilotMaya (Facilitator)
```

### Phase 2: Parallel Execution (Multi-Team Analysis)
```
ArchitectureTeam ──┐
SecurityTeam   ├──→ DevelopmentTeam → Quality Gates → Final Delivery  
DevelopmentTeam ──┘
QualityTeam    ──┘
```

## Team Composition

### Coordination Layer
- **CloudExplorerAlex**: Cloud Native/AI/DevOps Domain Expert (Discoverer)
- **DevOpsPilotMaya**: Task Assignment Coordinator (Facilitator)

### Executor Teams (执剑人 - Executors)
- **Architecture Team**: ArchitectAva, StructureSteve
- **Security Team**: SecuritySam, ComplianceChris  
- **Development Team**: DevBuilderAlex, DevCoderSam
- **Quality Team**: QualityQuinn, ReviewerRachel

## Integration with Spec-Kit (SDD) Workflow

This workflow integrates with the Spec-Driven Development (SDD) cycle:

1. **Constitution Phase**: Discoverer identifies project constraints and requirements
2. **Specification Phase**: Architecture team creates detailed specifications  
3. **Planning Phase**: All teams contribute to comprehensive planning
4. **Implementation Phase**: Development team executes with quality/security oversight
5. **Review Phase**: Quality team validates against specifications
6. **Delivery Phase**: Facilitator coordinates final delivery and handoff

## State Management

- **BACKLOG.md**: Contains ready tasks for all executor teams
- **STATUS.md**: Tracks active work across all teams
- **OPPORTUNITIES.md**: Shared discovery repository managed by Discoverer
- **HEARTBEAT.md**: Automated checks and proactive actions for team coordination

## Model Configuration

- **Primary Model** (`{{PRIMARY_MODEL}}`): Used by Discoverer and Facilitator for general tasks
- **Coding Model** (`{{CODING_MODEL}}`): Used by all Executor teams for specialized technical work

## Quality Gates

- Cross-team validation of findings
- Acceptance criteria verification by Quality team
- Security and compliance validation by Security team
- Architecture consistency checks by Architecture team
- Implementation quality assurance by Development team

## Escalation Rules

- Blocked tasks escalated after 24 hours
- Priority conflicts resolved by Facilitator
- Technical disagreements resolved through evidence-based discussion
- Strategic decisions escalated to human stakeholders