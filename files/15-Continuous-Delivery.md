## Continuous Delivery

- What is Continuous Integration? Continuous Delivery? Continuous Deployment?

> Continuous Delivery - build software so that it can be released to production at any time

- How does Continuous Delivery compare to traditional development methodologies?

> Waterfall application delivery - high risk. Low feedback

> CD - several smaller deployments reduce risk but increase feedback

- Can you name some common Continuous Delivery tools?

- Can you outline the basic workflow behind Continuous Delivery?

> 1. Dev push to repo
2. CD provider poll for changes
3. CD provider run build and tests
4. CD provider start feedback loop to actor
5. CD provider push artifact to binary repo
6. CD provider pull artifact from binary repo
7. CD provider push artifact to environment
8. CD provider run more tests on environment
