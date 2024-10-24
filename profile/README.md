# Velocity

Welcome to the Velocity Engineering repositories. 

## Rules

1. The branch structure for almost** all repos is as follows:

  - `develop`: Base for all development work.
  - `main`: Reflects the latest release in production.
  - `staging`: Used for deploying changes to production (if available). Please check the respective repositories for branching strategies that might differ.
  - `deploy/production`: Used for deploying to production and handling hotfixes (this branch will always match what is currently live in production environments).

``` mermaid
graph TD;
    A[develop] -->|Feature Branch| B[feature/*] 
    B -->|PR Review & Merge| A
    H -->|PR Review & Merge| A
    A -->|End of Cycle PR| C[deploy/production]
    A -->|Merge into| D[main]
    C -->|Hotfix Branch| E[hotfix/*]
    E -->|Merge into deploy/production & main| C & D
    A -->|Any Time| F[staging]
```

2. Always follow `gitflow` branching methedologies. E.g. `feature/*` or `bugfix/*` (where * is your branch name - it will be auto-generated for you by ClickUp). For more information on `gitflow` [Read More](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)
3. Pushing code directly to a server (Cowboy Coding) is **NOT ALLOWED** - not even in a crisis, as this could affect automations
4. Each repository will have specific rules, CI/CD pipelines etc. Please follow those.
5. Please create PRs for your work, into the `develop` branch.
6. When in doubt, ask.
