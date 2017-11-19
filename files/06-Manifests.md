## Manifests

- What is a manifest? What type of file is it? What is its purpose?

  > - describes the application deployment options
  > - YAML file
  > - automates subsequent deployments
  > - same options as `cf push` command

- How do you create a manifest?

  > - using text editor, or
  
  > - `cf create-app-manifest APP_NAME`

- If I specify a command in a manifest and on the command line what happens?

  > the `cf push` CLI options always take precedence over manifest file

- What happens if I don't specify a deployment option at all?

  > `cf push` will default all deployment options
