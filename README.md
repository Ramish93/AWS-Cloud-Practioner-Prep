# AWS CLOUD practionar: ps

## Understanding cloud computing:

### Cloud computing models:

## IAAS:

infrastructure as a service. absolute control. They are servers in cloud. Similar to how we would set servers in our own datacenter. Can change OS, completely config them. However we have to do maintenance of them.

## PaaS:

platform as a service, this is in middle of them both. this means we are given a service thats configed. we just need to deploy our customization on to it. like wordpress host like wpengine you just drop code and they config wordpress and install the server for you.

## SAAS:

software as a service: email provider could be a SAAS service we are using them everyday. Don’t have to config them, it is a service provided as you need.

![clude computing models](./assets/s1.png?raw=true "clude computing models")

- **whats cloud computing: AWS says the on demand delivery of computer power, data storage, applications, and IT resourses through a cloud service via internet with **pay as-you-go pricing\*\*\*\*

### Cloud Deployment Models:

- Public Cloud: like deploying a solution onto a public cloude provider like AWS, Azure. this is very scalable. its completely virtual. availabel on demand. pay as you go.
- On-Premises:(on prem) like cloud, platform in a private datacenter. this is your own data center but you are using cloud services with your hardware you have direct control over infrastructure, this provides small services to small number of employees usually. vmware is company that deploy solution for you to have a private cloud.
- Hybrid: a cloud application connected to a private data center. used for cloud bursting eg. if bussiness out grows on premises cloud you can quickly shift and use public cloud for scalability. but its challenging because they are rarely a match.

## AWS global infrastructure:

- there are three.

1.  Aws Regions:

    - each reagion is located in **specific/multiple geographic location.** it could be centered around like singapore etc. each location has cluster of data centers that work together. AWS has 22 different regions. some public some not.

2.  avalability zones:

- these reagions operate with smaller units called **avalability zones .** they consist of one or more data centers. there are multiple availability zones included with each aws region. this means at minimum each aws reagion has two availability zones. and at minimum each availability zone has one data center. availability zones are located in the aws reagion. globally 69 availability zones have been launched. almost every service in AWS is connected to these availability zones or regions.
  in US there are 6 regions 4 public 2 govCloud for government. each region has 3,4 availability zones.

           > availibility means an app is fulfilling its intended bussiness purposes,
           apps with high availability are built where a single failure wont lessen
           applications ability to fully operation. which means for an app to be high avalibility
           we need to be deployed in multiple availibility zones within an AWS region.
           they are normally mission critical applications.

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

  there are 200 different locations that have edge locations. so this is most common part of infrastructure AWS has. it allows AWS to serve content from locations closest to users. so if we produce content in stockholm because of edge locations out content is able to serve in singapore if people view it there.

## Understanding Cloud Economics:

- two important terms are

  1. CapEx (capitalized expenditures) like when building a data center upfront investing cost of building, server equipment etc which is an asset for company. images illustrating usage of private data center with an app and 2nd to show if you need more capacity.
  2. OpEx is operating expediture. day to day expenditures after building data center, maintenance, connectivity and utilities.

     ![CapEx](./assets/CapEx.png?raw=true "CapEx")
     ![CapEx1](./assets/CapEx1.png?raw=true "CapEx1")
     ![finance expence](./assets/finance.png?raw=true "inance expence")

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
    for individual devs trying to run workload in aws.along with basic support you get bussiness hours support access to engineers. its limited to one contact per developer and reply is late.
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
- Aws profesional service: if you wanna work with AWS engineers.

# Understanding AWS core Services (2nd blog):

### Intracting with AWS Services:

1. AWS console:
   - to leverage browser to config aws.
     - it can interact with all 150+ AWS services. with mobile app aswell. just like i used making account, trusted advisor etc.
     - usage: testing new services or getting a hang of it.
2. AWS CLI:
   - CLI for administrating AWS resourses.
   - most of all tasks done with console can be done with cli, supports mac, windos and linux.
   - usage: for repeated task or automation. you can write custom scripts for these automations.
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
  - if you change region, new resourses will be launched in new region, if region doesn't matter for a service like Route 53 it will say global at region selection menu.
- IAM user:

### using AWS Cli:

- You dont need to know how to config and use CLI to pass exam, but its a good skill

- to config CLI go to settings and credentials in console => access keys => create access and private keys. then follow the instructions in docs to install CLI.
- Root user keys should not be create use IAM user instead, its a security risk. but for one time use and deleting its fine.

## Compute services:

- The ones that are included in exam. this is kind of service that lets you leverage tha virtual machines like database,web server, or data calulations/statistics etc.

1. Amazon EC2 or elastic compute cloud. (imp for exam)
   - is a web service that provides resizeable compute capacity in cloud, designed to make web-scale computing easier for devs.
   - sample usecase:
     - web app hosting, go in ec2 and make a server and put code there.
     - Batch processing: if your org produce millions of lines of slaes data, you can process it before you analize it.
     - web service endpoint. to be an api server, take web-services and launch them in cloud, let other apps access them.
     - Desktop in cloud: like launch a windows instance in cloud EC2 and access that with remote desktop.

- **Instance types:** Instances in AWS are basically virtual environments. These virtual environments are isolated from the underlying base OS. it defines processor, memory, and storage type that is avalable any servers that are launch with that instance type. so servers and more are connected to an instance type. you cant go to server and change instance types like need more memory in it or etc. so make good choices when creating instance type.
- instance types are across different catagories.

  - general purpose: for most of workload put in cloud.
  - compute, memory, storage optimized: they are three different catagories, eg. if we launch an inmemory DB we choose in-memory instance type.
  - accelerated computing: like for machine learning because you have GPU (graphic process unit) with it.
  - prices is based on instance type. more resources more price.
  - some instance type families have uniqure things with them, like GPU or specialized storage with them.
  - Instance type price , may change with regions or time. 4th has modern GPU with it and 5th has specialized storage hence the price.
    ![ EC2 price](./assets/EC2price.png?raw=true "EC2 price")

- Root device type:
- there are two different root devices in EC2.

  - Instance Store: storage thats physically attached to host that virtual server is running on for a short amount of time meaning if you shut down your instance store server data will be lost.

  - Elastic Block Store (EBS): prisistent storage that exists seperately from host that v.server is running on, if you shut down data won't be lost. most of you work in done on EBS unless a specific reason.

- Amazon Machine Images (AMI):
- its a template for ec2 service that includes configs, operating systems, data that would go on that specific instance. there are many AMIs that you can leverage.
- they can be shared across accounts, so if you org has specific version of ubuntu linux that you want to modify in certain way for security reasons, and you wanna attach one storage to it these are example of configs you can make.
- you can create you custom AMIs, there is AWS market-place for available AMIs too.

### EC2 purchase Type:

1. On demand
   - default instanct if you launch without choosing. its on demand model, so pay as you go.
2. Reserved instances:
   - Provides discount over on-demand method model if you commit to specific period of time 1 or 3 years.
   - Provides capacity reservation for instance type that you specify so it will stay with you in time that you specify.
   - Reserved instance types:
     1. standered: highest discount, works for steady workloads. so if want bigger instance you are locked in for 1 or 3 year and you cant change.
     2. Convertable reserved instances: allows us to convert attributes equal value to what we already have.
     3. scheduled instances: If you have predictable but not-steady workload you can use this. like during weekend you have more traffic so you can use this.
     - here is a cost model for standered Reserved instances
       ![ EC2 SRIcost](./assets/SRIcost.png?raw=true "EC2 SRIcost")
3. **Saving plan**

- similar to reserved instances but it supports compute with EC2, fargate, and lambda.
- unlike reserved instances it does not reserve capacity but there is a way to do it.
- 72% saving on it.
- comes in 1 or 3 year terms.

4. **Spot instances.**

- this is only for workloads that can start and stop without effecting your bussiness or application. but great savings.
- it really lets you leverage excess EC2 compute capacity that might exists in availibility zone.
- provides upto **90% discount** over on-demand pricing.
- there is a market price for instance type per availability zone.
- you request instance if you bid id higher AWS will launch your app.
- if spot price exceeds your instance is terminated. but you get 2min notification prior to termination.

5. **Dedicated Host instances.**

- gives you dedicated physical server in datacenter, most expensive option.
- if you have a per-server licencing model. and you want to abile by terms of licence.
- also some compliance require a dedicated host. so in that case too use this.
  ![EC2 buy Options](./assets/EC2buyOptions.png?raw=true "EC2 buy Options")
  ![EC2 buy Options](./assets/EC2buyOptions1.png?raw=true "EC2 buy Options")
- here is an example of prices for Reserved Instances. as you can see the saving in it.
  ![EC2 spotPrice ](./assets/spotPrice.png?raw=true "EC2 spot Price")

- here is an example of prices for Spot Instances.
  ![EC2 RI price](./assets/EC2RIprice.png?raw=true "EC2 RI price")

- watched how EC2 instance is created and launched.
- ### AWS Elastic beanstalk is created and launched.
  - it automates the process of deploying and scaling the workloads on EC2.(PaaS)
  - its more like platform as a service
  - Unlike EC2 where you can do anything you need if you deploy a server. here you have to work with a specific set of technologies.
  - it leverage existing AWS services. only pay for the other services.
  - its kinda a new category because those services are only helping to connect or deploy the elastic Beanstalk.

#### - why use elastic beanstalk?

- it has monitoring using other small services but it pull monitoring info in.
- deployment: when you have big apps, there are multiple servers and figure out how to loadbalance them, so it is handled by elastic Beanstalk.
- it handles scaling. we can also config it.
- EC2 customization: it allows you to add customization to servers where your app is running.

- **Use cases for elastic Beanstalk**
- deploying app with minimum knowledge of other services, like config servers, scaling groups, setting scaling rules, etc. you can rely on elastic beanstalk to do for you
- reduce overall maintenance.
- few customize the environments. other hand if you really like to be precise in tech or versions then EC2 is ideal.

#### AWS Lambda:

- you can run code without provisioning or managing servers. only pay for compute time you use. you run your code for virtually any type of application or backend service with 0 administration.
- on high level it does that but you have to allocate memory for it. from 128 to 3k gb.
- integrate with AWS services easily, enables event driven workflows,

- Advanteges of Lambda:
  - reduced maintenance requirments and cost.
  - enables fault tolerance without building it in. no single point of failure plus multiple availability zones.
  - scale based on demand,
  - pricing on usage.

### Network and content delivery services:

<!-- // do this module again -->

1.  Amazon route 53
    - its a DNS. Domain name service
    - its leverages AWS edge location service.
    - its Global service not regional.
    - highly available.
    - Enables global resource routing. so you can send people to specific servers based on their geo-location.

- whats DNS:
  - its basically internet phone book. this translates www.google.com to a numaric ip that computer can communicate with.
  <!-- - it translates the domain names into numaric IP address, to specific address that are needed for identifying the computer service and device that are serving the content. -->

2. Amazon VPC vertual private cloud(imp for exam)

   - a logically isolated section of AWS cloud where you can launch say, EC2 or anyother virtual network and its your portion of cloud.
   - in VPC you support ipv4 and 1pv6.
     - you can config ip address, subnet, route tables, network gateways.
     - supports both private and public subnets. so if you want areas of cloud like a webserver of your VPC not acessable to internet or you dont want . you can do both.
     - Enables connection to your data center.
     - can connect to other Vpcs.
     - Private connection to many AWS services. it means if you dont want sensitive information info to go through inter net you can move it in VPC.

3. AWS direct connect
   - allows to establish a dedicated network connection easily from datacenter to your AWS app. the app wont be on internet.
4. Amazon API Gateway:
   - fully managed API management service. meaning you can create APIs so other apps can call them and you can make those available. you can distribute those through cloud front.
   - it directly integrates with other AWS services.
   - give you monitoring and metrics on API calls, So you can see usage and fix bugs if any.
   - can integrate this in VPC or on-premise app.
5. Amazon CloudFront:
   - it leverage edge locations. **its a gloabal CDN.** which means there are servers around the world where you can send your content to, so that users get that content from servers closer to them.
   - supports static and dynamic content.
   - utilizes AWS Edge Location.
   - it includes security features:
     - AWS shield for DDos: destributed denial of service attack.
     - AWS WAF: web application firewall.
6. Elastic Load Balancing
   - Elasticity is defined as ability of infrastructure supporting an app to grow and contract based on usage.
   - distributes traffic across multiple targets based on eg. which server is busier. come default with EC2 ECS and Lambda.
   - there are 3 types of load balancers:
     1. application load balancers(ALB):
     2. NLB: Network load balancers
     3. Classic load balancers
   - The ALB operates on layer 7, which means the ALB inspects the details of every incoming HTTP request. In contrast, the NLB works on layer 4. All the NLB cares about is forwarding the incoming TCP or UDP connection to a target. The NLB does not inspect an incoming HTTP request, for example

- Scaling on Amazon EC2:

  1. Vertical scaling: or scale up. meaning scale up you instance to larger instance type with more resources. we can do it if we see that users are seeing late response on one server etc. but in this case we have to **shut server down** and move it to bigger instance type.
  2. Horizontal scaling: or scale out. add additional instances to handle demand of app. its leverage elastic load balancing.

- AWS Global Accelerator:

  - its a networking service that sends your users traffic through amazon web services global network improving your internet user performance by upto 60%.
  - it uses IP's and also edge locations and cloud front but its using it from IP resolution instead of DNS.
  - once user request reaches to edge locations instead of routing it through internet it uses AWS network. it can also route request to many AWS resources. like
    1. NLB network load balancer.
    2. ALB: Application Load balencer.
    3. EC2 instances.
    4. Elastic IP address.
  - Performance improvements.

    1. distance btween user request and initial endpoint is going to decrease because of edge location.
    2. Traffic is optimized by using AWS network instead of public internet. it reduces latency and jitter.
    3. Superior fault tolerance.

  - Use Cases of AWS Accelerator:
    1. if you are using non-http protocol. like UDP, VOIP like maybe UDP in gaming context VOIP if you are doing internet telephony,
    2. if you require Static IP not DNS resolution then you need global accelerator.
    3. if you need instant filover with highest level of high availability and best fault tolerance.

## File Storage and Data Transfer services:

1. Amazon S3:
   <!-- important for exams -->
   - one of the core services. one of the first. let you store files in large amount in buckets, buckets are unit of storage in S3.
   - you create bucket and it will have some settings and any file that goes in it will have those settings-
   - gives storage classes for different use cases.
   - store data across multiple availability zones.
   - you can send urls for stored files to anyone with permission.
   - offers configurable rules for data life cycle.
   - can serve as a static web host.
   * **S3 Non-archivable storage classes:**
     - S3 standered: its by default, its for frequently accessed data.
     - **S3 intelligent-tiering.** its only way to move your data to correct storage classes based on usage,
       - automatically moves files to different storage classes based on access.
       - it has two different storage classes associated with: frequent and infrequent. it will move data between these classes.
       - same performance as standered S3 but will be cost effective.
     - S3 standered-IA (infrequent accessed): get lower cost if data is not frequently accessed.
     - S3 one zone-IA : for not frequently accessed data but its also in just one availability zone. less cost than others.
   - S3 lifecycle policies:
     - object in buckets can transition and expire based on your config.
     - transition can enable objects to move to another storage class based on time or delete aswell.
     - you can move objects based on usage thats only for intelligent tiering, here its based on time.
     - you can config to delete certain versions of files, like old ones after a configurable period of time
   - S3 Transfer Acceleration: it enables you to upload files faster because of edge locations as part of amazon cloud front.
2. Amazon S3 Glacier:

   - its designed to archive data with S3 as a separate storage class. eg. your org has data that you wont access regularly but you need to store it for long time. this is usecase for s3 glacier.
   - it offers configurable retrival times. you pay more/ less for quick or slow retirival.
   - you can use lifecycle of s3 to transition data here.
   - you can upload data here with AWS console but to retrieve you have to use programming.
   - it has two classes:
     1. S3 glacier:
     2. S3 glacier deep archive
        ![S3 glacier price](./assets/S3glacier.png?raw=true "S3 glacier price")

3. Amazon EBS Elastic Blast Store:
   - it is bassically presistent block storage for Amazon EC2.
   - its block storage designed to connect single EC2 instance that can scale to support petabytes of data and multiple volume types based on need.
     - data is durable.
     - allows users to take snapshots of data. like if you want to have data in backup aswell.
     - make sure to config encryption.
     - it provides multiple volums
       1. general purpose SSD
          - its a cost effective type designed for general workloads.
       2. provisionaed IOPS SSD
          - its a high performance volume. for intence usecase.
       3. Cold HDD
          - less frequently accessed workloads.
       4. Througput optimized Hard disk drives
          - its for if we have frequently accessed data.
4. EFS Amazon Elastic File System:

   - EBS is an option to attach storage to EC2 instance but EFS is anthoer approach.
   - Unlike EBS this can be attached to multiple instances at same time.
   - its a fully managed NFS (Network File System is a distributed file system protocol that lets users access files over a network similar to the way they access local storage) file system. designed specificly for linux workload.
   - like EBS it supports petabytes of data.
   - saves data across multiple AZ.
   - two different storage classes:
     1. standered
     2. infrequent access.
   - provides configurable lifecycle rules so you can transition between two options.
   - **for windows user FSx**:
     - fully managed native windows filesystem.
     - it gives windows features like
       1. SMB support
       2. Active Directory integrate
       3. Windows NTFS
     - uses SSD drive for low latency.

5. AWS snowball
   - how to transfer large amount of data two AWS without public internet?
   - its a data migration service. usually petabytes of data physically. meaning you get a physical device from AWS to connect to your network and upload.
6. Aws snowmobile.
   - if you want physically migrate exabytes of data. it will be like a shiping container size device.

- comparison of these 2:
  ![S3 snow ball and mobile](./assets/snowballMobil.png?raw=true "S3 snow ball and mobile")

## Database and related services:

![Database and related services](./assets/DBAS.png?raw=true "SDatabase and related services")

1. Amazon RDS relational Database service:

   - takes platform as a service approach.
   - fully managed service. handles provisioning and, patching, backup and recovery of your database for you which consume quiet some time.
   - supports deployment across multiple AZ.
   - support read replicas for some platforms. you can scale out (horizontal scaling) your database for apps that are using this database.
   - launches into a VPC.
   - two volume types

     1. general purpose SSD
     2. Provisioned IOPS SSD.

   - platform that it supports:
     1. MySQL
     2. postgresSQL
     3. MariaDB
     4. Oracle
     5. SQL
     6. Amazon Aurora
        > it was created as an option for RDS, it is MySQL and postgres compatible relational database. its simple and cost efficient.

2. Amazon Aurora
3. Amazon DynamoDB:

   - software as a service option.
   - its fully managed **NoSql** database.
   - you dont manage the database layer. you just use it.
   - provides both key value pairs, and documented database.
   - extremely low latency.
   - it can scale automatically based on usage or you can scale manually with configurations.
   - DAX dynamo Accelerator. which gives you in memory chache for faster speed.
   - can support 10 trillion reqs per day and 20million requests per second.
   - Use Cases:
     1. Scaling a DB is very challenging and unpredictable. so it scales automatically.
     2. serverless archetecture. its a match.
     3. where low latency is key, it has quick response time.

4. Amazon RedShift:
   - born in a cloud scalable data warehouse service. data anylitics, machine learning etc are good usecase for it.
   - petabytes of data-warehousing supported.
   - leverages high performance disks and columnar storage.
   - ability to fully endcrypt content of warehouse.
   - it gives a level of isolation in your VPC.
   - **redshift spectrum:**
     - an subset of Redshit, it gives you ability to query exabytes of data using amazon S3.
5. Amazon Elasticache
   - fully managed in-memory data store.
   - it has two different engines supported. Memchached and Redis which is very popular.
   - low latency
   - enable scaling and replicas to meet application requirements.
   - handles common use cases
     1. database layer caching, meaning a layer of caching between database and app.
     2. session storage.
6. AWS Database Migration Service/ DMS
   - if you have private database and you want to integrate it into RDS?
   - supports one time and continuous migration.
   - out of the box supports many databases.
   - you only pay for compute you used for migration-

## App integration services:

1. Amazon SNS:

- Simple Notification Service.
- fully managed pub/sub messaging service,
- can create decoupled applications.
- organized according to topics. pub/sub published and subscribed.
- integration to multiple AWS services.
- apart from you some parts of you app able to talk to each other it gives end user notifications. you can send aSMS, email or push to mobile app. so certain parts of app can listen to some topics and other can listen to others.
- SNS archetecture:
  - ![SNSarchetecture](./assets/SNSarchetecture.png?raw=true "SDatabase and related services")
- SNS messgaes or emails are not permanent. if you dont subscribed to a topic you may never know info about it

2. Amazon SQS
   - fully managed message query service.
   - allow you to build decoupled apps.
   - enables to build fault tolerant apps. meaning if something happens with analytics service when we send our user data to it. the info wont be lost it will still be in queue. and when that app is up and running we can get info from queue.
   - you can put 256kb in a message.
   - allows messages to be stored for 14 days.
   - two types of queues are supported with SQS.
     1. standered queue. it can't guarantee the order of items you pull off of queue.
     2. FIFO first in first out queue. processes messages in order.
3. AWS Step functions:
   - serverless workflow management service.
   - it enables oschestration of workflow through fully managed service.
   - can support complex workflows including error handling.
   - charged per state along with other services that you use.
   - workflows are defined using Amazon states language.
   - out of box work with other amazon services. like compute services, lambda, database services, SQS and SNS, data processing services and machine learning services.

## Management and governance services:

- this is the ecosystem of management services provided by Amazon once you launch resourses to cloud.

1. AWS CloudTrail:
   - with cloudtrail you can log, continuous monitor and retain activity from actions across aws infrastructure. it works with console, SDK and CLI.
   - it includes this in a S3 bucket.
   - logs event in reagions they occer.
   - best practice, it should be enabled on all aws accounts
   - it maybe a requirement to track account info.
   - use cases:
     - if its a requirement to track and log.
     - forensic analysis, like if you had a breach and you wanna see what actions were performed to stop it and soo on.
     - operational analysis, like what caused a crash, it will be in logs,
     - troubleshooting
2. AWS CloudFormation:
   - if you have specific need for an app like 2 S3 bucket, 4 instance of EC2 etc. and you do it manually in console, maybe you make a mistake, cloudformation solves it.
   - no addional charge.
   - it uses templates in two formats, YAML JSON.
   - this is infrastructure as code.
   - manage dependencies, if one resouse must launch before other it will manage that.
   - it detects if someone changes configs of infrastructure and tells you.
3. AWS Config
   - continuously evaluate/records your infrastructure like your configs again best practice rules they can be AWS's or you can make your own, if your infrastructure doesnt meet standerds it will give you insight how to meet them.
   - provides configurations history for infrastructure
   - if your getting payment information PCI-DSS are rules you must follow, it comes along with config here.
4. AWS System manager:
   - provides unified user interface so you view operational data from multiple AWS services, also can automate operational tasks. like common maintenance actions like update EC2 instances across 20 servers that you have or less. you would write it once and all servers will update.
   - secure way to access server using just AWS credentials.
   - secure way to save environment variables, like multiple apps use same key, password you can just save it here.
5. AWS Control tower:
   - in AWS organization you can make multiple accounts with same security, logging, make consolidated billing and best practices for that are under control tower.
   - it centralizes users across all aws accounts.
   - can make new AWS accounts based on template.
   - it has guadrails which is if you want any service to never turn off you config it here.
   - it has a decent dashboard for UI.
6. Amazon cloud watch:
   - provides metrics, logs, alarams for your infrastructure.
   - collects logs, metrics like number of users in a load balancer, eventsfrom most AWS services.
   - enables alarams based on metrics. like you can set alaram to see things are working as expected.
   - provides visualization capabilities for matrics. charts etc and you can make custom dashboards.
   -

- AWS opsworks:
  - its a configurations management service.
  - provides best for both chef and puppet
  - configs are going to be code and they will deploy on same server, chef and puppet will manage that for you
  - works hybrid, you can work with it on cloud and in own datacenter.
  - its make of 3 subservices:
    1. AWS opsworks Chef Automate: configurations management your app that utilizes chefs automate.
    2. AWS opsworks for puppet enterprise: configurations management your app that utilizes puppets automate.
    3. AWS opsworks stacks: it allows you to manage your app in layers and you can manage them with chef recepies .

# Inroduction to Security and Architecture on AWS:(3rd blog)

1. Acceptable use policy: like accept agreement when you sign up.

- it stop you to send unsolicited mass emails. spam emails.
- hosting or distribution of harmful content. virus or malware
- penetration testing: you can do that now, it lets you run test to see security risks in you app. they give a list of services for it.
- least privilege access: give new user least permisions to complete their task. dont use root account, make a IAM(identity and access managemanet) account for daily use.
- security and compliance is shared responsibility of AWS and customer.
  1. AWS is responsible for Security of Cloud, customer is responsible for security in the cloud.
     ![shared Responsibility](./assets/sharedResponsibility.png?raw=true "sharedResponsibility")

2. AWS well-architected framework:

   - over time AWS has created best practices here at AWS well-architechted framework.
   - there are 5 pillers
     1. operational excellence: let us know we're running and monitoring system and bussiness value.
     2. Security: procecting data while deploying and throughout lifecycle of it.
     3. reliability: systems are up and running.
     4. performance efficiency: using resources efficiently.
     5. Cost optimization: minimal cost for desired value
   - you should go to AWS well-architechted docs to follow best practices as you build your first app in AWS.

3. high-availability and fault tolerance:

   1. fault tolerance:
      - being able to support faliure of components within an architechture.
      - like SQS if some components are down. we can still get data from que.
   2. High availability:
      - keeping solution running despite issues that may occure.

   - how to build solution based on these practices.
     ![solutions Architech map](./assets/solutionsArchitech.png?raw=true "solutions Architech map")

4. Compliance Standards:
   - PCI-DSS: if you wanna directly handle credit cards data those companies would like you to meet this standered.
   - HIPAA: compliance standards for healthcare data in terms of privecy. so least privilege.
   - SOC 1, SOC 2, SOC 3: technical compliance standards, related to oporational processing of you data centers.
   - FedRAMP: compliance standards for government data handling
   - ISO 27018: personally identifiable information.
     services that allow you to adhere and navigate to these compliance standards:
     1. AWS Config: provides conformance packs for standards.
     2. AWS artifact: provides self-service access to reports.
     3. AWS guadDuty: provides intelligent threat decection. over-view and notify scenarios that could lead you to be out of compliance.

## AWS Identities and user management:

1. IAM: Identity and Access Management

   - if you want give access to your employees to AWS console, you want them to be able to spin up a EC2 server but nothing else this is where you'll create their user and configure what they are able to do.
   - its free. manages authentication and authentication
   - uses Identity Federation: allows us to use external identity providers like google accounts, facebook etc. to to handle authentication portion of IAM. like if you have 2k employees and you wanna create config for them.

   - IAM identity types:

     1. user: single individual to access AWS resources like making account for an employee and config it.
     2. group: allows you to manage permissions for a group. you assign permissions to group and then add new users in it.
     3. role: user or service assume permissions for a task. like an EC2 server accessing the s3 bucket. this is what roles are here for to give access to our services to talk with other services on AWS in a secure way.

   - Policies in IAM:

     1. its a json document that defines permissions for IAM identity.
     2. difines what services identity can access and what action can be taken by that identity on that service. like using s3 bucket allowed deleting now allowed.
     3. policies can be custom managed or by AWS.

     - here is what a custom policy look like
       ![custom policies](./assets/custompolicies.png?raw=true "custom policies")

   - IAM best practices:
     1. multi-factor authentication:
        extra layer of security.
     2. least privilege access

- Amazon Cognito:
  - a managed service that enables you to hande handle authentication and authorization for custom web and mobile applications.
  - its like IAM but for custom applications.
  - has UI components for IOS android etc.
  - security capabilities, to control access.
  - enables you controlled access to AWS resources.
  - can work with social and enterprise identity providers. like google, amazon, facebook.

## Data Architect in AWS:

1. on permise data integration services, **Aws storage gateway:**

   - this is a hybrid cloud storage service. so merging together your datacenter and AWS.
   - integrates cloud storage into your local network by deploying a VM or specific hardware appliance running gateway software onto your network.
   - integrats with S3 and EBS.
   - supports 3 types of gateway:
     1. tape gateway:
        > like old days where data used to be on tapes, it gives same experience. but with virtual tapes.
     2. volume gateway
        > provides cloud based iSCSI volume to local applications and its stored on cloud.
     3. file gateway
        > enables you to store file in amazon s3 while keeping some files for cache and low latency
   - AWS dataSync: its to show how you set you integration of data from your datacenter to AWS.
     - it works by deploying VM on your network.
     - integrates with S3, EFS, FSx.
     - great speed trasfer due to custom protocole AWS has developed.
     - charged per GB of data transfered between your datacenter and AWS.

2. Data processing:

   - **AWS Glue:** this is a managed extract, tansform and load ETL serveice.
   - so first you extract data from your datacenter, then transform it eg. change format of phone number or other thing. load meaning putting in new location
   - intergrates well with Amazon RDS, DynamoDB, Redshift and s3.
   - serverless model of execution. so you dont need to spin up servers. etc. just use service.

   - **Amazon EMR elastic map reduce:**
   - big-data cloud processing service using popular tools
   - operates in cluster environment without configurations.
   - frameworks it supports:
     - apache spark, apache hive, apache Hbase, apache Flink, apachehudi, Pesto
   - you can use these tools without spending massive time on configurations.

   - **AWS data pipeline:**
   - also a managed ETL service.
   - data workflow orchestration service across aws services
   - supperts S3, dynamoDb, Redshift, EMR, RDS.
   - can integrate your on-premise datastore within your pipeline.

## Analizing Data:

1. Amazon Athena: lets you query data stored in S3.
   - its a fully managed serverless service. dont have to configure any infrastructure just leverage the service.
   - being able to query large-scale data within S3.
   - write query just using standered SQL.
   - charged basied on data you scanned during query.
2. Amazon Quicksight: fully interlligent business intelligence service enabling dynamic data dashboards that you stored in AWS Redshift and others.
   - many use models: one is per-user and per-session pricing model. so there are different versions with different capabilities and cost.
3. Amazon CloudSearch: fully managed search service for custom applications.
   - if you wannt make application for custom search like alot of pdf documents etc. and show data to users it can scale large data.
   - charged per-hour and instance type search infrastructure.

## Integrating AI and Machine Learning:

- now that you have alot of data and you've processed and analyzed it. they can analyze large amout of data.

1. **Amazon Rekognition:** its computer vision service powered by Machine Learning. meaning we can get insights on images stored on platform.

   - fully managed image and video recognition deep learning service. it can identity object and actions in images/videos.
   - can detect specific prople using facial analysis.
   - if you had a clothing store and you would like to detect when people are wearing your products or checking then out in a website you can see that, its called custom label for bussiness objects

2. **Amazon Translate**: translate text powered by Machine Learning.

   - supports 54+ languages,
   - has laguage identification.
   - can translate text and you speak and it translates imidiately.

3. **Amazon Transcribe:** speach to text solution.
   - can translate audio or you speak and it translates imidiately.
   - can intigrate into your custom app.
   - supports 31 languages globally.

# Disaster Recovery/DR on AWS:

- how we prepair from it. hard/soft ware failure, water damage, human error etc.
- if you are leveraging AWS,
  ![DR scnerios](./assets/DRscnerios.png?raw=true "DR scnerios")

1. Backup and restore:

   - taking all production data and back it up to amazon S3, in archive or standered storage class.
   - EBS data can be stored as snapshots in amazon S3.
   - in a DR event, a process is started to launch new environment. new servers and DB instances etc.
   - it has longest recovery time. and least cost.

2. Pilot light:

   - you keep only key infrastructure running in the cloud. it does incure cost. and for infrastructure that you want ready but not running you can prepair AMIs so they can start new servers at moments notice.
   - its designed to reduce recovery time over backup and restore approach. it has to be maintained with time because it is running.

3. Warm Standby:

   - this is a scale down version if full environment running in cloud. it runs everything but not at full scale. it has more cost than above.
   - critical systems can be running on small instances types and scale up on DR event.

4. Multi site:
   - full environment is running in cloud at all times. meaning our datacenter is and could running at same time.
   - Near seamless recovery process.
   - most cost.

## Selecting a Disaster Recovery Architecture:

1. RTO Recovery Time Objective:
   - the time it takes to get your systems up and running after DR event.
   - if you have an objective that we should be up and runnin in 8 hours after DR then your RTO is 8hours.
   - multi site has least RTO but high cost and backup and store has highest RTO but least cost.
2. Recovery Point Objective:
   - the amout of data lost in terms of time during DR event.
   - meaning if you have online store and Disaster happens for 1 hour so in that time you will loose data that people sent, so RPO is 1 hour.
   - it is all about data not time.
   - multi site has least RPO but high cost and backup and store has highest RPO but least cost.

# Archetecting application on amazon EC2:

- Scaling EC2 infrastructure: vertical scaling, horizontal scaling:

  - Auto Scaling Group

    - set of EC2 instances with rules for scaling and management,
    - there is a launch template defines the instace config for the group. if you know you want Windows server with specific configs you can define all that in this template.
    - you can define min, max and desired number of instances.
    - performs health checks on each instance.
    - Exists within 1 or more AZ in single reagion. usually multiple AZ for fault tolerance.
    - works with on demand and spot instances.
    - if one server (C4) stops running the application load balancer will tell auto scaling and it will spin a new instance, mean time the traffic is routed to other AZ server.
      ![EC2 horizontal scaling](./assets/EC2horizontal.png?raw=true "EC2 horizontal scaling")

- AWS Secret Manager:

  - when scaling out to multiple servers to securely integrate things like credentials, API Keys, Passwords like if we have RDS we would need secure way to get those credentials.
  - Secrets Manager integrate natively with RDS, DocumentDB and redshift.
  - so you dont want keep same password for RDS for 3 years, for security, you can config it to keep rotating.

  - Elastic Load Balancing:
    - allows us to distribute traffic across multiple targets

## Controling access to EC2 instances:

1. EC2 Security groups.

   - enables firewall-like control for EC2 instances.
   - control inbound outbound traffic but at instance level, and they can belong to multiple
     security groups and all servers in that group will have
     same security config
   - VPC has default security group, and all our bound traffic
     is allowed meaning your server can send any info
     out to internet

2. Network ACL's: access control list.

   - control inbound outbound traffic for subnets within the VPC.
   - every server with subnet will adopt ACL for that subnet.
   - and this allows you to allow and deny traffic but default ACL
     allows inbound outbound traffic but a custom ACL by default denys all traffic.

3. AWS VPN:
   - secure access to entire VPC using a encrypted tunnel.
     so your VPC will not be available to anyone.
   - VPC can be connected to a single machine.
   - supports two services:
     1. site-to-site VPN: in aws direct connect you have direct connection to
        infrastructure that doesnt need public internet. but here you have a site-to-site VPN in middle and you config the connection.
        and it travels over internet. and its encrypted.
     2. Clinet VPN: WS Client VPN is a fully-managed remote access VPN solution used by your remote workforce to securely access resources within both AWS and your on-premises network. Fully elastic, it automatically scales up, or down, based on demand.

## Security services:

1. AWS Shield:

   - Managed Distributed denial of service DDoS, DDoS is a type of attach
     by flooding server or servers with more traffic than they can handle to bring them down.
   - its ongoing threat detection and mitigation. you keep it running.
   - two service levels for it:
     1. standered :
     2. advanced:

2. Amazon Macie:

   - Data stored in S3 protection service powered by machine learning.
   - with specifing it can detect personal information and intellectual property in S3.
   - it watch and catagories data to make sure data breach doesn't happen.
   - provides a level of dashboard to show how data is stored
   - enables alerts for unusual activity and we can't do this type of detection if we do it manually.

3. Amazon inspector:

   - automated security assesment service for EC2 instances.
   - if we wanna see vulnerabilities, standered practices meet etc we can use this.
   - charged per instance per assessment run.
   - two types of rules packages:

     1. network reachability assessment: to see what is available to internet from our servers
     2. host assessment: to see what EC2 instance are patched for vulnerabilities.

## deploying pre-defined solutions.

1. AWS service Catalog:

   - if you are an organization and want to use services on AWS.
   - if you make a robust service that meets all best practises org and industry you can let other use it.
   - supports a lifecycle for services released in catalog. eg. if you update verion of your service
     everybody using it will be notified.

2. AWS marketplaces:
   - catalog software to run on AWS but from third party providers.
   - many similarities in this and AWS service catalog.
   - enables different pricing models to overcome licencing in cloud.
   - charges appear on your AWS bill.

## Developer Tools:

- a suite of services to make developemet process as easy
  as it can be. and easy to follow best practices.

1. AWS Code commit: managed source code repository using Git.

   - uses IAM policies.

2. AWS Code Build: its a fully managed build service. continuos integration service.

   - dont have to worry about maintaining infrastructure.
   - charged per minute of compute resources you utilize.

3. AWS CodeDeploy: take care of deployment out to many AWS services. fully managed.

   - can deploy to EC2, fargate, lambda and your on-premise servers
   - provides dashboard so, easy to navigate.

4. AWS Code pipeline: it create a pipeline for all above
   services and integrates with them well, so we can make them and see the process.

   - fully managed continuous delivery service.
   - integrate with github

5. AWS CodeStar: a way to bootstrap this entire process for out custom applications.
   - workflow tool to automate the use of above developer services.
   - can create complete continuous delivery toolchain with few clicks.
   - dashboard, and configs in console.
   - you are only charged for other services you leverage. its free.
