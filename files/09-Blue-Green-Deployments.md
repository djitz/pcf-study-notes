## Blue-Green Deployments

- What is a blue-green deployment? Why would you use it?

> it's a technique that reduces downtime and risk by running two identical production environments called Blue and Green.

> This technique can eliminate downtime due to application deployment. Blue-green deployment also reduces risk; if something unexpected happens with your new version on Green, you can immediately roll back to the last version by switching back to Blue.

- How do you map and unmap route with cf?

> `cf map-route APP_NAME DOMAIN [--hostname HOSTNAME] [--path PATH]`

> `cf unmap-route APP_NAME DOMAIN [--hostname HOSTNAME] [--path PATH]`

- How does route mapping enable a blue-green deployment?

> by routing the existing domain to the Green 

- What other steps are involved in a blue-green deployment?


### pluralsight recap

- What is the purpose of a Blue-Green deployment?
> To achieve no downtime when managing multiple versions of your application

- How is the distribution of traffic handled when running multiple versions of an application? 
> It's based on the percentage of app instances that is running, and traffic will be distributed accordingly

- True of False. When releasing a new version of an application, adding a new non-nullable field to a database table is an acceptable Blue-Green strategy?
> False.
> If it's a new non-nullable field without a default value then the old version of the application will run into problems when your application deploys.

- How would a rollback situation be handled using a Blue-Green deployment? 
> Unmap the production route from the next version of the application.

- What other design implications does running at least two versions of the same time have on your application?
> Changes need to be backwards compatible and non-destructive


### pluralsight exercise questions

- How would a rollback situation be handled using a blue-green deployment?

- What other design implications does running at least two versions at the same time have on your applications? Do you do blue-green deployments today? How is this different?
