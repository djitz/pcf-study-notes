## Cloud Foundry Architecture

- Can you name the main components running inside Cloud Foundry? Do you know what each of them does?
![CF Architecture Diagram](https://github.com/djitz/pcf-study-notes/raw/master/images/cf_architecture_block.png)


- What does Diego refer to?
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
