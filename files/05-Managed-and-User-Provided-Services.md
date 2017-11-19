## Managed and User-Provided Services

- What is a service? Can you name some examples?
  > service is a resource reserved on demand 
  > examples: database on a shared or dedicated server, access to a SaaS application

- What is the "marketplace"? Does it show all services?
  > A marketplace is a listing of all service brokers and their corresponding catalogs which can be used by the apps deployed into cloud foundry by creating respective service instances.
  
  
  > All market place services can be seen using: `cf marketplace`
  
  
  > All services ( Managed & User-Provided) inside a particular space can be seen using: `cf services`

- What is the difference between a managed and user-provided service?
  >  Managed service is a service that is available in marketplace. User-provided service instances enable developers to use services that are not available in the marketplace with their applications running on Cloud Foundry.

- How would you create a managed service?
  > `cf create-service SERVICE PLAN SERVICE_INSTANCE`

- How would you use a managed service?
  > `cf bind-service APP_NAME SERVICE_INSTANCE [-c PARAMETERS_AS_JSON]`

- How would you create a user-provided service?
  > `cf cups SERVICE_INSTANCE [-p CREDENTIALS] [-l SYSLOG_DRAIN_URL] [-r ROUTE_SERVICE_URL]`

- How would you use a user-provided service?
  > `cf bind-service APP_NAME SERVICE_INSTANCE [-c PARAMETERS_AS_JSON]`

- What is `VCAPS_SERVICES`? Why is it important?
  > it is an environment variable containing connection details of bindable services that Cloud Foundry added after binding the services instance to the application.

- How do services interact with spaces?
  > Every application and service is scoped to a space. Use service keys when you want a set of credentials for use by clients other than the application in the same space. Not all services support service keys. Some services support credentials through application binding only.


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
