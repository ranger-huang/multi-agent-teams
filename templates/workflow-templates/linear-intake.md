# Linear Intake Workflow Template

## Overview
A self-sustaining 5-phase loop that keeps work moving without bottlenecks.

## Workflow Diagram
```
     ┌─────────────────────────────────────────────────────────┐
     │                                                         │
     ▼                                                         │
┌─────────┐    ┌─────────┐    ┌─────────┐    ┌─────────┐      │
│ DISCOVER│───▶│  TRIAGE │───▶│  READY  │───▶│ EXECUTE │──────┘
│         │    │         │    │         │    │         │
│Discoverer│   │Triage   │    │Self-Srv │    │ Agents  │
└─────────┘    └─────────┘    └─────────┘    └─────────┘
     ▲                                              │
     │              Feedback Loop                   │
     └──────────────────────────────────────────────┘
```

## Phase Details

### Phase 1: DISCOVER
**Owner**: Discoverer role
**Sources**: User feedback, research, build failures, retrospectives, external signals
**Output**: Entries in `process/OPPORTUNITIES.md`
**Format**: 
```markdown
### [Opportunity Name]
**Discovered**: YYYY-MM-DD
**Source**: [where it came from]
**Description**: [what's the opportunity/problem]
**Suggested action**: [rough idea of what to do]
```

### Phase 2: TRIAGE  
**Owner**: Triage Owner role
**Decision Framework**: READY/BLOCKED/PARK/KILL
**Ready Criteria**: Clear outcome, size estimated, no blockers, aligned with strategy
**Output**: Updated `process/BACKLOG.md`

### Phase 3: READY QUEUE
**Location**: `process/BACKLOG.md` Ready section
**Structure**: High/Medium/Low priority sections
**Rules**: First claim wins, respect priority order, no approval needed

### Phase 4: SELF-SERVICE EXECUTION
**Claim Process**: Check queue → Pick task → Claim in STATUS.md → Execute → Complete
**No Bottleneck Rule**: If it's in Ready, it's fair game

### Phase 5: FEEDBACK LOOP
**Owner**: Completing agent
**Actions**: Log completion, capture learnings, spawn new opportunities
**Output**: Updates to DONE section and new OPPORTUNITIES entries

## Best For
- Simple projects
- Single team coordination  
- Linear task dependencies
- Teams familiar with reflectt/agent-team-kit patterns

## Anti-Patterns to Avoid
❌ "[Human] will add it" — Anyone can discover
❌ "Waiting for approval" — Self-serve from Ready
❌ "I'll remember this idea" — Log it or lose it
❌ "This is too small to log" — Small tasks clog brains
❌ "Someone else will notice" — You noticed, you log it