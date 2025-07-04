# Production First Metholodgy


We always think about a live system when coding and developing features or building Greenfield

We are pragmatic when doing features, we build enough to meet client needs and what has value in Production

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


### Security

**Is the system safe from any threats?**

**Is access secured?**

**Do we correctly limit areas of the system based on the users roles?**

* Threat monitoring 
* Pen-testing
* DevSecOps
* Secure coding practices 
* OWASP top 10
** Cookies - HTTPOnly, Secure, Samesite strict/lax
** Validate/sanitise inputs
** Prevent XSS
* Secret scanning in pipelines
* Package scanning
* DAST tooling
* Authentication and authorization of users
* Role and permission management 
* Session management 
* Security monitoring 
* Cloud/on prem access to servers/databases/Cloud services use Principal of least privilege 
* Use of WAF/Firewalls 