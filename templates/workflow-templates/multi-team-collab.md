# Multi-Team Collaboration Workflow Template

## Overview
Designed for enterprise-scale projects requiring multiple specialized teams to work together. Each team has its own focus area but coordinates through shared processes and communication channels.

## When to Use
- Large enterprise applications with multiple domains
- Projects requiring specialized expertise (security, architecture, compliance, etc.)
- Cross-functional initiatives spanning multiple business areas
- Complex systems requiring comprehensive analysis from multiple perspectives

## Team Structure
```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│ Architecture    │    │ Security &      │    │ Quality &       │
│ Team            │    │ Compliance      │    │ Testing         │
│                 │    │ Team            │    │ Team            │
└─────────────────┘    └─────────────────┘    └─────────────────┘
        │                      │                      │
        └──────────┬───────────┴───────────┬──────────┘
                   │                       │
           ┌───────▼───────┐     ┌───────▼───────┐
           │ Coordination  │     │ Integration   │
           │ Team          │     │ Team          │
           └───────┬───────┘     └───────┬───────┘
                   │                       │
                   └──────────┬────────────┘
                              │
                    ┌─────────▼─────────┐
                    │ Delivery Team     │
                    └───────────────────┘
```

## Team Responsibilities

### Architecture Team
- System architecture analysis
- Dependency mapping
- Technical debt assessment
- Migration path planning

### Security & Compliance Team  
- Security vulnerability scanning
- Compliance requirement validation
- Risk assessment and mitigation
- Security architecture review

### Quality & Testing Team
- Code quality analysis
- Test coverage assessment
- Best practices validation
- Performance bottleneck identification

### Coordination Team
- Inter-team communication facilitation
- Dependency management
- Timeline coordination
- Resource allocation

### Integration Team
- Cross-team finding synthesis
- Integration point validation
- End-to-end flow analysis
- System-wide impact assessment

### Delivery Team
- Final report compilation
- Executive summary creation
- Stakeholder communication
- Action item tracking

## Workflow Phases

### Phase 1: Team Formation & Planning (15 minutes)
- Assign team members from member pool
- Establish inter-team communication channels
- Define shared success criteria
- Set up process files and coordination mechanisms

### Phase 2: Parallel Team Execution (30-60 minutes)
- Each team executes their specialized analysis
- Regular coordination checkpoints every 15 minutes
- Shared status updates in central `process/STATUS.md`
- Cross-team discovery sharing in `process/OPPORTUNITIES.md`

### Phase 3: Integration & Synthesis (15-20 minutes)
- Integration team combines findings from all teams
- Coordination team resolves conflicts and dependencies
- Unified priority framework established
- Cross-cutting recommendations developed

### Phase 4: Delivery & Handoff (10 minutes)
- Delivery team creates final comprehensive report
- Executive summary with key findings and recommendations
- Detailed action items with owners and timelines
- Follow-up coordination plan established

## State Management

### Central Process Files
- `process/BACKLOG.md`: Contains tasks for all teams with team assignments
- `process/STATUS.md`: Tracks status across all teams with team-specific sections
- `process/OPPORTUNITIES.md`: Shared discovery repository for all teams
- `process/HEARTBEAT.md`: Multi-team coordination heartbeat checks

### Team-Specific Files
- Each team maintains their own working directories
- Team-specific reports are consolidated by Integration team
- Cross-team dependencies documented in shared dependency matrix

## Communication Protocol

### Status Updates
- All teams update `process/STATUS.md` every 15 minutes
- Critical blockers escalated immediately to Coordination team
- Daily standup equivalent through file-based updates

### Decision Making
- Team-level decisions made autonomously
- Cross-team decisions require Coordination team facilitation
- Strategic decisions escalated to human lead
- Consensus required for system-wide changes

### Conflict Resolution
- Technical conflicts resolved through evidence-based discussion
- Priority conflicts resolved by Coordination team using business impact criteria
- Resource conflicts resolved through Coordination team mediation
- Escalation path: Team → Coordination → Human Lead

## Success Criteria
- [ ] All teams complete their specialized analysis
- [ ] Cross-team dependencies properly identified and managed
- [ ] Integrated findings provide comprehensive system view
- [ ] No conflicting recommendations between teams
- [ ] Final delivery meets stakeholder requirements
- [ ] Action items are clear, prioritized, and assigned

## Failure Handling
- Individual team failures don't block other teams
- Coordination team manages impact of partial team failures
- Partial delivery possible with clear scope limitations
- Retry mechanisms for failed team analyses
- Human lead intervention for critical coordination failures