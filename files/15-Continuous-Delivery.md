## Continuous Delivery

- What is Continuous Integration? Continuous Delivery? Continuous Deployment?

> Continuous Delivery - build software so that it can be released to production at any time

- How does Continuous Delivery compare to traditional development methodologies?

> Waterfall application delivery - high risk. Low feedback

> CD - several smaller deployments reduce risk but increase feedback

- Can you name some common Continuous Delivery tools?

- Can you outline the basic workflow behind Continuous Delivery?

> 1. Dev push to repo
> 2. CD provider poll for changes
> 3. CD provider run build and tests
> 4. CD provider start feedback loop to actor
> 5. CD provider push artifact to binary repo
> 6. CD provider pull artifact from binary repo
> 7. CD provider push artifact to environment
> 8. CD provider run more tests on environment


### pluralsight recap

- What are some of the continuous delivery strategies we talked about?

>  - Implement continuous integration
>  - Don't create application environment specific packages
>  - Blue-Green deployments

- Does continuous delivery means continuous deployment?

> No, it's not. Continuous deployment means every commit is pushed directly into production assuming it passes its test. Continuous delivery means every change can be deployed at production at anytime.

- What are some of the benefits of continuous delivery?

>  - Reducing risk
>  - Increasing feedback
