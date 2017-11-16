# acp-security-baseline

## Apprenda Cloud Platform - Security Baseline

### Guidelines

The following security guidelines apply to servers, components, and accounts that constitute an ACP instance. The steps to implement these guidelines vary by hosting environment and provider, but the concepts are the same. Protecting a Platform from compromise involves 1) securing the underlying OS, 2) ACP components and services, and 3) access to the hosting environment both physically and via the network to prevent malicious entities from attacking services/nodes or obtaining access to protected information.

It is recognized that exceptions may be needed, or overwritten by a non-Apprenda provider in on-premises scenarios, for one or more of the outlined guidelines. Exceptions will be reviewed and documented on a case-by-case basis and mitigating actions will be taken to address risk.

#### Access Controls

* Specify guest applications to run under accounts with the least viable privileges (e.g. Virtual Accounts in version 7.1 and beyond)
* Utilize securables in the Account Portal to provide Role-based Access Controls to Developers and Tenants

#### Communications Protection

* Encrypt external and internal Platform application communications using Transport Layer Security certificates
* Rotate TLS certificates regularly 
* Limit network communications to only those ports and protocols required by ACP and its dependencies

#### Identity and Authentication

* Integrate with Identity Federation to use the Security Tokens Services (STSs) provided by your enterprise 
* Rotate AD FS Claims Authenticity (Signing) certificate regularly
* Rotate passwords/credentials for Platform and guest applications regularly

#### Configuration Management

* Run ACP components under accounts with the least viable privileges
* Run underlying ACP "infrastructure" under least viable privileges. Examples include:
  * Windows OS
  * IIS
  * Linux OS
  * Tomcat
  * JBoss
  * Docker
  * AD FS

#### Contingency Planning

* Run ACP components on dedicated nodes in clustered configurations for high availability of services. Components include:
  * SQL Servers
  * Platform Coordinators
  * Load Managers
  * Platform Cache
  * Federation Brokers (AD FS)

#### Maintenance

* Apply patches and updates to Platform nodes using Maintenance and Reserved modes
* Utilize Zero Downtime Platform Upgrades for security patches and updates to the Platform without taking guest applications down during the process