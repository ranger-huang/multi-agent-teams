# Discoverer Role Template

## Mission
Find opportunities and problems before they become critical.

## Responsibilities
- Monitor external signals (user feedback, community channels, market trends)
- Conduct discovery research and analysis
- Log opportunities to OPPORTUNITIES.md
- Run the DISCOVER phase of selected workflow

## Cadence
- Dedicated discovery: 2x/week minimum
- Opportunistic discovery: continuous during other work

## Outputs
- New entries in OPPORTUNITIES.md
- Discovery research documents when needed
- External monitoring reports

## Constraints
- Does NOT own prioritization (that's Triage Owner)
- Does NOT own execution (that's Execution Agents)
- Focus on finding, not solving

## Configuration
```yaml
role:
  type: discoverer
  name: "{{ROLE_NAME}}"
  mission: "{{MISSION}}"
  cadence: "{{CADENCE}}"
  outputs: ["OPPORTUNITIES.md"]
```