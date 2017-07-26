## Application Performance Monitor

- What is performance monitoring? How is it implemented for Cloud Foundry applications?

> - real-time monitoring of applications
- marketplace service

- Why is a buildpack involved?

> to include the APM agent in the droplet

- What APM tools are available with Cloud Foundry?

> New Relic, AppDynamics, Dynatrace


### pluralsight recap


- Why must Articulate and Attendee service be restaged as opposed to restarted?

> Because the droplet has to include the New Relic agent and to do that, our application droplet needs to be restaged

- How is this different from how you manage your APM tools today? Is this something that makes it easier for you to integrate your APM capabilities? 
