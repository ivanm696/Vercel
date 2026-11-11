# Vercel CLI Overview

Vercel gives you multiple ways to interact with and configure your Vercel projects. With the command-line interface (CLI), you can interact with the Vercel platform using a terminal or an automated system.

If you'd like to interface with the platform programmatically, check out the [REST API documentation](https://vercel.com/docs/rest-api).

## Installing Vercel CLI

To download and install Vercel CLI, run one of the following commands:

```bash
pnpm i -g vercel
yarn global add vercel
npm i -g vercel
bun add -g vercel
```

## Updating Vercel CLI

When a new release of Vercel CLI is available, running any command will show a notice. If you've installed the CLI via npm or Yarn, the easiest way to update it is by rerunning the install command:

```bash
pnpm i -g vercel@latest
yarn global add vercel@latest
npm i -g vercel@latest
bun add -g vercel@latest
```

If you see permission errors, please read npm's [official guide](https://docs.npmjs.com/resolving-eacces-permissions-errors-when-installing-packages-globally).

To see what changed in each version, browse the [release notes](https://vercel.com/docs/cli/release-notes).

## Checking the version

```bash
vercel --version
```

## Using in a CI/CD environment

Vercel CLI requires you to log in and authenticate before accessing resources or performing administrative tasks. In a terminal environment, you can use [`vercel login`](https://vercel.com/docs/cli/login), which requires manual input. If you don't have a Vercel account yet, you can create one with [`vercel signup`](https://vercel.com/docs/cli/signup).

If you need non-interactive authentication in CI/CD, use one of the following methods:

- Set the `VERCEL_TOKEN` environment variable
- Pass the [`--token` option](https://vercel.com/docs/cli/global-options#token) to the command

Using `VERCEL_TOKEN` is recommended because it avoids exposing the token in command-line arguments.

## Available commands

### activity

View activity events for your Vercel project or team.

```bash
vercel activity
vercel activity --all --since 30d
vercel activity --type deployment --since 7d
```

[Learn more about the activity command](https://vercel.com/docs/cli/activity)

### agent

Generate an `AGENTS.md` file with Vercel deployment best practices for coding agents.

```bash
vercel agent init
vercel agent init --yes
```

[Learn more about the agent command](https://vercel.com/docs/cli/agent)

### alias

Apply custom domain aliases to your Vercel deployments.

```bash
vercel alias set [deployment-url] [custom-domain]
vercel alias remove [custom-domain]
vercel alias list
```

[Learn more about the alias command](https://vercel.com/docs/cli/alias)

### api

Make authenticated HTTP requests to the Vercel API.

```bash
vercel api [endpoint]
vercel api /v2/user
vercel api /v9/projects -X POST -F name=my-project
```

[Learn more about the api command](https://vercel.com/docs/cli/api)

### build

Build a Vercel project locally or in your own CI environment.

```bash
vercel build
vercel build --prod
```

[Learn more about the build command](https://vercel.com/docs/cli/build)

### deploy

Deploy your Vercel projects. Default command when no subcommand is specified.

```bash
vercel
vercel deploy
vercel deploy --prod
```

[Learn more about the deploy command](https://vercel.com/docs/cli/deploy)

### dev

Replicate the Vercel deployment environment locally and test your project.

```bash
vercel dev
vercel dev --listen 3000
```

[Learn more about the dev command](https://vercel.com/docs/cli/dev)

### dns

Manage your DNS records for your domains.

```bash
vercel dns list [domain]
vercel dns add [domain] [name] [type] [value]
vercel dns remove [record-id]
```

[Learn more about the dns command](https://vercel.com/docs/cli/dns)

### env

Manage environment variables in your Vercel projects.

```bash
vercel env list
vercel env add [name] --environment [environment]
vercel env pull [file]
```

[Learn more about the env command](https://vercel.com/docs/cli/env)

### git

Manage your Git provider connections.

```bash
vercel git connect
vercel git connect [git-url]
vercel git disconnect
```

[Learn more about the git command](https://vercel.com/docs/cli/git)

### help

Get information about all available Vercel CLI commands.

```bash
vercel help
vercel help [command]
```

[Learn more about the help command](https://vercel.com/docs/cli/help)

### init

Initialize example Vercel projects locally from the examples repository.

```bash
vercel init
vercel init [framework-name]
```

[Learn more about the init command](https://vercel.com/docs/cli/init)

### link

Link a local directory to a Vercel project, or add projects to an existing repository link.

```bash
vercel link
vercel link --cwd [path-to-directory]
vercel link --repo
```

[Learn more about the link command](https://vercel.com/docs/cli/link)

### login

Log in to your Vercel account through the CLI.

```bash
vercel login
```

[Learn more about the login command](https://vercel.com/docs/cli/login)

### logout

Log out from your Vercel account through the CLI.

```bash
vercel logout
```

[Learn more about the logout command](https://vercel.com/docs/cli/logout)

### logs

Query runtime log entries and CDN request records for your project.

```bash
vercel logs
vercel logs requests
vercel logs --deployment [deployment-url]
```

[Learn more about the logs command](https://vercel.com/docs/cli/logs)

### project

List, create, inspect, delete, and manage your Vercel projects.

```bash
vercel project list
vercel project create [project-name]
vercel project inspect [project-name]
```

[Learn more about the project command](https://vercel.com/docs/cli/project)

### pull

Update your local project with remote environment variables and project settings.

```bash
vercel pull
vercel pull --environment=production
```

[Learn more about the pull command](https://vercel.com/docs/cli/pull)

### redeploy

Rebuild and redeploy an existing deployment.

```bash
vercel redeploy [deployment-id-or-url]
```

[Learn more about the redeploy command](https://vercel.com/docs/cli/redeploy)

### rollback

Roll back production deployments to previous deployments.

```bash
vercel rollback
vercel rollback [deployment-id-or-url]
```

[Learn more about the rollback command](https://vercel.com/docs/cli/rollback)

### switch

Switch between different team scopes.

```bash
vercel switch
vercel switch [team-slug]
```

[Learn more about the switch command](https://vercel.com/docs/cli/switch)

### teams

List, add, remove, and manage your teams.

```bash
vercel teams list
vercel teams create
vercel teams invite [email]
```

[Learn more about the teams command](https://vercel.com/docs/cli/teams)

## Related guides

- [The Complete Guide to Vercel Connect](https://vercel.com/kb/guide/vercel-connect)
- [Does Vercel support Docker deployments?](https://vercel.com/kb/guide/does-vercel-support-docker-deployments)
- [Build a fullstack app with Next.js 16 and Prisma Postgres](https://vercel.com/kb/guide/nextjs-prisma-postgres)
- [Using coding agents to procure Vercel Marketplace integrations](https://vercel.com/kb/guide/using-coding-agents-to-procure-vercel-marketplace-integrations)

## More resources

- [Vercel documentation](https://vercel.com/docs)
- [Vercel knowledge base](https://vercel.com/kb)
- [Vercel account tokens](https://vercel.com/account/tokens)
- [Vercel status](https://vercel.com/status)

