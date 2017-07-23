# Command Line Utility `cf`

- Do you know what `cf` is used to perform the following:

-- View organizations?
> `cf orgs`

-- View routes?
> `cf routes`

-- View spaces?
> `cf spaces`

-- View a single organization, route or space?
> `cf org ORG`
> `cf route ROUTE`
> `cf space SPACE`

-- Deploy an application?
> `cf push`

-- Select a space and/or organization to deploy to?
> `cf target [-o ORG] [-s SPACE]`

-- View logs?
> `cf logs APP_NAME`

-- Connect (login) to the Cloud Controller?
> `cf login [-a API_URL] [-u USERNAME] [-p PASSWORD] [-o ORG] [-s SPACE]`

-- Start, stop or restart an application?
> `cf start APP_NAME`
> `cf stop APP_NAME`
> `cf restart APP_NAME`

-- What does `cf target` do? What information does it give you?
> it set or view the targeted org or space
> - `API endpoint: https://api.run.pivotal.io (API version: 2.6.0)`
> - `User: pchapman@pivotal.io`
> - `Org: pivotaledu`
> - `Space: development`
