# Commands

Init project and CDK:

```sh
git init
yarn init -y
yarn add aws-cdk -D # add aws-cdk runner
mkdir cdk && cd cdk && npx cdk init app --language=typescript # create cdk boilerplate project
# start making reference adjustments
mv cdk.json ..
mv tsconfig.json ..
mv jest.config.js ..

cd ..
```

> Edit `cdk.json`
> Change references: <https://dev.to/alexvladut/how-to-add-aws-cdk-to-an-existing-project-2d30>

Update references:

```sh
yarn add aws-cdk-lib constructs
mkdir -p infra/src/
cp cdk/bin/cdk.ts infra/src/main.ts
mkdir -p infra/src/app/
cp cdk/lib/cdk-stack.ts infra/src/app/
mv cdk/test infra/
mv infra/test/cdk.test.ts infra/test/main.test.ts
```

> Edit `infra/src/main.ts` || [fix InfraStack path]

Remove cdk boilerplate:

```sh
rm -fr cdk
```

Setup for development:

```sh
yarn add -D typescript # add typescript
yarn add -D ts-node # add ts-node
yarn add -D jest # add jest
yarn add -D ts-jest # add jest typescript support
yarn add -D @types/jest # add jest types
yarn add -D @types/node # read environment variables
yarn add source-map-support
yarn add -D @types/source-map-support
yarn add -D rimraf
```
