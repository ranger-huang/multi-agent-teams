# Parallel Analysis Workflow Template

## Overview
Designed for complex analysis tasks that can be broken down into parallel work streams. Multiple team members work simultaneously on different aspects of the same project.

## When to Use
- Complex project analysis requiring multiple perspectives
- Security + Architecture + Quality analysis needed simultaneously  
- Large codebases requiring comprehensive review
- Multi-domain expertise required (security, performance, architecture, etc.)

## Workflow Structure
```
┌─────────────┐
│  ANALYZE    │ ← All analysis phases run in parallel
└─────────────┘
       │
       ▼
┌─────────────┐
│  SYNTHESIZE │ ← Combine findings and create unified report  
└─────────────┘
       │
       ▼  
┌─────────────┐
│  DELIVER    │ ← Final delivery and recommendations
└─────────────┘
```

## Phase 1: ANALYZE (Parallel)
**Duration**: 15-30 minutes
**Participants**: All assigned team members

### Parallel Work Streams
- **Security Analysis**: SecuritySam runs healthcheck and compliance audit
- **Architecture Analysis**: ArchitectAva analyzes system structure and dependencies  
- **Quality Analysis**: QualityQuinn reviews code quality and best practices
- **Documentation Analysis**: ReporterRiley prepares reporting framework

### Coordination Rules
- All members work independently but share findings in real-time
- Use `process/STATUS.md` to track individual progress
- Any member can add discoveries to `process/OPPORTUNITIES.md`
- Facilitator monitors for conflicts or blockers

## Phase 2: SYNTHESIZE  
**Duration**: 5-10 minutes
**Coordinator**: Facilitator or Lead Analyst

### Activities
- Cross-reference findings from all analysis streams
- Identify overlapping issues and priority conflicts
- Create unified assessment with consistent severity ratings
- Resolve any contradictory findings through discussion

### Output Requirements
- Single comprehensive analysis report
- Unified priority list of issues
- Cross-cutting recommendations
- Dependencies between findings documented

## Phase 3: DELIVER
**Duration**: 5 minutes  
**Coordinator**: Documentation Specialist

### Deliverables
- **Main Report**: `analysis-report.md` with executive summary
- **Detailed Findings**: Individual section reports with evidence
- **Action Items**: Prioritized list with owners and timelines
- **Next Steps**: Recommendations for follow-up actions

## State Files
- `process/BACKLOG.md`: Contains analysis tasks for each stream
- `process/STATUS.md`: Tracks parallel execution status
- `process/OPPORTUNITIES.md`: Captures new discoveries during analysis
- `process/HEARTBEAT.md`: Configured for parallel workflow monitoring

## Success Criteria
- [ ] All analysis streams completed successfully
- [ ] Findings synthesized into coherent report
- [ ] No conflicting recommendations
- [ ] Action items are clear and actionable
- [ ] Delivery meets format and quality standards

## Failure Handling
- If one stream fails, others continue
- Facilitator escalates critical failures to human lead
- Partial delivery possible if core streams complete
- Retry mechanism for failed analysis streams