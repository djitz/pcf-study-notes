## Logging, Scaling, and High Availability

- How do you access application logs?
> cf logs APP_NAME

- What are the components of the Loggregator system?

> 1. Metron - Forward logs to the Loggregator subsytem
> 2. Doppler - gather logs from Metron
> 3. Traffic Controller - handles client requests for logs
> 4. Firehose - a websocket endpoint that exposes app logs, container metrics and ER component metrics
> 5. Nozzles - consume the firehose output

- How do you scale an application manually?
> cf scale <APP_NAME> -m <Size> -i <Instance_COUNT>


- What are the four levels of high-availability provided by PCF?

> 1. BOSH detects and recreates failed VMs
> 2. BOSH also detects and restarts failed processes
> 3. Application instances are automatically spread
-- Across different Cells
-- Across Cells in different Availability Zones
> 4. CF Converger detects if an application instance has failed and restarts it

- What is the difference between scaling up and scaling out?
> - scale up (vertically) increases the disk space limit or memory limit of all instances of an application. It requires downtime as the container is recreated.
> - scale out (horizontally) increases the number of instances of an application by creating or destroying them. It requires no downtime.

### pluralsight recap



- What are some fundamental changes impacting application design and delivery?

>  - Distributed computing
>  - Ephemeral infrastructure
>  - Immutable infrastructure

- What is a modern methodology for delivering cloud based applications?

> Twelve-factor app

- How are logs handled in a Twelve-factor app?

> As event streams

- True or false, Garden is an interface with many implementations.

> True, there's Linux and Windows and more on the way

- Which component of the Elastic runtime exposes an API for users to manage applications?

> Cloud controller

- What are the four levels of high availability that keep your applications running?

>  - Availability zones
>  - BOSH managed processes
>  - Failed VMs - any VM that BOSH deploys will be recreated if you enable resurrector
>  - Self healing application instances handled by the brain within Diego

- Where should you write your application logs?

>  - To Standard Out and Standard Error

- What are some of the different origin codes that were seen in the log?

>  - cf logs
>  - API for cloud controller
>  - stage for stating 
>  - cell for running applications

- What did you think about accessing the logs? How is that different from what you do today?

- What is the difference between scaling out versus scaling up?

> Scaling up requires down time to recreate the container
> Scaling horizontally requires no downtime

- How do you recover failed application instances today? What happens if the underlying platform fails? How do you recover from that?

- How could you tell if your application has been crashing?

> Look at the logs, but probably the best place to go is cf events
