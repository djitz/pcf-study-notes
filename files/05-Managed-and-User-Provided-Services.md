## Managed and User-Provided Services

- What is a service? Can you name some examples?

- What is the "marketplace"? Does it show all services?

- What is the difference between a managed and user-provided service?

- How would you create a managed service?

- How would you use a managed service?

- How would you create a user-provided service?

- How would you use a user-provided service?

- What is `VCAPS_SERVICES`? Why is it important?

- How do services interact with spaces?


### pluralsight recap

- What is the difference between a managed service and a user-provided service instance?

> A managed service is advertised in the marketplace

> User provided service are provisioned outside of the platform

- Would it be advisable for a 12 factor app to store a configuration in a local file?

> No, because the application would have to be rebuild to change that configuration.

- Does a 12 factor app make a distinction between local and third party services?

> No, it doesn't. Both should provide location and credential information through the config, through the operating system environment variables

- After binding a service to an application, why is the application restarted, or restaged?

> So the application can have access to the new environment variables. The container is immutable, so once you bind a service to an application, we'll need to throw that one away by either restarting or restaging, or create a new one.

- Why could we restart versus restage?

> Restage rebuilt the application droplet.

- Whe does it need to be rebuilt?

> When there's new dependencies to pull in
