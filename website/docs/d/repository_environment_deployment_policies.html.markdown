---
layout: "github"
page_title: "GitHub: github_repository_environment_deployment_policies"
description: |-
  Get the list of deployment policies for a given repo / env.
---

# github_repository_environment_deployment_policies

Use this data source to retrieve deployment policies for a repository / environment.

## Example Usage

```hcl
data "github_repository_environment_deployment_policies" "example" {
    repository = "example-repository"
    environment_name = "env_name"
}
```

## Argument Reference

- `repository` - (Required) Name of the repository to retrieve the deployment policies from.

- `environment_name` - (Required) Name of the environment to retrieve the deployment policies from.

## Attributes Reference

- `deployment_policies` - The list of this repository / environment deployment policies. Each element of `deployment_policies` has the following attributes:
  - `id` - Id of the policy.
  - `name` - The name pattern that branches or tags must match in order to deploy to the environment.
  - `type` - Whether this rule targets a branch or tag.
