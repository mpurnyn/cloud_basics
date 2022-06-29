# Azure 900 Notes for Test

https://www.youtube.com/watch?v=gH3pwWO0Q9Y


## 1. Describe Cloud Concepts

## Cloud Models and Services
**Shared Responsibility Model** 
- whos responsbily for what between the Cloud Service Provider (CSP) and the Customer

### Breakdown of components
1. Applications, Data, 
2. Runtime, Middleware, OS
3. Virtualization, Servers, Storage, Networking

### Cloud Models and Services
On Premises 
- Everything is yours. Responsbile for 1,2, and 3. 
IAAS 
- Virtual Machines. Youre responsble for 1, and 2.
PAAS 
- The underlying libraries and configuration of the VM is handled. Youre responsbile for 1.
SAAS 
- Everything is on Microsoft, you just use the software. Youre not responsble for any of the Tech.

*Benifits of Cloud Computing*
- cost-effective, global, secure, scalable, elastic, always-current
- low cap-ex

**Public Cloud Advantages**
- Scalable, agile, PAGY, no maintenance, low skills
**Private Cloud Advantages**
- legacy support, control, compliance
**Hybrid Cloud Advantages**
- flexibility

Synchronized Identity 

**scalability** - ability of system to handle growth of users or work
**elasticity** - grow and shrink based on app demand
**agility** - react quickly to changes in demand
**economies of scale** - lower cost per unit
**capital expenditure** - 
**operational expenditure** - 
**consumption based model** - 

**fault tolerance** - resistance to component level failure
**high availability** - resistance to service level failure
**disaster recovery** - ability to recover from event

## 2. Describe Core Azure Services

**Core architecture components**
- regions
- region pairs
    - 300 miles between them
    - chosen by microsoft
- availability zones
    - one or more datacenters
    - zore-redundant load balancer to survive zone failure
**Management Group**
- contain subscriptions
    - contains resource groups
- single top-level management group called the "root" management group
**Subscriptions** (Many in Management Group)
- unit of billing and scale
- multiple subscriptions are needed when 
    - subscription limits are reached
    - different payment methods
    - you need to isolate resources between departments
**Resource Groups** (1 to Subscription)
    - group related resources that share common resource lifecycle
    - **Resources** are entities managed by azure
    - boundary for setting access policies

### Compute

**Virtual Machines**
- compute-on-demand, no cap-ex
**Azure App Services**
- hosting web apps, rest-api, mobile back ends, secure with TLS cert
**Azure Container Instances (ACI)**
- Docker containers-on-demand managed, serverless environment
- solution for scenarios where they can run in isolated containers without orchestraction
**Azure Kubernetes Service (AKS)**
- hosted Kubernetes service where azure handles critical tasks like health monitoring
- same as above with orchestration using Kubernetes
- pay only for agent nodes
**Windows Virtual Desktop**
- desktop and app virtualization service in azure
- enables IT Pros and Mnaged Service Providers to create W10 virtual desktops in azure

### Network

**Virtual Networks** (VNET)
- logical representation of network in azure
- contains one or more subnets
- logical isolation
- dedicated network for resources
- sit-to-site vpn needed for hybrid cloud
- vnets cannot communicate by default only in subnets
**Private Link**
- private endpoint with specific IP
**VPN Gateway**
- core component of hybrid cloud
- encrypted and travels accross network
- encrypted traffic between on-premises and CNET
**Virtual Network Peering** (VNET Peering)
- connects VNETs
- transfer data between AD tenants
**Express Route**
- extends on-premises networks into azure over private connection with connectivity provider
- traffic does not traverse the internet
- faster than other options

### Storage

**Geo-redundant** - 3 data copies in 2 regions
**Read-Access GRS** - replicated data access in two zones
**Locally Redundant** - all replicas in one data center

**Storage Types**
- blob storage
    - unstructured data (images, files)
- file sthare
    - smb or nfs
- disk storage
    - virtual disks like vms
- table storage
    - structure, schema-less, NoSQL data, key-attribure store
    - cheap and fast and easy to manage
- Queue Storage
    - for storing lots of messages accessable from anywhere
    - authenticated with HTTP or HTTPS calls
**Storage tiers**
- hot, cool, and archive access tiers
- store blob objects in cost-effective manner
- lifecycle management policies to automate tiers

### Databases
**Cosmos DB**
- **important** ultra-low response latency
- can function as different types of DBs (mongo, sql, gremlin, cassandra, spark, etcd)
- fast global access and data conversion
- supports key-value, document object model and NoSql
**Microsoft SQL** (MS SQL)
- PaaS database engine, fully managed upgrading, patching, backups and monitoring
**PostgreSQL**
- managed PAAS service for PostGreSQL Community Edition
**MySql**
- managed PAAS service for MySQL Community Edition
**SQL Managed Instance**
- broadest compatibility SQL PaaS service
- migrate on-premises DB
#### Azure Marketplace
- lots of offered services
- simplified billing and single bill

## 3. Describe Core Solutions and Management Tools on Azure

**iothub**
-bidirectional communication between iot app and devices it manages
**iot central**
- simplifies the creation of iot solutions. reduces burden and cost. SAAS solution
**azure sphere**
- secure high leve application platform with built in security and communication on interente connected devices
- linux based, developed by microsoft to run on special Azure Sphere chip
- continous, renewable security
**Data Warehouse**
- data lake
    - big data analytics
    - AI
    - store organize and analyze diverse data from diverse sources
- synapse analytics
    - integrated analytics service 
    - accelerate time to insight accross data warehouse and big data systems
- HDInsight
    - cloud distribution of Hadoop
    - supports open source frameworks like hadoop, spark, hive, LLAP, Kafka, Storm, R, and more.
- Data Bricks Anaylitics Platform
    - developing data-intensive applications
    - 2 environments
        - SQL Analytics
        - Workspace
**Azure Machine Learning**
- cloud based environment to train, deploy, automate, manage and track ML Models
**Cognitive Services**
- cloud-based service with RestAPI to help build cognitive intelligence into your applications
- cognitive understanding categorized into five main pillars
    - vision, speach, language, decision, and search
**Bot Service**
- managed bot development service for building customer bots
**Serverless**
- Logic App
    - Schedule, Automate, Orchestrate tasks, Business processes and workflows
    - flow is built on top of logic apps
    - 300+ apps
- Functions
    - code-triggered by events
    - save money by only running when triggered
    - scalling built into platform
    - no spin up
    - less control over environment
- Event Grid
    - easily manage events across many different azure services and applications
    - pub/sub model
    - link app or service to react to event
    - push model
**DevOps**
- code deployment for CI/CD, KanBan, Agile
**Github**
- web-based git repository hosting service for source code management
**Github Actions**
- CI/CD for Github. build test, package, release, deploy code.
**Azure DevTest Labs**
- self-service sandbox environment
- quickly create dev/test environments
- minimize waste
- for saving money when running

### Azure Management Tools
**Portal**
- web based gui
**Cloud Shell**
- browser accessible powershell or bash shell for managing azure resources
**Powershell/CLI**
- set of cmlets for managing azure resources from Command Line
- windows, linux, mac, docker
**Azure Mobile App**
- browser app for managing, health, status and troubleshooting
**Advisor**
- scan config and recommends changes
- optimizes deployments
- increase security
- saves you money
- high availability
**Azure Resource Manager**
- JSON file to descibe deployment to Azure
- declarative syntax
- idempotent - deployable many times and get same resources
- infrastructure-as-code
**Azure Monitor**
- collects monitoring telementy from on-premises and azure sources
- management tools push log data to azure monitoy
- aggregates and stores telemetry in azure log analyics instance backend data store
**Azure Health Service**
- notifies you about azure service incidents and planned maintenance
- take action to mitigate downtime

## 4. Describe General Security and Network Security Features
### security features
**Security Center / Azure Defender**
- provides guidance on security
- can be set per resource
- free tier
    - continuous assesments of security and recomendations
    - azure secure score
- paid tier
    - just-in-time vm access
    - adaptive controlls
    - regulatory compliace
    - threat protection
**Sentinal**
- security information event management
- security orchestration automated response
**Keyvault**
- api keys, passwords, certificates, cryptographic keys
- accessable in many ways 
**Dedicated Host**
- dedicated phyical servers to host one or more VMs.
- not shared

### Network Security
**Defense in Depth**
- methodology for implementing security at multiple layers
**Network Security Group**
- rules that control allow/deny for users and ips and network adapters of NICs
**Firewall**
- high availability
- scalability
- firewall as a service
**Azure DDos**
- DDOS mitigation
- standard tier provides DDOS mitigation
- logging, alerting, telemetry not included in basic tier

## 5. Describe Identity Governance, Privacy, and Compliance Features
**Authentication AuthN**
- prove who you are
**Authorization AuthZ**
- permision to do something
**Azure AD**
- cloud-based 
- identity and access management service
- internal and external apps
- not necessary to link with on-premises
- apps must be registered
- RBAC supports authorization
**Single Sign on**
- user only logs in once and credentials are used in multiple apps
**MFA**
- two or more authentication methods: something you know, have or are
**Conditional Access**
- rules for giving access based on signals
    - signals are users, location, device, application, and real-time risk
**Role Based Access Control**
- access management based on roles
**Resource Locks**
- prevent users in org from accidentally deleting or modifying critical resources
- overrides any permisions the user migth have

**Cloud Governance**
- **policy** - enforces standards, sizes, names, regions for resources
- **intiatives** - collection of policies fto work toward specific goal
- **blueprint** - set of standards patterns and requirements for implementation of azure cloud
    - new environment
    - updating blueprint doesnt update assigned
    - unassigning blueprint removes resource lock but blueprint remains in place
    - deleting core blueprint, assigned blueprint remains
**Tags**
- organizing resources
- apply business policies, and tracking costs
- enforce tagging rules in policies

**bliling zone**
- biling based on data transfer

**Cloud Adoption Framework**
- guidance by microsoft on how to implement cloud

**Security, Privacy, and Complicance**
- tenants of seucrity privacy and complicance
- transparent about how and why data is used
- compliance - shows which standards azure is conpliant with
- template audit documents
- azure compliance documentations is searchable

**Microsoft Privacy STatement**
- how and why microsfot uses data

**Online Service Terms / Product Terms Site**
- contains terms and conditions for software use

**Data Protection Amendment/Addendum**

**Trust Center**
- 4 principles of trust: security privacy, compliance and transparency.

**azure sovereign regions**
- government, china, germany

## 6. Describe Azure Cost Management and Service Level Agreements

**cost impacts**
- factors that can affect resource costs
    - types, services, locations, ingress, egress traffic

**reducing costs**
- factors that can reduce costs
    - reserved instances, reserved capacity, hybrid use benifit, spot pricing

**reserved instances**
- reserve virtual machines in advance. VM specific
- 1 or 3 year options
**reserve capacity. **
- product specific discount on Databases and Analytics
- 1 or 3 year options
**hybrid use benifit**
- share on-premises software licences on azure
- include windows server, sql server, redhat and suse linux
**spot pricing**
- access unused azure compute capacity at deep discounts
- 90% percent discount
- VMs only
**Pricing Calculator**
- check pricing for region, instance, tiers before you deply
**Azure Cost Management**
- analyze, manage, and optimize costs of workloads
**Total Cost of Ownership**
- for calculate costs over long period of time


**Azure Service Licence Agreement**
- make sure to meet SLA requirements when deploying resources

**Private Preview**
- not for production. special resources for partners.

**Public Preview**
- not for production but public