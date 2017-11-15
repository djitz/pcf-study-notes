## Metrics

- What is "PCF Metrics"? What information does it provide?

> PCF built-in metrics information
> - Container metrics: CPU, memory, disk %
> - HTTP metrics: requests per second, HTTP errors per second, request latency
> - App events: create, update, start, stop, and crash

- Do you understand how to use the metrics to spot a badly performing application? For example: CPU or memory usage?
> 1. Set up a custom chart to monitor the application performance (or)
> 2. Highlight the CPU Utilization spike keyword in the logs and debug the application to resolve what is causing the spike.

### pluralsight recap

- What might a spike in memory indicaate when using PCF metrics?

> It might mean a resource leak in the code


### documentation

http://docs.pivotal.io/pcf-metrics/1-3/using.html
