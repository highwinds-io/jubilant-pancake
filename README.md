# jubilant-pancake

# Problem Statement
Terraform needs multiple steps to apply successfully.  Plan should be executed before an apply and the output of the plan should be used in order to ensure that the approved plan is what is applied.  Not using the plan output could result in unintended consequences.  The file generated by the plan also contains secrets and this file needs to be saved in a secure area and not as a GitHub artifact.

It is possible that even upon a successful plan that an apply fails.  Given that a PR should not be merged into the main branch until it has been successfully applied to the given environment.  Only after an apply is the desired state configuration the actual configuration.

# Project Goals

- [X] Approval Flow, the output of a plan must be approved to apply
- [X] Sanitized output of plan must be available for PR review and not in the workflow run log
- [X] Plan output must be used for apply
- [X] Plan output must be saved securely not as an artifact
- [ ] Should support multiple Terraform folders in a single repo
- [ ] Credentials used for plan must be limited in order to not allow the possibility of a plan to modify resources
- [ ] Multiple environments should be used to allow approval of apply to prod environment
- [ ] Must allow for plan/apply to multiple environments dev/test/prod etc
- [X] Use Subscription Id, Client Id and Tenant Id in OIDC connectivity are provided by environments
- [ ] Prevent PR acceptance into main until Apply is complete
      Requires usage of branch protection rules


