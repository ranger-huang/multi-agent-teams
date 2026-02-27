# Multi-Agent Teams Status Tracking

*Real-time tracking of all team member activities and project progress*

## Active Work

| Team | Agent | Task | Started | Status | ETA |
|------|-------|------|---------|--------|-----|
| {{TEAM_NAME}} | {{AGENT_NAME}} | {{TASK_NAME}} | {{START_DATE}} | 🟡 In Progress | {{ETA}} |

## Completed Work

| Team | Agent | Task | Completed | Status | Output |
|------|-------|------|-----------|--------|--------|
| {{TEAM_NAME}} | {{AGENT_NAME}} | {{TASK_NAME}} | {{COMPLETION_DATE}} | ✅ Completed | {{OUTPUT_FILE}} |

## Blocked Work

| Team | Agent | Task | Blocked Since | Reason | Owner |
|------|-------|------|---------------|--------|-------|
| {{TEAM_NAME}} | {{AGENT_NAME}} | {{TASK_NAME}} | {{BLOCKED_DATE}} | {{REASON}} | {{OWNER}} |

## Team Coordination Status

### Inter-Team Dependencies
| Dependent Team | Dependency | Required From | Status |
|----------------|------------|---------------|--------|
| {{DEPENDENT_TEAM}} | {{DEPENDENCY}} | {{REQUIRED_FROM}} | {{STATUS}} |

### Communication Channels
| Channel | Purpose | Last Activity | Status |
|---------|---------|---------------|--------|
| {{CHANNEL_NAME}} | {{PURPOSE}} | {{LAST_ACTIVITY}} | {{STATUS}} |

## Workflow Progress

### Current Phase: {{CURRENT_PHASE}}
- **Phase Start**: {{PHASE_START_TIME}}
- **Phase End**: {{PHASE_END_TIME}}  
- **Progress**: {{PROGRESS_PERCENTAGE}}%
- **Next Phase**: {{NEXT_PHASE}}

### Phase Completion Checklist
- [ ] {{CHECKLIST_ITEM_1}}
- [ ] {{CHECKLIST_ITEM_2}}
- [ ] {{CHECKLIST_ITEM_3}}

## Heartbeat Status

### Last Heartbeat Check: {{LAST_HEARTBEAT_TIME}}
- **BACKLOG Health**: {{BACKLOG_HEALTH_STATUS}}
- **STATUS Freshness**: {{STATUS_FRESHNESS_STATUS}}  
- **OPPORTUNITIES Activity**: {{OPPORTUNITIES_ACTIVITY_STATUS}}
- **Team Health**: {{TEAM_HEALTH_STATUS}}

### Automated Actions Triggered
| Time | Action | Status | Result |
|------|--------|--------|--------|
| {{ACTION_TIME}} | {{ACTION_DESCRIPTION}} | {{ACTION_STATUS}} | {{ACTION_RESULT}} |

## Escalation Log

### Recent Escalations
| Time | Issue | Escalated To | Resolution Status |
|------|-------|--------------|-------------------|
| {{ESCALATION_TIME}} | {{ISSUE_DESCRIPTION}} | {{ESCALATED_TO}} | {{RESOLUTION_STATUS}} |

## Performance Metrics

### Team Velocity
- **Tasks Completed/Day**: {{TASKS_PER_DAY}}
- **Average Task Duration**: {{AVG_TASK_DURATION}}
- **Blocker Resolution Time**: {{BLOCKER_RESOLUTION_TIME}}

### Quality Metrics  
- **Rework Rate**: {{REWORK_RATE}}
- **Defect Density**: {{DEFECT_DENSITY}}
- **Stakeholder Satisfaction**: {{SATISFACTION_SCORE}}

---

*This file is automatically updated by the multi-agent teams system. Manual edits may be overwritten.*
*Last updated: {{TIMESTAMP}}*