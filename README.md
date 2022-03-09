# azure

## everything-as-code-workshop

## User story:

As an engineer, I want to create infrastructure in azure cloud so that I can deploy and run my simple website in development and in production

### Assumptions:

I have the following to get started:
- github account within organisation
- repository for my website code
- repository for my infrastructure code
- terraform cloud account within organisation
- azure account
- azure Subscription

### Steps:

> Show and walk through repositories: [GitHub Org](https://github.com/everything-as-code-workshop)

> Show and walk through [terraform cloud](https://app.terraform.io/app/everything-as-code-workshop/workspaces)

> Show and walk through [Azure](https://portal.azure.com/#@richardeverythingascodework.onmicrosoft.com/dashboard/private/ea654e9b-81e4-45b4-9884-da1abb09507c) subscription

#### Azure service accounts

- create service account so I can use it to deploy infrastructure
- create service account so I can use it to deploy my website

```bash
sh az-ad-sp.sh
```

> Show the [script](https://github.com/everything-as-code-workshop/infra/blob/main/scripts/az-ad-sp.sh)

> Show where terraform secret is [stored](https://app.terraform.io/app/everything-as-code-workshop/settings/varsets)

> Show where GitHub secret is [stored](https://github.com/everything-as-code-workshop/website/settings/secrets/actions/AZURE_CREDENTIALS)

### DEV environment

- run:

```bash
terraform init && terraform apply -auto-approve
```

> How this ^^ works

> Walk through resources created in dev

### PROD environment

- run:

```bash
sh setup.sh prod
```

> What this ^^ does

- run:

```bash
terraform init && terraform apply -auto-approve
```

> How this ^^ works

### Deploy website

> re-run [workflow](https://github.com/everything-as-code-workshop/website/actions/workflows/build_deploy.yaml)

> What happens here ^^

> Walk through resources created in prod

> Check website deployment

## Summary

I can deploy website to azure

## Bonus content

> KeyVault soft delete

> terraform destroy

> terraform cloud configuration as code

