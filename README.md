# AWS Cognito React - Revamped

![signin](./logo.png)

Reference implementation / boilerplate for AWS Cognito user management

## AWS Cognito Infrastructure setup

To help deploy the AWS Cognito infrastructure I've create an Amazon Cloud Development (CDK) script

CDK set up instructions can be found [here](https://docs.aws.amazon.com/cdk/latest/guide/cli.html)

CDK deploy instructions

```bash
cd cdk
npm run cdk bootstrap   # only needed first time
npm run cdk deploy
```

After deployment copy the userPoolId and userPoolClientId values from the command line window; you will need these values in the app config step

## App Configuration

Setup the Cognito environment values buy creating app/.env.local file and adding the following

```bash
VITE_COGNITO_USERPOOL_ID=YOUR_USER_POOL_ID
VITE_COGNITO_CLIENT_ID=YOUR_CLIENT_ID
```

Create React App has been used to setup the development process so the next steps should be familiar

```bash
cd app
npm install
npm dev
```

## Other Solutions

[Firebase Auth](https://firebase.google.com/products/auth?gclid=Cj0KCQiAtqL-BRC0ARIsAF4K3WFgWD7NC4y4eJfdGZg68t4ovEoqpGrqWWk2kj1_htu5e2844DCBKVoaAhl_EALw_wcB) - Great for mobile and web. Fairly limited but easy to use. Integrates really nicely with other Firebase services

[Auth0](https://auth0.com/) - Comes with comprehensive and feature rich frontend. Seems to quicky get expensive but a very safe option

[Keycloak](https://www.keycloak.org/) - Excellent feature rich Enterprise service that offers fully themable frontend. No Cloud solution but easy to deploy to AWS using [this](https://github.com/dbroadhurst/aws-cdk-fargate-keycloak) CDK script

## Useful References

<https://www.npmjs.com/package/amazon-cognito-identity-js>

<https://docs.aws.amazon.com/cdk/api/latest/docs/aws-cognito-readme.html>

<https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-pools-social-idp.html>

<https://docs.aws.amazon.com/cdk/latest/guide/getting_started.html>
