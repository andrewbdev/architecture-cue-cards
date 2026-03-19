# Production First Metholodgy

We always think about a live system when coding and developing features or building Greenfield

We are pragmatic when doing features, we build enough to meet client needs and what has value in Production

We should build or improve upon the existing client frameworks around the key areas listed below

## Key areas

### Deployability

**Can the system be quickly redeployed?**

* Release management/release process/CAB ie. tracking what is live
* Runbooks and KOPs
* Documentation
* Build assets 
* Deployment pipelines
* Infrastructure as code
* Data Backups 
* Database migrations
* Disaster Recovery plans and regular tests to check restoration is successful including data backups
* Chaos testing
* DR Strategy - Failover etc

### Security

**Is the system safe from any threats?**

**Is access secured?**

**Do we correctly limit areas of the system based on the users roles?**

* Threat monitoring 
* Pen-testing
* DevSecOps
* Secure coding practices 
* OWASP top 10
  * Cookies - HTTPOnly, Secure, Samesite strict/lax
  * Validate/sanitise inputs
  * Prevent XSS
* Secret scanning in pipelines
* Package scanning
* DAST tooling
* Authentication and authorization of users
* Role and permission management 
* Session management 
* Security monitoring 
* Cloud/on prem access to servers/databases/Cloud services use Principal of least privilege 
* Use of WAF/Firewalls
* User provisioning - SCIM
* Joiners/Movers/Leavers process

### Monitoring/Logging

**Can we see how the system is performing, and what it is doing?**

* Logging in services and applications
* Alerts
* Visulation tools
* Log retention
* Removing user data in logs
* Can the logs be successfully used by Operations?
* Cost of running both prod and non-prod - Can we turn off services that are not requried?

### Data

**What data do we hold, where is it, and how is it used?**

* Data soventity
* Data encryption - customer or platform managed keys?
* Data catalogues
* Data regulations ie. DPIA
* Maintain database schemas separate from the data/database
* Documentation on the transforms/logic performed on the data, it governance, and services accessing it.
* ERD diagrams
* Mock data for testing

### System functionality

**Can we easily maintain system features/functionality, and easily add new features now and in the future?**

* Code repositories
* Branching stategies
* PR review strategy
* Tests
  * Unit
  * Integation
  * E2E
* Build pipelines
* Use of AI Agents for coding
* Loosly coupled code and services
* Environments
  * Dynamic or developer environment
  * Integration environment
  * UAT environment
  * Pre-prod
  * Production
* Meet client governance around coding standards and approved technologies (ie. tech radar)
* Can easily build and run solution locally
* Ensure Team follows guideance
* Team shape and experience
* NFRs
* KDDs or Architecture decision records
* Consistant Tech Stacks
* Is the dev exp of a high-quality?
* System architecture and decomposition ie. what architecture patterns or styles to use?
* Code quality tools ie. Linters and SONARCube.
* Documentation covering both architecuture and code
* Accessibility - WCAG / ARIA
* Package managers to control access to 3rd party libraries

## Other concerns

### Meeting with team/TLs/TAs

* How are the team doing?
* Any blockers
* Any issues?
* Feedback any upstream design decisions or new areas of work

### Security Incident

* Root cause analysis
* Any proven exploits - from monitoring/logging data
* Risk analysis - How much risk is it to the business?
* Inform the relevant people in the business this as happened.
* Create solution
* Deploy solution 
* Provide necessary commuications 
* Document and de-brief

## Making decisions

### Understand the context/ask

* Business value/need
* Requirements both functional and non-functional
* Timescales/Cost and Budget
* Risks
* Team structure and knowledge

### Decide on a technical solution

* Setup an architecture review group
  * Key technical people on the project - EA/TA/TLs
* Review decisions 
  * Technical solutions
  * ADRs or KDDs
* Group sets up a framework to submit proposals and presenet this to the teams
* Group sets up a tech radar to show acceptable techologies and architectual patterns/approaches
* Process:
  1. Technical solution or ADR written
  2. Emailed to the group
  3. (Optional) Meeting setup to discuss proposal
  4. (Optional) Changes requested
  5. Approved
* All proposals are open for all to see

* Documents
  * Describe business or technical problem being solved
  * Show reqirements
    * Team restrictions
    * Timescales
    * Costs
    * Client/project technical restrictions or requirements
    * NFRs
    * IG/Legal requirements
   * List options
    * Show why each ones does/does not meet the requirements
    * Consider - SaaS, White label, Cloud products / services, Configurable package framework, Bespoke or custom written. 
### Diagram link checking
 * Security
  * What data encryption is used? ie. HTTPS/TLS
  * What cyper suites are used?
  * What certificate checks are in place?  Standard TLS or mTLS?
 * Authentication/Authorization
  * How can we verify requests have come from specific sender ie. webhooks using secrets and HMAC; or Bearer tokens
 * Protocol
  * What protocol is used? ie. HTTP/RPC/REST/GraphQL
  * What is the schema/structure of the payloads?
  * Is it synchronous or asynchronous?
  * Time for a response to be sent back
 * Reliency
  * What happens if the sender fails to send the request?
  * What happens if the receiver fails when processing the request? ie. think about retries from the sender
  * What happens if the sender does not receieve the response from the reciever
  * How does the receiver deal with multiple requests containing the same data or operation? ie. idempotency
 
