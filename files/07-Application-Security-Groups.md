## Application Security Groups

- What is an application security group (ASG)? What does it do?

- How do you define one?

- What can an ASG apply to?

- What is the difference between white and black listing? Which do you use when defining an ASG?


---
## pluralsight questions

- Do application security groups use a whitelist or blacklist approach to firewall rules? 
- What are the differences in the two application security groups that you looked at? 
- What are some reasons why security groups could be used?
- How could security groups affect the staging and running of your application?

- What are the differences between the different types (running and staging) of security groups?
Imagine a situation in which an application is bound to a backing database service and deployed to PCF.

- In the absence of ASG bindings, would the application be able to communicate with the backing service?
Let's assume that the backing database is a MySQL instance, which by default accepts connections on port 3306.

- As a Cloud Foundry administrator, what would you have to do in order to allow any running application to communicate with this type of backing service?

- What would your security group rules JSON file look like? Should the rules allow all ports over all ip addresses? Can the rules be constrained to allow only port 3306 over a specific range of ip addresses? Try to construct a security group rules file (JSON) that you'd use to create and then bind to running applications. What command would you use to define the security group? What would you name it? What command would you use to bind it?

### recap questions

- As a developer what cf commands can be used to investigate and understand what's going on with application security groups?

> - `cf security-groups`
> - `cf security-group APP_NAME`

- Do application security groups use a white list or black list approach to firewall rules?

> White list

- What is the relationship between running security groups and space security groups?

> It's a union of both of those put together. So if you've allowed any outbound connection from either running security group or space security group your application won't be able to take advantage of that.

- What are some reasons why security groups could be used?

> - Protection against typically trusted resources like employees and preventing them from doing bad things
> - Limit your exposure and only allowing access to what application should have access to
> - Force applications to really use the applications to use the appropriate APIs. In a microservie based architecture you really want to force all of the data access through the appropriate application rather than side stepping that application and accessing the data directly
