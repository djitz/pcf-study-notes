## Log Drains

- What is a log drain?

- How do you create one?

- Why would you use it?

- What is "Syslog"?

> de facto standard for logging on Unix/Linux

---
### pluralsight recap

Is cf restart or restage required for log draining to start working? Why or why not?

> It's not required, because from application perspective it's just writing to standard out or standard error. Doppler is a component of the Loggregator system that's responsible for forwarding those logs to third party log management services like Paper Trail or Splunk.

How does this approach differ from how you get your logs today?

What kind of alerts or visualizations could you create from your log data?

> Identify top five exceptions that were happening in an application

> Being able to understand what the utilization is of the applications
