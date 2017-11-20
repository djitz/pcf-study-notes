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
  > `cf create-user-provided-service SERVICE-INSTANCE -r ROUTE-SERVICE-URL`
  
  > `cf bind-route-service [domain-name] [route-service-name] --hostname [target-hostname]`

- How does a route service work?
  > Binding a service instance to a route associates the `route_service_url` with the route in the Cloud Foundry router. All requests for the route are proxied to the URL specified by `route_service_url`
- How does a route service know where to send a request once it has performed its function?
  > With the Headers
    * X-CF-Forwarded-URL
    * X-CF-Proxy-Signature
    * X-CF-Proxy-Metadata
  > Used by the Router to validate the request and pass through to the application or reject it.
