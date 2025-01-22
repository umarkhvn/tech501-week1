# DevOps Day 2


- [DevOps Day 2](#devops-day-2)
  - [Intro to Agile](#intro-to-agile)
    - [What is the Agile Methodology?](#what-is-the-agile-methodology)
    - [Why is it relevant for DevOps Engineers?](#why-is-it-relevant-for-devops-engineers)
    - [Agile Manifesto](#agile-manifesto)
  - [The Cloud](#the-cloud)
    - [What is The Cloud?](#what-is-the-cloud)
    - [Differences between On-Premise and The Cloud](#differences-between-on-premise-and-the-cloud)
    - [Main Cloud Providers](#main-cloud-providers)
    - [Cloud Deployment Models](#cloud-deployment-models)
    - [Types of Cloud Services](#types-of-cloud-services)
    - [Costs in the Cloud](#costs-in-the-cloud)
    - [4 Pillars of DevOps](#4-pillars-of-devops)
    - [Why is the VNet Important?](#why-is-the-vnet-important)
- [SSH Code Along](#ssh-code-along)


## Intro to Agile

### What is the Agile Methodology?

* A philosophy, a way of thinking
* Delivering immediate value rather than conforming to deadlines
* Incrementally respond to changes often, rather than a big overhaul every now and then
* Categorised by daily stand-ups, regular sprint planning, and retrospectives
* Not all organizations are actually Agile even if they claim to be
  * Cargo Culture

### Why is it relevant for DevOps Engineers?

* Helps to promote a culture of learning and improvement by incrementally improving a product by using core practices like daily-stand ups, sprints, and retrospectives.
* Emphasises the concept of continuous integration and releasing code frequently.
* Always having a minimum viable product to which you can build open.
*  Seamless collab between different teams.
*  Able to remain flexible.

### Agile Manifesto

* ***Individuals and interactions*** over processes and tools
* ***Working software*** over comprehensive documentation
* ***Customer collaboration*** over contract negotiation 
* ***Responding to change*** over following a plan

## The Cloud

### What is The Cloud?

* The Cloud is essentially a non-physical server where resources are allocated
* It is a service available over the internet
* Centrally managed. Allows us to have remote access to our resources
* Key indicators of a service in the cloud are:
  * No physical servers or on-site infrastructure
  * Scalability and flexibility in resource provision
  * Use of web interfaces, APIs, or cloud consoles to manage resources
* Resources can include:
  * Virtual Machines | VN (Compute)
  * Virtual Networks | VNet (Network)
  * Databases
  * Storage (AWS S3, Azure Blob)

### Differences between On-Premise and The Cloud

On-Premise
* Owned and managed by the organization
* High initial cost and ongoing maintanence
* Limited by physical infrastructure
* Full control over hardware and software
* Requires internal teams for maintanence and upkeep

Cloud
* Owned and managed by a Cloud Provider
* Pay as you go pricing model
* Highly scalable
* Shared responsibility model. Not in full control
* Cloud provider handles most maintanence 

### Main Cloud Providers

* Azure
  * Strong hybrid capabilities, integration with Microsoft ecosystem
* AWS
  * Comprehensive offerings, early market entry, global reach
* GCP
  * Known for AI/ML and data analytics

On Azure... 

* Only make what you are authorised to make 
Tag everything with the key Owner and value (your first name) 
* Any .pem file must go in your .ssh folder (a private key when generated yourself doesn't have any extension) 
.ssh folder must NEVER be part of any Git repo. Why? 
* Use UK South region only 
* Working hours for Azure: 9:00 to 17:00. If you need to use after this time, ask your trainer well ahead of time. 
* Switch off (“Stop”) VMs when you are not using them or by the end of working hours. 
* Your responsibility: Remove anything you know you don’t need anymore. 

<br>

On AWS... 

* Similar rules apply except... 
* You don't need to tag everything you make 
* Use the Ireland region only 

<br>

DO NOT EVER EXPOSE YOUR CREDENTIALS ON ANY PLATFORM. This includes: 

* GitHub 
* AWS/Azure 
* While screensharing on Teams 
* Uploading content to teams 
* If you are ever asked to make a video 

### Cloud Deployment Models

* Private Cloud
  * Dedicated to a singe organization for greater control and security
  * Higher costs associated
* Public Cloud
  * Owned and managed by cloud providers. 
  * Cost efficient but less control
  * Shared Infrastructure
* Hybrid Cloud
  * Combines private and public clouds. Balances flexibility and control
* Multi Cloud
  * Use of multiple cloud services from different providers to avoid vendor lock-in

### Types of Cloud Services

* IaaS (Infrastructure as a Service): Virtual servers, storage, and networking (e.g., AWS EC2, Google Compute Engine).
* PaaS (Platform as a Service): Managed platforms for developers to build applications (e.g., AWS Elastic Beanstalk, Azure App Services).
* SaaS (Software as a Service): Ready-to-use applications (e.g., Microsoft 365, Google Workspace)

### Costs in the Cloud

* Compute (VMs, containers).
* Storage (block, file, or object storage).
* Networking (data transfer, load balancing).
* Additional services (AI/ML, databases).

Is migrating to the cloud always cheaper?
* Pros: Reduced upfront costs, scalability, maintenance handled by providers.
* Cons: Long-term costs may be higher, particularly if not optimised for usage.

OpEx vs CapEx

* OpEx (Operational Expenditure): 
  * Pay-as-you-go expenses. Cloud falls into this category as it involves ongoing payments.
* CapEx (Capital Expenditure): 
  * Large upfront investments, typically seen with on-premises infrastructure.
* Cloud services shift costs from CapEx to OpEx, improving cash flow but potentially increasing total lifetime cost.

### 4 Pillars of DevOps

* Culture: Collaboration across teams.
* Automation: CI/CD pipelines.
* Measurement: Monitoring performance.
* Sharing: Knowledge sharing.

### Why is the VNet Important?

* Our resources live in the VNet
  * Think of the VNet as a house, and our resources the furniture inside
  * We have limited space in our house to allocate the furniture
* 2 Subnets in the VNet
  * Public Subnet
    * To communicate with IP addresses externally
    * Public IP addresses are optional
  * Private Subnet
    * To communicate with IP addresses internally
* VM's live inside our Subnets
  

# SSH Code Along

1) Go into root ~ /c/Users/ukhan/
2) Make a directory for SSH keygen: mkdir .ssh
3) Navigate into directory: cd .ssh
4) Generate a key with the following command: ssh-keygen -t rsa -b 4096 -C "['your personal email' without the square brackets]"
5) Create a file name for the key. As we use Azure, the key should reference this. The name in this instance is: tech501-umar-az-key
6) Enter passphrase: optional
7) A public and private key should have been generated, assigned with a randomart image.
8) Use the ls command to confirm both keys are generated. One should be exactly the file name. The other should be the same with a .pub extension, indicating this is the public key.