# Home Healthcare Routing & Scheduling Problem
## Prescriptive Analytics with Mathematical Programming

## Overview
This project formulates and solves a Home Healthcare Routing and Scheduling Problem (HHCRSP) using Mixed Integer Linear Programming (MILP). The objective is to optimise weekly caregiver routing and assignment decisions while respecting clinical, operational, and regulatory constraints.

The model supports decision-making in home healthcare operations by balancing travel cost, workforce utilisation, service quality, and regulatory compliance.

---

## Problem Context
Home healthcare providers must coordinate skilled caregivers to deliver timely patient care under limited resources. Scheduling decisions are constrained by:
- Staff skill compatibility
- Patient time windows
- Shift length regulations
- Workload limits
- Mandatory visit requirements

Manual scheduling struggles to account for these constraints simultaneously, often resulting in inefficient routing and uneven workloads. This project addresses these challenges through mathematical optimisation.

---

## Problem Definition
- **Caregivers:** 10  
- **Patients:** 30  
- **Planning horizon:** 7 days  
- **Depot:** Central start/end location  
- **Objective:** Minimise total operational cost

### Cost Components
- Travel time
- Overtime penalties
- Penalties for unmet mandatory visits

---

## Modelling Approach

### Optimisation Technique
- Mixed Integer Linear Programming (MILP)

### Decision Variables
- Routing decisions between nodes
- Patient–caregiver assignment
- Service start times
- Overtime allocation
- Unattended mandatory visit indicators

### Key Constraints
- Skill compatibility between caregivers and patients
- Daily workload limits (maximum visits per caregiver)
- Shift duration and overtime
- Patient time windows
- Route continuity and depot flow conservation
- Subtour elimination (MTZ formulation)
- Continuity of care limits

---

## Data
Synthetic data was generated to reflect realistic operational conditions:
- Skill-classified caregivers
- Patients with priority levels and time windows
- Distance-based travel times

The use of synthetic data ensures transparency, reproducibility, and controlled experimentation.

---

## Results
- **Solver:** GAMS (NEOS Server)
- **Variables:** 74,221 (69,880 binary)
- **Constraints:** 139,191
- **Solve time:** ~300 seconds

### Optimal Solution Summary
- All 109 mandatory patient visits covered
- No overtime incurred
- No unattended patient penalties
- Total travel time reduced by ~30% compared to non-optimised routing

The solution satisfies all operational and clinical constraints while achieving a lower total cost.

---

## Sensitivity Analysis
Sensitivity tests were conducted on:
- Number of caregivers
- Service duration
- Shift length

### Key Insights
- Staffing levels have a non-linear impact on cost
- Operating below 8 caregivers leads to rapid cost escalation
- Service duration and shift length have limited impact within tested ranges
- Current configuration operates below capacity, indicating potential for service expansion

---

## Model Extensions
The following extensions were conceptually analysed but excluded due to computational complexity and data limitations:
- Multi-caregiver simultaneous visits
- Multiple daily visits per patient
- Stochastic travel times

These extensions would increase realism but significantly raise model size and solver time.

---

## Limitations
- Deterministic travel times
- Synthetic data assumptions
- Weekly planning horizon without demand uncertainty

Results are prescriptive within the defined model scope.

---

## Tools & Technologies
- GAMS
- Python (visualisation and post-processing)(reason we stopped using GAMS because free version doesnt support heavy computing)

---

## Course Context
Prescriptive Analytics with Mathematical Programming  
University of Edinburgh  
Group 9

---

## References
See project report for the complete reference list.
