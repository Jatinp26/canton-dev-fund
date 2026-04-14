## Development Fund Proposal

**Author:** Canton Foundation  
**Status:** Draft  
**Created:** 2026-04-15  
**Label:** node-deployment-operations

**Champion:** Canton Foundation

## Abstract

Canton Foundation will deploy and operate 3–4 dedicated DevNet validator nodes, exposing rate-limited JSON Ledger API endpoints. Access credentials will be issued by DevRel/BD staff after a qualification review (project legitimacy, use case fit, no bad actors). Endpoints will not appear in public documentation or on the Canton website. The Keys will be revoked after the Partner Whitelisting is done / Hackathon event is over i.e Foundation will give a limited validity time key which will be automatically revoked after that time of 14 days and after that once whitelisted, developers will continue on their own whitelisted IP. The qualification bar is intentionally low, the goal is to eliminate the timing friction of onboarding and Building.

## Specification

### 1. Objective

Every new Canton developer whether an ecosystem partner, hackathon team, or early-stage project must go through validator IP whitelisting before they can make a single API call against DevNet. Even for DevNet, this process involves submitting an IP, waiting for super validators to adopt updated config files, and a ~14 days approval window. For mainnet and testnet the wait is unavoidable, but for DevNet this delay causes friction on onboarding / lack of interest. 

This blocks two concrete use cases:

1. **Early-start Partners** that want to start into their development Prep. while their validator whitelisting is processing.
2. **Hackathons** where teams have 24–32 hours to build and cannot wait for DevNet.

Moreover, adding to more facts to the problem support, Foundation members have seen friction to continue retention of early start projects, this problem extends into developer adoption initiatives too such as an example of ETH Denver hackathon where foundation had put a bounty but majorly trying to find a way around by hosting devnet nodes and share via static IPs, yet the friction to handle this nature of network access still become a major pain point, check detailed report here: [ETH Denver Hackathon Report on Dev Challenges - Google Docs](https://docs.google.com/document/d/1LKY1opIGqP6RJwe9ukQ-5TjJVt8VLAQCUpELgy91vSE/edit?tab=t.0)

### 2. Implementation Mechanics

**Infrastructure:**

- 3 – 4 validator nodes deployed on Canton DevNet, meeting standard requirements.
- Nodes operated and maintained by Canton Foundation or a trusted NaaS provider under Foundation direction.

**Access control:**

- API key issuance managed by DevRel/BD team via an internal tracking sheet.
- Per-key rate limits enforced at the API gateway layer (requests/minute, transaction volume caps, and more!)
- Keys scoped to DevNet only, non-transferable, revocable
- Revoking API Endpoints allocated after the Partner Whitelisting is completed.

**What this is not:**

- Not a public sandbox, no open registration, no docs listing
- Not a replacement for running your own validator /  Working with a NaaS, projects are expected to run their own node / Setup a NaaS for TestNet/MainNet and Get whitelisted for DevNet.
- It's not mainnet or testnet infrastructure, only for DevNet.

**Adoption and Access** (Access to these endpoints will not be publicly listed.)

- **Hackathons:** Canton Foundation sponsoring a hackathon will pre qualify all participating teams and issue keys at event kickoff and will be auto revoked by end of the event.
- **Inbound ecosystem projects:** BD qualifies projects during initial discovery calls, promising early start projects receive keys while their own validator whitelisting processes / NaaS setup process gets done, removing overall onboarding frction on DevNet.

## Milestones and Deliverables

### Milestone 1: Node Deployment
- **Estimated Delivery:** Weeks 1 – 3
- **Focus:** Deploy 3 – 4 DevNet validator nodes
- **Deliverables / Value Metrics:** 3 – 4 DevNet validator nodes live, passing standard health checks, connected to DevNet synchronizer

### Milestone 2: Setup Infra and Access Control Guidelines
- **Estimated Delivery:** Weeks 3 – 4
- **Focus:** API gateway and rate limiting setup
- **Deliverables / Value Metrics:** API gateway deployed with per-key rate limiting

### Milestone 3: Pilot Cohort
- **Estimated Delivery:** Week 4-6
- **Focus:** First pilot projects onboarded and Hackathon Testing done
- **Deliverables / Value Metrics:** Usage telemetry report shared with Tech & Ops Committee

### Milestone 4: 12 Month Operations
- **Focus:** Ongoing operations
- **Deliverables / Value Metrics:** Ongoing node operation, upgrades, key management, quarterly usage reports to Tech & Ops Committee

## Acceptance Criteria

The Tech & Ops Committee will evaluate completion based on:

- Deliverables completed as specified for each milestone
- Demonstrated functionality or operational readiness
- Alignment with stated value metrics

## Funding

**Total Funding Request:** $50,000

### Payment Breakdown by Milestone

| Category | Amount | Detail |
| :---- | ----- | :---- |
| **Node Infrastructure (Setup)** | $6,000 | Initial provisioning of 4 validator nodes i.e compute instances, managed PostgreSQL databases, static IPs, TLS certificates, DNS configuration |
| **Node Infrastructure (12 mo ops)** | $15,000 | Ongoing hosting for compute + DB + network + storage for 4 Nodes. |
| **API Gateway & Monitoring** | $6,000 | API gateway setup + 12-month licensing/ops including rate limiting, key management, request logging, abuse detection |
| **DevOps Time (Setup)** | $6,000 | API gateway integration & rate limit tuning, monitoring/alerting setup. |
| **DevOps Time (12-mo ops)** | $10,000 | ongoing for node upgrades to track DevNet releases, key issuance/revocation, incident response, quarterly telemetry reports. |
| **Team for Coordination and Management** | $5,000 | Qualification review for inbound projects, hackathon key distribution & Support by Foundation, partner onboarding calls + Support |
| **Buffer** | $2,000 | Unforeseen infrastructure scaling, DevNet reset recovery, additional node if demand exceeds capacity |
| **Total** | **$50,000** | |

## Co-Marketing

Foundation will handle the Marketing needs of the Initiative but there is no Major "Marketing" required but on this one as it's an internal service for better dev adoption and onboarding.