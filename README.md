# Infrastructure deployment with CDK

This is a template/boilerplate for deploying AWS infrastructure with CDK.

## Initial setup

Bootstrap AWS CDK with the deployer AWS account:

> Note: AWS account should have Administrator Access policy attached.

```sh
yarn cdk bootstrap aws://<ACCOUNT>/<REGION> \
--cloudformation-execution-policies \
arn:aws:iam::aws:policy/AdministratorAccess \
aws://<ACCOUNT>/<REGION>

# Example:

yarn cdk bootstrap aws://098162465323/sa-east-1 \
--cloudformation-execution-policies \
arn:aws:iam::aws:policy/AdministratorAccess \
aws://098162465323/sa-east-1

```

## Development

Infrastructure definition is located in `infra/src/app/cdk-stack.ts`.

Main entrypoint for infrastructure stacks is defined at `infra/src/main.ts`.

## Deploy

Deploy & update existing infrastructure:

```sh

yarn deploy

```
