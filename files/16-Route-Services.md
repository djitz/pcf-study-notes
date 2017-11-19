## Route Services

- What is a route service?
  > Route Services are a kind of Marketplace Service that developers can use to apply various transformations to application requests by binding an application’s route to a service instance.
  
- Why might you create a route service? Can you think of some examples?

  > Provide transformation or processing to requests before/after they reach an application

  > Examples:
  - Authentication
  - Rate limiting
  - Logging 
  - Caching
  - Transformation 


- How would you create a route service?

  > `cf bind-route-service [domain-name] [route-service-name] --hostname [target-hostname]`

- How does a route service work?
- How does a route service know where to send a request once it has performed its function?

> Headers 

> - X-CF-Proxy-Signature
- X-CF-Proxy-Metadata
Used by the Router to validate the request and pass through to the application
