## Cloud Foundry Overview
- Do you understand Cloud Foundry concepts like spaces, organizations, routes, services, domains, users, quotas?

> **spaces** - every application and service is scoped to a space. Each org contains at least one space. A space provides users with access to a shared location for application development, deployment, and maintenance. Each space role applies only to a particular space.

> **organizations** - an org is a development account that an individual or multiple collaborators can own and use. All collaborators access an org with user accounts. Collaborators in an org share a resource quota plan, applications, services availability, and custom domains.

> **routes** - define how to get to an application
-- a unique route exists to each application in every space
-- domain can be mapped to multiple spaces
-- route can only be mapped to one space
-- same application can be deployed in multiple spaces
-- each must have a different, unique URL
-- development space route: http://myapp-test.cfapps.io
-- production space route: http://myapp.cfapps.io

> **services** - any type of add-on that can be provisioned along side your apps
-- database, messaging, mail, third-party SaaS provider
-- services are usually bound to 1 or more applications
-- connection info and credentials are put in an environment variable: `VCAP_SERVICES`

> **domains** - define routes to apps

> **users** - a user account represents an individual person within the context of a PCF application. A user can have different roles in different spaces within an org, governing what level and type of access they have within that space.

> **quotas** - restrict resources for orgs and spaces
-- total memory
-- total number of routes
-- max application instance size
-- total number of services

- How do you login to Cloud Foundry?
> `cf login [-a API_URL] [-u USERNAME]`

- How do you deploy an application? What are three activities involved?
> `cf push APP_NAME`
> 1. Upload
> 2. Stage
> 3. Start

- Can you remember the steps Cloud Foundry goes through when deploying applications? What components are involved?

- What is the difference between a public, private and hybrid cloud?

- What infrastructure does Cloud Foundry runs on?
  * AWS
  * VMware
  * Openstack
  * Azure 


- What is BOSH? Why is it useful?
> BOSH can provision and deploy software over hundreds of VMs. It also performs monitoring, failure recovery, and software updates with zero-to-minimal downtime.

- What is staging? What does it do?
> 1. Uploads application packages to staging droplet.
> 2. Applies Buildpack
> 3. Builds the application and make it ready to be run.

- Do you know the difference between restarting, restaging and redeploying and application? How does each of these affect the services, environment-variables available on an application?

> `restart` will simply stop your application and start it with the existing droplet.

> `restage` will stop your application, run the application bits through the staging process to create a new droplet, and then start the new droplet. It's a lot like `push` but without actually pushing new application bits.

> You typically restart when you need your applicaiton's environment refreshed and you typically restage when you need/want the buildpack to run without updating the application source.

- What is meant by ephemeral? What are the design implications for an application?
> ephemeral -> temporary
> virtual machines and containers are temporary
> immutable infrastructure - updates to systems and applications are not done in-place
> new, updated instances are created instead

- What are the 12 Factor Design patterns? Could you list each one from memory?

> 1. Processes
Execute the app as one or more stateless processes

> 2. Concurrency
Scale out via the process model

> 3. Disposability
Maximize robustness with fast startup and graceful shutdown

> 4. Logs 
Treat logs as event streams

> 5. Build, release, run
Strictly separate build and run stages

> 6. Processes
Execute the app as one or more stateless processes

> 7. Port binding
Export services via port binding

> 8. Concurrency
Scale out via the process model

> 9. Disposability
Maximize robustness with fast startup and graceful shutdown

> 10. Dev/prod parity
Keep development, staging, and production as similar as possible

> 11. Logs
Treat logs as event streams

> 12. Admin processes
Run admin/management tasks as one-off processes

- Why does Cloud Foundry rely on environment-variables?
> Environment variables are the means by which the Cloud Foundry runtime communicates with a deployed application about its environment.

- Can you manage environment-variables manually? If so how?
  > Yes, environment variables can be managed manually!
    * `cf set-env my-app my-variable_name my-variable_value`
    * `cf unset-env my-app my-variable_name my-variable_value`

- Can you name two predefined environment-variables available to any application?
  * `VCAP_APPLICATION`
  * `VCAP_SERVICES`
