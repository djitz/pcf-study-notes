## Buildpacks

- What is a buildpack? Why are they important?
> a combination of scripts that assembles runtimes, containers, frameworks, and your application into a droplet.
>
> droplets run inside PCF containers, which run inside Execution Agents (Cell VMs).
>
> build packs are responsible for preparing the machine image for an application

- Can you name some buildpacks?

> Official: 
> - Binary
> - Go
> - Java
> - .Net Core
> - Node.js
> - PHP
> - Python
> - Ruby
> - Staticfile


- How does Cloud Foundry know which buildpacks to run?

> During staging, each buildpack has a position in a priority list (`cf buildpacks`). CF checks if the buildpack in position 1 is a compatible buildpack. If not, CF moves on to the next buildpacks until the correct buildpack is found. If no buildpack is compatible, `cf push` fails.

- How does a buildpack work? Are you aware of the scripts that run and how  they might be written or modified?

> scripts:
> - `bin/detect`
> inspect application to see if the buildpack should be applied
> - `bin/compile` 
> creates droplet by combining application with runtime, container, packages, libraries (downloading them if necessary, kept in cache thereafter)
> - `bin/release`
> build application start command

- Can you tell what buildpack was used when an application was deployed?
> `cf app APP_NAME` gives the details of the buildpack used for the application.

- Why might you customize a buildpack? In general, would you know what to do?
> If your application uses a language or framework that the Cloud Foundry system


## Pluralsight Recap
- So which script is responsible for building the droplet? 
> The answer is the compile script.
		
- How do buildpacks help with managing CVEs or security issues? 
> Instead of patching systems manually, simply upload the patch buildpacks and then restage your applications. It's much, much easier to manage that way
		
- Would a cf restart be sufficient instead of a cf restage? Why not? 
> it really wouldn't be sufficient, because the droplet needs to be rebuilt. 
> If you recall, we set the configuration parameter to set the Java version. And when you do that and issue the cf restage command, that environment variable is available to the staging process, because it's being run in a container. All the same environment variables are available there. And it's going to go ahead and use that particular version of the JRE. 
		
- What other items are easily customized with the Java buildpack? 
> We talked about one, the Tomcat version. 
> Also, the JRE implementation. So, for instance, you could use Oracle. 
> if you wanted to get into managing the trustStore, you could investigate the documentation on that as well. 
