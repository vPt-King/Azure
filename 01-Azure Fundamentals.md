# Some common Cloud Services

## Compute
virtual machine computer run in cloud 

## Storage
Having virtual hard drive that can store file

## Networking
Virtual network being able to define internet connection or network isolations

## Database
Virtual database for storing data or database for general puporse web-application

# Type of cloud services
## SaaS Software as a service
A product that is run and managed by the service provider , don't need to worry about how the service is maintained, it just works and remain available.
Example: Salesforce, email, Office 365.

## PaaS Platform as a service
Focus on the deployment and management of your apps. Don't worry about provisioning , configuring or understanding the hardware OS
Example: Heroku , Google app engine

## IaaS Infrastructure as a Service
The basic building blocks for Cloud IT. Provides access to networking features, computers and data storage space. Don't worry about IT staff, data centers and hardware.

Example: Azure, AWS, OCI

# Cloud Deployment mode
## Public cloud
Everything built on the Cloud provider : Cloud native

## Private Cloud
Everything on the onpremise like Openstack

## Hybrid
Using both cloud and on premise

## Cross Cloud
Using multiple cloud providers aka multi-cloud, hybrid cloud

# High availablity
Running accross multiple Availability zones ensures that if 1 or 2 server down, the service remains available

Azure loadbalancer : allows to distribute traffic to multiple servers in one or datacenter, if 1 server or datacenter become unavailable , the load balancer will route the traffic to only available datacenter or server

# High Scalability
increasing capacity based on the demand of traffic, memory and computing power

```
- Vertical scaling : (Up) Upgrade to a bigger server
- Horizonal Scaling : (Out) More server
```

# High Elasticity
Your ability to automatically increase or decrease your capacity based on the current demand of traffic, memory and computing power
Using only with horizonal Scaling

Technology using:
`Azure VM scale sets : Automatically increase or decrease in response to demand or a defined schedule`

`SQL server strech Database: Dynamically stretch warm and cold transactional data from Microsoft SQL server 2016 to Micorsoft Azure`

# Fault Tolerance
Ensure that no single point of failure , prevent chance of failure

Some service: `Azure Traffic Manager` DNS-based traffic balancer to failover from a failing primary system to a standby sencondary system

# High Durability
Your ability to recover from a disaster and to prevent the loss of data. The solution that recover from a disaster is known as Disaster Recovery (DR)

# Business Continuity Plan (BCP)
A business continuity plan (BCP) is a document that outlines how a business will continue operating during an unplanned disruption in services

## Disaster Recovery options
We need to trade cost and time to recover
```
- backup and restore: backup data and restore it to new infrastructre
- Pilot light: Data is replicated to another region with the minimal services running
- Warm standby: Scale down copy of your infrastructure running ready to scale up
- Active/active: always ready
```

# Global infrastructure - Regions and Geographies

## Region
group of multiple datacenters : Azure has 58 regions available accross 140 countries

Paired region
```
Every region is paired with another region 300 miles away
=> Only one region is updated to ensure no outage
Some azure region rely on paired region for DR
```

Region type
```
Not all azure cloud services are available in every region
+ Recommended region: A region that provides the broadest range of service capabilities and is desgined to support availability zones
+ Alternate region : A region that extends Azure's footprint within a data residency boundary where a recommended region also exist. Not design to support AZs.

+ Special region: Region work with government
```


## Geography
Geography is discreet market of two of more regions
that preserves data residency and compliance boundaries

## Availability zones
Availability zones (AZ) is physical location made up one or more datacenter

A region will generally contain 3 datacenter

## Availability zone supported region
Not every region support Availability zones
These region as known as Alternate or Other
Recommended Regions support 3 AZ

# Fault and update domain
An availability zone in Region is combination of a fault domain and update domain
```
+ Fault domain : A logical grouping of hardware to avoid a single single point of failure within an AZ, group of virtual machines that share a common power source and network switch

+ Update domain : Azure may need to apply updates to the underlying hardware and software, update domains ensure your resources do not go offline

+ Availability set : a logical grouping that you can use in azure to ensure that the VMs you place in the Availability Set are different fault/update domains to avoid downtime
```

Each VM in an availability set is assigned a Fault domain and update domain