# org-management

Configuration of organization membership and automation to apply this
membership via GitHub Actions automation.

## Automation Setup

We use [Peribolos](https://docs.prow.k8s.io/docs/components/cli-tools/peribolos/) to manage
organization membership. The membership is defined in [config/organization_membership.yaml](config/organization_membership.yaml).
We then use a GitHub action, defined in [.github/workflows/apply-org-membership.yaml](.github/workflows/apply-org-membership.yaml)
to automatically apply the membership after any change to the membership config.

This automation depends on a GitHub ]personal access token with read and write
permissions to organization members. The token value is saved in this repository as a
repository secret with name `ORG_MANAGEMENT_TOKEN`.