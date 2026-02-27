# Multi-Agent Teams Heartbeat Configuration

*Automated checks and proactive operations to keep the team running smoothly*

## Heartbeat Philosophy

The heartbeat system enables **self-sustaining team operation** without human intervention. It continuously monitors team health, triggers automated actions, and maintains workflow momentum.

## Core Principles

### ✅ Do
- **Check regularly**: Run checks at appropriate intervals
- **Act automatically**: Trigger actions when conditions are met  
- **Escalate appropriately**: Know when to involve human leads
- **Log everything**: Maintain audit trail of all actions
- **Be proactive**: Don't wait for problems to become critical

### ❌ Don't  
- **Just return OK**: Actually perform meaningful checks
- **Create bottlenecks**: Enable self-service wherever possible
- **Ignore stale work**: Actively monitor for stuck tasks
- **Forget discoveries**: Ensure opportunities are captured and processed
- **Assume everything is fine**: Verify system health continuously

## Heartbeat Checks Configuration

### BACKLOG Health Checks
```yaml
check: "BACKLOG.md Ready section not empty"
interval: "15 minutes"
action: "notify available team members of ready tasks"
priority: "medium"

check: "BACKLOG.md Blocked section has items > 24 hours"
interval: "30 minutes" 
action: "escalate to Facilitator for unblocking"
priority: "high"

check: "BACKLOG.md Ready section empty for > 2 hours"
interval: "1 hour"
action: "trigger Discoverer to find new opportunities"
priority: "medium"
```

### STATUS Freshness Checks
```yaml
check: "STATUS.md has tasks with no updates > 24 hours"
interval: "1 hour"
action: "escalate to Facilitator for reassignment"
priority: "high"

check: "STATUS.md shows multiple agents claiming same task"
interval: "5 minutes"
action: "trigger conflict resolution protocol"
priority: "critical"

check: "STATUS.md workflow phase completed but not progressed"
interval: "30 minutes"
action: "trigger next phase automatically"
priority: "medium"
```

### OPPORTUNITIES Activity Checks
```yaml
check: "OPPORTUNITIES.md has new entries not triaged > 1 hour"
interval: "15 minutes"
action: "notify Triage Owner to process new opportunities"
priority: "medium"

check: "OPPORTUNITIES.md empty for > 24 hours"
interval: "6 hours"
action: "trigger Discoverer discovery session"
priority: "low"
```

### Team Health Checks
```yaml
check: "Team velocity below threshold (tasks/day)"
interval: "4 hours"
action: "analyze bottlenecks and suggest improvements"
priority: "medium"

check: "Error rate above threshold in completed tasks"
interval: "2 hours"
action: "trigger quality review and process adjustment"
priority: "high"

check: "Communication gaps between teams detected"
interval: "1 hour"
action: "facilitate inter-team coordination session"
priority: "medium"
```

## Automated Actions Library

### Task Management Actions
- `assign_task_to_agent(agent, task)`: Assign specific task to available agent
- `reassign_stale_task(task, new_agent)`: Move stuck task to new agent
- `create_ready_task_from_opportunity(opportunity)`: Convert opportunity to ready task
- `escalate_blocked_task(task, owner)`: Escalate blocked task to appropriate owner

### Team Coordination Actions  
- `notify_team_members(message, priority)`: Send notification to relevant team members
- `trigger_discovery_session(team)`: Start discovery session for specific team
- `facilitate_conflict_resolution(tasks)`: Handle task claiming conflicts
- `coordinate_inter_team_dependencies(dependencies)`: Manage cross-team dependencies

### Quality Assurance Actions
- `validate_task_completion(task)`: Verify task completion meets standards
- `trigger_quality_review(work)`: Initiate quality review process
- `generate_performance_metrics()`: Create team performance reports
- `suggest_process_improvements(metrics)`: Recommend workflow optimizations

### Escalation Actions
- `escalate_to_human_lead(issue, priority)`: Escalate to human for strategic decisions
- `request_additional_resources(need)`: Request more team members or resources
- `pause_workflow_for_intervention(reason)`: Temporarily pause workflow for fixes
- `activate_contingency_plan(scenario)`: Execute backup plans for critical failures

## Heartbeat Execution Rules

### Priority Handling
- **Critical**: Execute immediately, escalate if not resolved in 5 minutes
- **High**: Execute within 15 minutes, escalate if not resolved in 1 hour  
- **Medium**: Execute within 1 hour, escalate if not resolved in 4 hours
- **Low**: Execute within 4 hours, no escalation needed

### Resource Management
- Limit concurrent heartbeat actions to prevent resource exhaustion
- Prioritize actions based on business impact and urgency
- Queue lower priority actions when system is busy
- Monitor action execution time and optimize slow processes

### Failure Handling
- Retry failed actions with exponential backoff
- Log all action failures with detailed error information
- Escalate persistent failures to human lead
- Maintain system stability even when individual actions fail

## Integration Points

### With Other Process Files
- **BACKLOG.md**: Read task status, update task assignments
- **STATUS.md**: Monitor work progress, update execution status  
- **OPPORTUNITIES.md**: Process new discoveries, update opportunity status
- **Team Configuration**: Read team structure, member assignments, workflows

### With External Systems
- **Notification Systems**: Send alerts and updates to team members
- **Monitoring Tools**: Integrate with external monitoring and alerting
- **Project Management**: Sync with external project management tools
- **Communication Platforms**: Post updates to team communication channels

## Customization Guidelines

### Project-Specific Heartbeats
Projects can override default heartbeat configuration by creating their own `process/HEARTBEAT.md` with custom checks and actions.

### Team-Specific Heartbeats
Different teams can have different heartbeat configurations based on their workflow and requirements.

### Domain-Specific Heartbeats
Specialized domains (security, architecture, etc.) can add domain-specific heartbeat checks.

### Scaling Heartbeats
For large projects with many teams, heartbeat intervals can be adjusted to prevent system overload.

---

*The heartbeat system is the engine that keeps multi-agent teams running autonomously. Configure it thoughtfully and let it work.*
*Last updated: {{TIMESTAMP}}*