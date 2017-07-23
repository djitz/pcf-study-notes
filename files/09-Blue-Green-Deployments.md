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
