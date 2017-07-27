## Service Brokers

- What is a service broker?

> a component of the service which implements the service broker API. This component advertise a catalog of service offerings and service plans, as well as interpreting calls for provision (create), bind, unbind, and deprovision (delete).

- Why do we need service brokers?

- How do a service broker and the Cloud Controller intercooperate?

- What is the purpose of each broker endpoint?

- In general terms, how would you write your own service broker? How would you test it? How would you deploy it for everyone else to use?


### pluralsight recap

- Where does a service broker have to be deployed?

> It just needs to be deployed somewhere that the cloud controller can reach it via an HTTPS call. It can live inside PCF as an application or outside of it

- Why provide unique credentials per binding?

> It's the recommended best pratice so that unbinding doesn't affect other applications other than the application being unbound

- Can service broker support an upgrade or downgrade of a service?

> Upgrade support

- The borker is required by the cloud controller to respond within how many seconds?

> 60 seconds

- Does provisioning have to be done synchronously?

> No, it can be done asynchronously if you have a really long provisioning times. There's another endpoint to be implemented.

- Do all services have to be bindable?

> No, they don't
