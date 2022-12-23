# TERRAFORM-VALIDATE-GH-ACTION

Repository containing Pixel System's Github Action to validate Terraform configuration with Pixel System standard.

- [TERRAFORM-VALIDATE-GH-ACTION](#TERRAFORM-VALIDATE-GH-ACTION)
  - [code-of-conduct](#code-of-conduct)
  - [github-action](#github-action)

## code-of-conduct

Go crazy on the pull requests :) ! The only requirements are:

> - Use _conventional-commits_.
> - Include _jira-tickets_ in your commits.
> - Create/Update the documentation of the use case you are creating, improving or fixing. **[Boy scout](https://biratkirat.medium.com/step-8-the-boy-scout-rule-robert-c-martin-uncle-bob-9ac839778385) rules apply**. That means, for example, if you fix an already existing workflow, please include the necessary documentation to help everybody. The rule of thumb is: _leave the place (just a little bit)better than when you came_.

### github-action

This action performs a [_terraform validate_](https://www.terraform.io/cli/commands/validate) on the IAC that is specified. The (required) inputs are _terraform-folder_ and _use-backend_.

example usage:

```yaml
name: CI
on:
  pull_request:
    branches: ["main"]
jobs:
  validate-iac:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: ohpensource/terraform-validate-gh-action@1.0.0.0
        name: validate-terraform
        with:
          terraform-folder: "terraform"
          use-backend: "false"
```
