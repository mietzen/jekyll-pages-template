# Jekyll CI Template

This template will automatically build and deploy GH-Pages for you.
Simply place a your Jekyll Page at the root of the repo.

## Usage

Click on `Use this template`:

![](https://github.com/mietzen/docker-ci-template/blob/8cf107cd387f7301ac6625cf324416965b362974/use-template.png?raw=true)


## Dependabot

For working dependabot setup follow these steps.

### Github Token App

For the workflow to run you need to create a GitHub-App to generate tokens, follow:

[https://github.com/actions/create-github-app-token](https://github.com/actions/create-github-app-token?tab=readme-ov-file#usage)

If you follow the instructions above you should have your App listed under `Settings -> GitHub Apps`:

![](https://github.com/mietzen/docker-ci-template/blob/313cb3c73a4ce2a43397a3a749bfcc238c967367/github-app.png?raw=true)

### Repository config

You need to activate `auto-merge` under `Settings -> General -> Pull Requests`:

![](https://github.com/mietzen/docker-ci-template/blob/313cb3c73a4ce2a43397a3a749bfcc238c967367/auto-merge.png?raw=true)

and setup the branch protection for `main` under `Settings -> Branch -> Add branch protection rule`, for `Branch name pattern` type in `main`:

Then apply the following settings:

![](https://github.com/mietzen/docker-ci-template/blob/313cb3c73a4ce2a43397a3a749bfcc238c967367/branch-protection.png?raw=true)

**The status check `Build` is only available after the `deploy.yml` ran at least one time. You can trigger the workflow by simply opening a Pull-Request e.g. to add your Pages.**

#### Secrets

You need to add the following secrets as repository secrets in the Dependabot section:

- `APP_ID`
- `APP_PRIVATE_KEY`

![](https://github.com/mietzen/docker-ci-template/blob/313cb3c73a4ce2a43397a3a749bfcc238c967367/dependabot-secrets.png?raw=true)
