## Logging, Scaling, and High Availability

- How do you access application logs?

- What are the components of the Loggregator system?

> 1. Metron - Forward logs to the Loggregator subsytem
2. Doppler - gather logs from Metron
3. Traffic Controller - handles client requests for logs
4. Firehose - a websocket endpoint that exposes app logs, container metrics and ER component metrics
5. Nozzles - consume the firehose output

- How do you scale an application manually?

- What are the four levels of high-availability provided by PCF?

> 1. BOSH detects and recreates failed VMs
2. BOSH also detects and restarts failed processes
3. Application instances are automatically spread
-- Across different Cells
-- Across Cells in different Availability Zones
4. CF Converger detects if an application instance has failed and restarts it

- What is the difference between scaling up and scaling out?

