# Business Continuity Planning/ Disaster Recovery (BCP/DR)
Assessing risks to the organizational processes and creating polices, plans and procedures to minimize the
impact if the risks were to occur. 

_Seat of the pants_ attitude is one of the most common arguments against committing resources to BCP. 

## Key Concepts
- **fail secure**: system that when fails will block all access
- **fail open**: system that when it fails will grant access
- **Max Tolerable Outage (MTO)**: Maximum tolerable outage of the business
- **Max Tolerable Downtime (MTD)**: Max tolerable downtime of a system
- **Cold Site**: facility to use without being in full working order
- **Hot Site**: fully functional with infrastructure and all data
- **Warm Site**: fully funtional but without data
- **Service Bureau**: Bit outdated, facilty that leases compute time
- **Mutual Assistance Agreement (MAA)**: Firms agree to help each other during a disaster
- **Full Backup**: All items backed up, archive bit set back to 0 after
- **Incremental Backup**: Only changed files backed up, archive bit set to 0 after
- **Differential Backup**: All changed files backed up and archive bit not changed
- **Software Escow Arrangement**: Third party dev firm periodically stores copy of code with escrow agent,
  if they go under the ownership transfers to the escrow agent and customer
- **Read Through Test**: read and update BCP
- **Structured Walk Through (aka Table Top)**: Role play scenarios around the BCP
- **Simulation Test**: Same as Structured, but response measures are tested
- **Parallel Test**: Full test on a parallel/staging environment
- **Full Interuption Test**: Full test on production system



## Project Scope and Planning
- Structed analysis of org from crisis perspective
- create a BCP team with leadership approval
- assess resouces available to participate in BCP
- analyze legal and regulatory framework

### Business Org Analysis
- What operational departments are responsible for the core business services
- What support services help these operational departments?
- What is the structure of the security teams?
- Which senior executives and key individuals are needed for the ongoing viability of the organization?

### BCP Team Selection
- Representatives from the organziational departments supporting core services
- Business folks who are essential to the organization
- IT Folks
- Security Folks
- Legal help, attorneys who are knowledgeable about the legal, regulatory, and contractual responsibilities
- HR folks who can address staffing issues
- Public Relations folks to communicate in the event of a problem
- Senior Management to set the vision, define priorities, and allocate resources. Fiduciary reponsiblities
  require senior management presence. 

### Resource Requirements
Need resources for the following: 
- BCP Development
- BCP Testing, Training and Maintenance
- BCP Implementation
  
## Business Impact Assessment
Identifies the sources critical to the organziations viability

- Identify Priorities
  - Map out Asset Value (AV)
  - determine Maximum Tolerable Downtime (MTD)
  - Identify Recovery Time Objective (RTO)
 
- Risk Identificaion
  - Map out risks
 
- Likelihood Assessment
  - What of the risk will happen
  - Use Annualized Risk Occurence (ARO)
 
- Impact Assessment
  - Refer to [Risk Management](docs/RISKMANAGEMENT.md) for more information on these terms
  - SLE = AV * EF
  - ALE = SLE * ARO
 
- Resource Prioritization
  - Sort them by ALE
  - Use common sense to adjust rating for special cases
 
## Continuity Planning
- Strategy Development
- Provisions and processes
- Plan Approval
- Plan implementation
- Training and Education

## BCP Documentation/artifacts
- Statement of Importance
- Statement of Priorities
- Statement of Organizational Responsiblity
- Stagment of Urgency and timing
- Risk Assessment
- Risk Acceptance or Mitigation
- Vital reocrds - where are vital records stored
- Emergency Response Guidelines
- Maintenance
- Testing and Exercises
