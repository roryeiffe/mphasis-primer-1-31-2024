## Azure
- Collection of Cloud Services offered by Microsoft
  - Hosting Apps
  - Hosting Databases, storage
  - In the same vein as AWS or GCP
- Real Life Example:
  - Host a PostgreSQL database on Azure's PostgreSQL service
  - Create a back-end application that interacts with that hosted database
  - Host that app on Azure's web app service
    - Can then access the back-end via a public endpoint

## Terms
- Cloud Computing - delivering services over the internet
  - servers, storage, database, networking, software, security
- Software as a Service (SaaS) - The application itself is managed/created by the cloud provider (AWS, Azure). The customer just controls who can access it
  - Examples: Microsoft Office, Google Docs, Salesforce
- Platform as a Service (PaaS) - operating system is determined by the cloud provider, we still have control over the application itself (sometimes shared)
  - ex: AWS RDS, Azure PostgreSQL
- Infrastructure as a Service (IaaS) - hosting infrastructures online where we don't have to worry about is physical level of setting things up but we have a lot of control over the operating system, choose the CPUs, etc., environment
  - Examples: AWS EC2, Azure Virtual Machine
- On-Premise - you manage everything yourself, buying hardware, setting up all security, data center
- ![Differences between SaaS, PaaS, IaaS](https://learn.microsoft.com/en-us/training/wwl-azure/describe-cloud-compute/media/shared-responsibility-b3829bfe.svg)

### Shared Responsibility Model
Outline the responsibilities delegated to either you the customer or the cloud provider (Azure in this case). 
- "Security Of the Cloud" - Azure's responsibility
  - The services themselves
  - Infrastructure
  - Physical Security
- "Security In the Cloud" - Our responsibility
  - Our data
  - Our Applications
- For the most part, Azure will offer certain options/settings to secure your apps/data. It is up to use to use these.

### Private vs Public vs Hybrid Cloud
- Private - dedicated to a single organization
- Public - many organizations can share the cloud for different purposes (Azure)
- Hybrid - using a private cloud for some needs/responsibilities and using public cloud for others

## Benefits of Cloud Computing
- A lot easier to spin up resources than having an on-premises infrastructure (managing everything)
  - Service Provider handle the hard parts that we also don't care about
- Cheaper than setting up everything yourself
  - Pay as you Go - pay for what you need, super cost-effective as opposed to setting up the entire infrastructure ourselves
  - Economies of Scale - the fact that so many people are using these services, the price goes down
- High Availability - services should be up and running for most of the time ( > 99%)
- Fault Tolerance - If something goes wrong, should continue running the services either way
  - Redundancy - having multiple instances of an app running (or at least ready to run) in different physical locations
    - So, if the power goes out, or some unforeseen event occurs, switch to the one that's working
- Scaling - scale up/out to meet demand or scale down/in during times of less traffic
  - Black Friday - spikes in activity
  - Summer Sales - spikes
  - Websites might not get as much traffic during the night - lulls in traffic
  - Good for keeping up with customer demand but also reducing unnecessary payments
### Horizontal Scaling
Refers to adding or removing instances of a server. Scaling out vs scaling in.

### Vertical Scaling
Refers to increasing or decreasing the power of a particular instance (CPU, RAM, storage size).

### Which is Better?
There are situations where one could be preferred over the other. Usually, it's easier and more scalable to do horizontal scaling.
- There's no limit to how much we can horizontally scale, we can keep adding units as opposed to building up our singular unit which does have a realistic "cap"
- Just adding more and more of the same type of unit, so a bit less involved
- With vertical scaling if you reach the limit, app could crash or slow down
  
### Azure Regions

## Resources
- [List of All Azure Resources](https://azure.microsoft.com/en-us/products#compute)
- [Azure Global Infrastructure](https://azure.microsoft.com/en-us/explore/global-infrastructure)


## Questions to Research
- Vertical Scaling - When we scale up, how do we avoid downtimes?

## Recordings
- [First Half](https://revature0-my.sharepoint.com/:v:/g/personal/rory_eiffe_revature_com/EbkZfa_CGO5Ii8AprazpCwQBdG-TSChaV7B06gDPJL7pBQ?referrer=Teams.TEAMS-ELECTRON&referrerScenario=MeetingChicletGetLink.view.view)
- [Second Half](https://revature0-my.sharepoint.com/:v:/g/personal/rory_eiffe_revature_com/EWiLcW5FnblIquW9glYpwWIB14v4aGJygO8tTHg_1lIVTA?referrer=Teams.TEAMS-ELECTRON&referrerScenario=MeetingChicletGetLink.view.view)