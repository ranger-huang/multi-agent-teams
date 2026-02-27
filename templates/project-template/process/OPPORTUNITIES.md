# Multi-Agent Teams Opportunities Discovery

*Shared repository for all team members to log discoveries, ideas, and new work opportunities*

## Discovery Guidelines

### Who Can Add
- **ANY TEAM MEMBER** can add opportunities
- **EXTERNAL SOURCES** can be logged by any team member who encounters them
- **AUTOMATED SYSTEMS** can add opportunities through heartbeat checks

### When to Add
- During regular work when you notice something
- From external monitoring (user feedback, community channels, etc.)
- From system alerts and heartbeat checks  
- From completed work retrospectives
- From cross-team collaboration sessions

### Format Requirements
```markdown
### [Opportunity Name]
**Discovered**: YYYY-MM-DD HH:MM
**Discovered By**: [Team Member Name]
**Source**: [External/Internal/Automated]
**Team**: [Relevant Team - Architecture/Security/Quality/etc.]
**Priority**: [High/Medium/Low]
**Description**: [Clear description of the opportunity or problem]
**Impact**: [Business/Technical impact if addressed]
**Suggested Action**: [Rough idea of what should be done]
**Related Files**: [Relevant files or documentation]
**Dependencies**: [Any blocking dependencies]
```

## Active Opportunities

### High Priority Opportunities

### [Critical Security Vulnerability]
**Discovered**: 2026-02-27 02:30
**Discovered By**: SecuritySam
**Source**: Automated scanning
**Team**: Security
**Priority**: High  
**Description**: Critical vulnerability found in authentication module
**Impact**: Potential unauthorized access to user data
**Suggested Action**: Immediate patch and security audit
**Related Files**: /src/auth/module.js
**Dependencies**: None

### Medium Priority Opportunities

### [Architecture Documentation Gap]  
**Discovered**: 2026-02-27 02:30
**Discovered By**: ArchitectAva
**Source**: Internal review
**Team**: Architecture
**Priority**: Medium
**Description**: Missing architecture documentation for payment processing module
**Impact**: New developers struggle to understand payment flow
**Suggested Action**: Create comprehensive architecture diagram and documentation
**Related Files**: /docs/architecture/, /src/payment/
**Dependencies**: None

### Low Priority Opportunities

### [Code Style Inconsistency]
**Discovered**: 2026-02-27 02:30  
**Discovered By**: QualityQuinn
**Source**: Code review
**Team**: Quality
**Priority**: Low
**Description**: Inconsistent code formatting in utility functions
**Impact**: Minor readability issues
**Suggested Action**: Apply consistent code formatting rules
**Related Files**: /src/utils/*.js
**Dependencies**: None

## Processed Opportunities

### Recently Triaged (Moved to BACKLOG)
- [List of opportunities moved to Ready queue]

### Parked Opportunities  
- [Good ideas that are not ready for implementation]

### Killed Opportunities
- [Ideas that were evaluated and rejected]

## Discovery Sources

### External Monitoring
- User feedback channels
- Community forums and discussions  
- Social media mentions
- Competitor analysis
- Market trend reports

### Internal Signals
- Build failures and test results
- Performance monitoring alerts
- Security scanning results
- Code quality metrics
- Team retrospective findings

### Automated Discovery
- Heartbeat-driven checks
- Scheduled analysis tasks
- Integration test results
- Dependency update notifications
- Compliance requirement changes

## Discovery Cadence

### Regular Discovery Sessions
- **Daily**: Quick scan during routine work
- **Weekly**: Dedicated discovery session (2x per week recommended)
- **Sprint Boundaries**: Comprehensive discovery during planning
- **Post-Release**: Discovery from release retrospectives

### Opportunistic Discovery
- Log immediately when discovered
- Don't wait for scheduled sessions
- Capture context while it's fresh

## Triage Integration

### Ready for Triage
Opportunities remain here until triaged by the Triage Owner.

### Triage Criteria
- Clear scope and outcome definition
- Reasonable size estimation
- No blocking dependencies  
- Alignment with current priorities
- Sufficient information for execution

### Triage Process
1. Triage Owner reviews opportunities regularly
2. Applies triage criteria to each opportunity
3. Moves to appropriate destination:
   - **READY**: Move to BACKLOG.md Ready section
   - **BLOCKED**: Move to BACKLOG.md Blocked section  
   - **PARK**: Keep in OPPORTUNITIES.md with Parked status
   - **KILL**: Remove from OPPORTUNITIES.md

---

*This file is the single source of truth for all discovered opportunities. If it's not logged here, it doesn't exist in the system.*
*Last updated: {{TIMESTAMP}}*