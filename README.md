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

## Support your AWS infrastructure:

- AWS support is the service allows you to file support requests to aws resourses. it allows you to get support for aws resourses running in cloud. its in different tiers based on your scope.. it sudevides into two services.
  - AWS personal Health dashboard:
    - provides alerts and remediations guidence with aws is experience an event that may effect you. like a power shortage or cyber attack. this is where you'll know about it.
  - Aws trusted advisor:
    - automated tool to check aws usage against best practice. so always impliment solutions as trusted advisor provides. different checks are provided according to the support tier plan. but all customers get access to 7 core support checks with advisor. the checks are divided into 5 parts.
      Cost optimizations, Performance, Security, Fault tolerance, Service limits.

* AWS support plan tiers:
  the differenses in tiers basically falls into 4 catagories, cost, communication Method, Response time, Type of guidence.
  - AWS Basic support (no cost):
    its for all customers, you have 7 core check with trusted advisor. 24x7 customers service, docs, white papers etc. however you dont get access to engineers for technical-implimentation.
  - AWS developer support(29$ per month but tied to usage):
    for individual devs tring to run workload in aws.along with basic support you get bussiness hours support access to engineers. its limited to one contact per developer and reply is late.
  - AWS bussiness support(100$ permonth but tied to usage):
    along with developer support, full set of trusted advisor checks. 24x7 access to phone, email and chat access to engineers. it lets all of your people to have access and file support request not just root user. you are also allowed to deploy third party software in aws with support.
  - AWS enterprise support(15k permonth plus usage):
    all bussiness plus TAM a technical account manager just for you, and a concierge support team.

- Now for support response time, look at this image.
  ![support response time](./assets/AWSsuportRes.png?raw=true "support response time")

## Assistance for Cloud Workload:

these services are for organizations who wanna move to cloud.

- aws quick start: docs for step by step implimenting any common tech platform into aws. good for orgs who just wanna know if they are deploying in a good manner.
- Aws partner network consulting partner: thye dont work for aws but work for a company that is approved from aws, orgs can hire them to imliment a solution.
- Aws profesional service: if you wanna work with AWS people.

# Understanding AWS core Services (2nd blog):

### Intracting with AWS Services:

1. AWS console:
   - to leverage browser to config aws.
     - it can interact with all 150+ AWS services. with mobile app aswell. just like i used making account, trusted advisor etc.
     - usage: testing new services or getting a hang of it.
2. AWS CLI:
   - CLI for administrating AWS resourses.
   - most of all tasks done with console can be done with cli, supports mac, windos and linux.
   - usage: for repeated task or automation.
   - here is command to get users from CLI:
     ![cli getusers](./assets/cligetusers.png?raw=true "cli getusers")
3. AWS SDK:
   - programming access to manage AWS resources.
     - this is where we use a language to script the process how we intract with Aws.
     - usage: for repeated task or automation + if you have an custom app adk would be great choice to let that app intract with AWS services.
     - languages support:
       ![ sdk languages](./assets/sdklanguages.png?raw=true " sdk languages")

### using AWS console:

- Root User: is special kind of user, its the user that first created account on AWS when you started using AWS. it has permissions like support tier and deleting the account.
  - root user can auth two factor login, they can see billing and organization in dashboard, and region change,
  - if you change reagion, new resourses will be launched in new reagion, if reagion doesn't matter for a service like Route 53 it will say global at region selection menu.
- IAM user:

### using AWS Cli:

- You dont need to know how to config and use CLI to pass exam, but its a good skill

- to config CLI go to settings and credentials in console => access keys => create access and private keys. then follow the instructions in docs to install CLI.
- Root user keys should not be create use IAM user instead, its a security risk. but for one time use and deleting its fine.
