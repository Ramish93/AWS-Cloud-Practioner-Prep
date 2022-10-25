# AWS CLOUD practionar: ps

## Understanding cloud computing:

### Cloud computing models:

## IAAS:

infrastructure as a service. absolute control. They are servers in cloud. Similar to how we would set servers in our own datacenter. Can change OS, completely config them. However we have to do maintenance of them.

## SAAS:

software as a service: email provider could be a SAAS service we are using them everyday. Don’t have to config them, it is a service provided as you need.

## PaaS:

platform as a service, this is in middle of them both. this means we are given a service thats configed. we just need to deploy our customization on to it. like wordpress host like wpengine you just dropm code and they config wordpress and install the server for you.

![clude computing models](./assets/s1.png?raw=true "clude computing models")

- whats cloud computing: AWS says the on demand delivery of computer power, data storage, applications, and IT resourses through a cloud service via internet with **pay as-you-go pricing**

### Cloud Deployment Models:

- Public Cloud: like deploying a solution onto a public cloude provider like AWS, Azure. this is very scalable. its completely virtual. availabel on demand. pay as you go.
- On-Premises:(on prem) like cloud like platform in a private datacenter. this is your own data center but you are using cloud services with your hardware you have direct control over infrastructure, this provides small services to small number of employees usually. vmware is company that deploy solution for you to have a private cloud.
- Hybrid: a cloud application connectied to a private data center. used for cloud bursting eg. if bussiness out grows on premises cloud you can quickly shift and use public cloud for scalability. but its challenging because they are rarely a match.

## AWS global infrastructure:

- there are three.

1.  Aws Regions:

    - each reagion is located in **specific/multiple geographic location.** it could be centered around like singapore etc. each location has cluster of data centers that work together. AWS has 22 different regions. some public some not.

2.  avalability zones:

- these reagions operate with smaller units called **avalability zones .** they consist of one or more data centers. there are multiple availability zones included with each aws region. this means at minimum each aws reagion has two availability zones. and at minimum each availability zone has one data center. availability zones are located in the aws reagion. globally 69 availability zones have been launched. almost every service in AWS is connected to these availability zones or regions.
  in US there are 6 regions 4 public 2 govCloud for government. each region has 3,4 availability zones.

           > availibility means an app is fulfilling its intended bussiness purposes, apps with high availability are built where a single failure wont lessen applications ability to fully operation. which means for an app to be high avalibility we need to be deployed in multiple availibility zones within an AWS region. they are normally mission critical applications.

           1. naming convention of availibility zones is as follows: eg name is us-east-2a

           - us is area
           - east is sub area - 2 a number because there could be multiple regions within that area.
           - then alpha bet to show the availability zone.
             the region name would be us-east-2 but a is avalability zone.

- here are some AWS regions (without avalability zones):
  ![aws Regions](./assets/awsRegions.png?raw=true "awsRegions")

3. Edge Locations:

- Edge Locations are primarily used for caching of the data to provide better user experience with low latency, where as availibility zones are used for hosting servers, websites, applications, softwares, Big Data processing, analytics and a wide variety of use cases. Edge location are used as a part of global CDN (content delivery network). there are 2 different services that leverage these edge locations.

  1. Amazon cloud front: its AWS global CDN.a web service that speeds up distribution of your static and dynamic web content, such as . html, . css, . js, and image files, to your users.
  2. Amazon Route 53: Amazons DNS service.a highly available and scalable Domain Name System (DNS)

  there are 200 different locaitons that have edge locations. so this is most common part of infrastructure AWS has. it allows AWS to serve content from locations closest to users. so if we produce content in stockholm because of edge locations out content is able to have a server in singapore if people view it there.

## Understanding Cloud Economics:

- two important terms are
  1. CapEx (capitalized expenditures) like when building a data center upfront investing cost of building, server equipment etc which is an asset for company. images illustrating usage of private data center with an app and 2nd to show if you need more capacity.
     ![CapEx](./assets/CapEx.png?raw=true "CapEx")
     ![CapEx1](./assets/CapEx1.png?raw=true "CapEx1")
     ![finance expence](./assets/finance.png?raw=true "inance expence")
  2. OpEx operating expediture. day to day expenditures after building data center, maintenance, connectivity and utilities.

## organizations and optimizations of AWS cost:

- AWS cost explorer: a tool in AWS with UI.
  - it provides breakdown via
    1. by Service
    2. cost Resource tags
    - there are predefined reports make you can download with your data.
    - it also tries to predic cost for upcoming 3 months.
    - gives recommendations for cost optimizations by UI or by API.
- AWS Budgets:
  - utilizes data from cost explorer and track all AWS services, track cost per service, service usage, reserved instance utilization, coverage and saving plans.
- Cost planing tools:

  - AWS TCO (total cost of ownership) calculator. for organizations considering from their own data center to cloud. help make a case to transition to cloud. Based on a lot of customer feedback, the AWS TCO Calculator has been replaced by the AWS Pricing Calculator.
  - AWS simple Monthly Calculator **now deprecated and called AWS pricing calculator:** calculate specific workload in cloud. like your datacenter use 5 servers you can add them here and it will tell monthly cost.

- How to organize use of aws:

  - Resources Tags: just matadata that we attach to our AWS resourses. they include a name and optional value, like in your datacenter allocating 5 servers to social webapp and naming them social app as tag name or dev and production servers etc.

    - You can make an allocation report in aws and it will include the cost by active tags.

  - AWS Organizations: multiple accounts under single master account. like different departments (dev, production) or different applications can run on seperate accounts under same master account.
    - Consolidated billing: this will give bill of each account under organization in detail.
    - you can also standerdize logging or security etc across all accounts within organization.
