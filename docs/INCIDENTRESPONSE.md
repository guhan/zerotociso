# Incident Response

## Steps
- Preparation
- Detection
- Response
- Mitigation
- Reporting
- Recovery
- Remediation
- Lessons Learned (Postmortem)


## Procedure
### Preplanning 
Before an incident get the following in place:
  - Monitoring
  - secure SDLC
  - Encryption for data at rest
  - Encryption for data in transit
  - RBAC
    - IAM audits
  - Recurring Pen Tests
  - Incident Response plan
    - Identify and prioritize critical assets and data.
    - Establish an incident response team with defined roles and responsibilities.
    - Outline procedures and protocols
      - Runbooks
    - Define communication channels and escalation procedures.
    - Conduct regular training and exercises to ensure the team is well-prepared.
      
### Triage
- Incident is triggered
  - automated notification
  - manual notification

- Confirm assignment of roles
  - Incident responders: Does technical work to resolve incident
  - Incident manager: reports on progress, documents incident, shields incident responders
  - Define other roles if needed
 
- Assess situation
  - Blast Radius
  - What happened
  - Timeline

- Start Documenation
  - RCA
  - Postmortem Doc
    
### Resolution
- Loop in stakeholders
  - put up maintenance notifaction
  - stakeholder escalation list
  - notify leadership if needed
 
- Use Runbook
  - Preserve logs
  - Take systems offline
  - Find fix for issue

- Deployment
  - Test resolution
  - Deploy fix
  - Update maintenance notifcation
 
- Compliance notifications
  - Notify outside parties if needed
    - Law enforcement
    - Legal
    - Industry (Threat Intel, -ISAC)
  - Notify customer, if contract clause impacted
 
### Post Incident
- Post Mortem
  - Additional controls
  - Additional Telemetry
  - Additional processes

- Add incident to table top exercise

