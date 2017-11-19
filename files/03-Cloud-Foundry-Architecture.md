## Cloud Foundry Architecture

- Can you name the main components running inside Cloud Foundry? Do you know what each of them does?
![CF Architecture Diagram](https://github.com/djitz/pcf-study-notes/raw/master/images/cf_architecture_block.png)
![Diego Diagram](https://github.com/djitz/pcf-study-notes/blob/master/images/diego-overview.png)

#### Elastic Runtime Subsystems 
- Diego 
- Loggregator 
- Cloud Controller API 
- Routing 
 
#### Key Sequence Flows through the ER 
 
#### Diego 
- Schedules tasks and Long-Running Processes (LRPs) 

##### Task 
- Is guaranteed to run at most once  
  - E.g. stage an application 

##### LRP 
- Typically represented as a web app. LRPs can have multiple instances 

##### Container 
- An application instance is run within an immutable container 

##### Cell 
- Containers are run within a cell 

##### Garden 
- Containers are managed by Garden 
- Garden is an interface 
- Garden-Linux is a backend implementation 

##### Rep 
- Represents the Cell in the BBS/Auctions 

##### Auction 
- An auction is held to bid on executing a task or an LRP 

##### Executor 
- Manages container allocations on the cell 
- Subprocess of a Rep 
- Steams stdout and stderr to metron 

##### Metron 
- Forwards logs to the Loggregator subsystem 

##### BBS 
- Bulletin board system 
- API to access the Diego database for tasks and LRPs 
- Data is persisted to etcd 

##### Brain 
- Composed of two components 
   - Auctioneer 
       - Hold auctions for tasks and LRPs 
   - Converger 
       - Reconciles desired LRPs vs Actual LRPs through auctions 
 
#### Loggregator 

##### Doppler 
- Gathers logs from Metron 
- Create app syslog drains 
Splunk 
Papertrail 

##### Traffic Controller 
- Handles client requests for logs 
- Exposes a web socket endpoint called the firehose 

##### Firehose 
- A websocket endpoint that exposes app logs, container metrics and ER component metrics 

##### Nozzles 
- Consume the firehouse output 
    - E.g. Datadog Nozzle 
 
 
#### Cloud Controller API 
##### Cloud Controller 
- Exposes an API for using and  managing the Elastic Runtime 
#### Cloud Controller Database (CC_DB)
- The Cloud Controller persists Org/Space/App data in the Cloud Controller Database 
##### Blob Store 
- The Cloud Controller persists app packages and droplets to the Blob Store 
##### CC-Bridge 
- CC-Bridge translates app specific messages into the generic language of task and LRPs 
 
 
#### Routing 
##### Router 
- Routes traffic to appropriate component 
 


What does Diego refer to?
> PCF container management system

- What is Garden?
> it's a component that CF uses to create and manage isolated environments called containers.

- What components run in a Diego Cell?
> - Rep
> - Executor
> - Garden
> - Metron Agent
> - Route-emitter

- What is the System domain? And the application domain?
  * The system domain is the domain used for things like the API, Apps Manager and other system provided services.
  * The apps domain is the default domain that will be setup for developers to use when pushing applications to the environment.
  
- What is Cloud Foundry's API endpoint for?
> - it provides access to the system
> - for managing spaces and orgs

- What is a container? What is it used for?
> An application instance is run within an immutable container

- What is a droplet? How is it created? Where is it stored?
> - Droplets is a staged apps packaged with everything needed to run in a container.
> - It is created during application staging process by Diego cell
> - It is stored in Blobstore

- What are the purposes of the two data stores used by the Cloud Controller?
> - Blobstore
>    - Store app packages, buildpacks, droplets
> - Database (CC_DB)
>    - The Cloud Controller persists Org/Space/App data in the Cloud Controller Database
