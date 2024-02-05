## Azure Kubernetes Service (AKS)
Azure's solution/service for handling Kubernetes. We can deploy Kubernetes clusters with Azure handling the management/scaling/operational overhead.

### Kubernetes 
An open-source platform used for automating deployment, scaling, and operating of containers. Kubernetes groups the containers into logical units for easy management. Good for running production workloads because in a production environment, traffic can fluctuate thus scaling is an essential feature in our infrastructure.

### Containers
Package software and environment details in a format that can run anywhere. Containers are lightweight and they contain everything needed to run the software including code, runtime, system tools and libraries, and settings. More lightweight than a virtual machine because they are able to leverage the host's operating system. 


## Azure Images
To create a VM from "scratch" on Azure, we had to select an OS, performance requirements, storage. There might be situations in the real world where we want to create VMs based on a pre-built set of configurations. Azure Images are the solution for these, they let us create VMS based on whatever conditions/configurations we set. 

Two approaches to creating Images:
1. First, create a VM with the settings you want and then capture it and save it to an image. All VMs created with this image would be pretty similar to the original VM in terms of things like OS, memory, etc.

2. The other option is using Azure VM Image Builder.


## Azure Load Balancer
For apps that require scaling and multiple instances of services to be up and running, the question becomes: when we get a request to our app, which instance is it going to go? 

As requests come on, the load balancer will delegate these requests to the healthy (up and running) instances of our service. It's highly available and scalable so it's important for production environments that are utilizing multiple instances of VMs, containers, etc.

### Network Load Balancer
The general term for what Azure Load Balancer achieves. Operates at the Network Layer (refer to OSI model). Distributes incoming traffic to healthy instances . 

## VPN (Virtual Private Network) GateWay
Azure VPN Gateway lets us send encrypted traffic between Azure Virtual Networks and on-premises locations over the public internet. Because the connection is secure, can use this to transfer data between private and public cloud.

On Azure Portal, can look into Application Gateway

### VPN Gateway
A VPN Gateway is a type of virtual network gateway that is comprised of 2 or more VMs that are deployed to a specific subnet, which is called the gateway subnet. This subnet is a part of the virtual network that contains the resources connect to. 

## Storage Services
Azure offers many different storage solutions, each for specific scenarios. Azure storage services are, in general, designed to be highly available, scalable, and durable. 

### Azure Disk Storage
Provides block storage for VMs and apps. Think of a disk drive on your computer and remember that VMs are kind of like a virtual computer that we can use. 

### Azure Blob Storage
A storage solution that lets us store a lot of different types of data, unstructured data such as text files and binary data. A use case that we will explore is storing an HTML file and then deploying it to a static website. 
- Can store
  - text
  - binary data
  - videos
  - files
  - source code

This is different from a SQL service in that the data is very unstructured. 

### Azure Data Lake Storage
A storage solution that provides scalable and secure data lake for big data analytics.

### Azure Files
Provides file storage for applications and VMs. 

### Azure NetApp Files
A storage solution for big enterprises, characterized by extreme performance. 

### Azure File Sync
Solution for synchronizing on-premises data for caching. 

### Azure Stack Edge
Hardware-as-a-service that extends Azure services to your physical location (referred to as the edge). Sort of like a mini-data center that you keep on-premises. It reduces latency because the processing is happening there. Good for remote locations like factories, oil rigs, farms, etc.

### Azure Data Box
Pick from physical components to transfer large amounts of data to Azure especially when networks are slow and/or there's a lot of data. The process is secure and the devices are wiped afterwards.

## Azure Cache for Redis
Thinking about caching, where we hold on to certain data for quicker retrieval later on. Azure Cache for Redis is a caching solution that allows for improved latency for apps that need to access data frequently. 

## Azure Backup
Azure's service that lets you back-up data including:
- On-premises data
- Azure VMs
- Azure File Shares
- SQL Server
- SAP HANA (High-performance ANalytic Appliance)
- Azure Blobs
- Azure Kubernetes

## Resources
- [AKS Overview](https://learn.microsoft.com/en-us/azure/aks/intro-kubernetes)
- [Kubernetes Overview](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/)
- [Create an image of a VM](https://learn.microsoft.com/en-us/azure/virtual-machines/capture-image-portal)
- [Azure VM Image Builder](https://learn.microsoft.com/en-us/azure/virtual-machines/image-builder-overview?tabs=azure-powershell)
- [Azure Load Balancer](https://learn.microsoft.com/en-us/azure/load-balancer/load-balancer-overview)
- [VPN Gateways](https://learn.microsoft.com/en-us/azure/vpn-gateway/vpn-gateway-about-vpngateways)
- [Azure Storage Solutions](https://azure.microsoft.com/en-us/products/category/storage)
- [Block vs File Storage](https://aws.amazon.com/compare/the-difference-between-block-file-object-storage/)
- [Azure Data Box](https://azure.microsoft.com/en-us/products/databox)
- [Azure Cache Tutorial](https://learn.microsoft.com/en-us/azure/azure-cache-for-redis/cache-java-get-started)
- [Azure Backup](https://learn.microsoft.com/en-us/azure/backup/backup-overview)