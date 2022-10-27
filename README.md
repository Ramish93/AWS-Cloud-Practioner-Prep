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
  - if you change reagion, new resourses will be launched in new reagion, if reagion doesn't matter for a service like Route 53 it will say global at region selection menu.
- IAM user:

### using AWS Cli:

- You dont need to know how to config and use CLI to pass exam, but its a good skill

- to config CLI go to settings and credentials in console => access keys => create access and private keys. then follow the instructions in docs to install CLI.
- Root user keys should not be create use IAM user instead, its a security risk. but for one time use and deleting its fine.

## Compute services:

- The ones that are included in exam. this is kind of service that lets you leverage tha virtual machines like database,web server, or data calulations/statistics etc.

1. Amazon EC2 or elastic compute clode. (imp for exam)
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

- this is only for workloads that can start and stop without effecting what you are trying to do. but great savings.
- it really lets you leverage excess EC2 compute capacity that might exists in availibility zone.
- provides upto **90% discount** over on-demand pricing.
- there is a market price for instance type per availability zone.
- you request instance if you bid id higher AWS will launch your app.
- if spot price exceeds your instance is terminated. but you get 2min notification prior to termination.

5. **Dedicated Host instances.**

- gives you dedicated physical server in datacenter, most expencive option.
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
- deploying app with minimum knowledge of other services, like config servers, scaling groups, setting scaling rules, etc. you can rely on electric beanstalk to do for you
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
   - give you moneitoring and metrics on API calls.n so you can see usage and fix bugs if any.
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
   - there are 3 types of load balencers:
     1. application load balancers(ALB):
     2. NLB: Network load balancers
     3. Classic load balancers

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
       - it has two different storage classes associated with: frequent andinfrequent. it will move data between these classes.
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
3. Amazon EBS Elastic Blast Store:
4. EFS Amazon Elastic File System:
5. AWS snowball
6. Aws snowmobile.
