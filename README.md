# api-gateway-dev-portal

## Step 1: Go to the API Gateway Serverless Developer Portal page in the AWS Serverless Application Repository.
```
https://serverlessrepo.aws.amazon.com/applications/arn:aws:serverlessrepo:us-east-1:563878140293:applications~api-gateway-dev-portal
```

## Step 2: Choose Deploy

## Step 3: In the Lambda console, enter the required developer portal stack parameters under Application settings.
```
- ArtifactsS3BucketName: 623552185285-bbsdm-api-gateway-dev-portal-artifacts
- CognitoDomainNameOrPrefix: bbsdm-api
- DevPortalSiteS3BucketName: 623552185285-bbsdm-api-gateway-dev-portal-site
```

## Step 4: Select the check box next to I acknowledge that this app creates custom IAM roles and resource policies.

## Step 5: Choose Deploy

## Step 6: Create an Admin User
- In your developer portal, choose Register.
- Enter an email address and password and choose Register.
- In a separate browser tab, sign in to the Amazon Cognito console.
- Choose Manage User Pools.
- Choose the user pool for your developer portal that you set when you deployed the developer portal.
- Choose the user to promote to administrator.
- From the dropdown menu, choose the {stackname}-dev-portalAdminsGroup, where {stackname} is the stack name from when you deployed the developer portal.
- Choose Add to group.
- In your developer portal, log out and log back in using the same credentials. You should now see an Admin Panel link in the upper right corner, next to My Dashboard.

## Step 7: Publish an API Gateway managed API to your developer portal
### Step 7.1: Make an API Gateway managed API available for publishing
- If you haven't already done so, deploy the API to a stage.
- If you haven't already done so, create a usage plan and associate it with the API stage for the deployed API.
- Sign in to the Developer Portal and go to the Admin Panel.
- You should see the API in the Admin Panel API list. In the API list, APIs are grouped by usage plan. The Not Subscribable No Usage Plan group lists the APIs that aren't associated with a usage plan.
### Step 7.2: Make the API Gateway managed API visible in the developer portal
- In the Admin Panel API list, check the Displayed value for your API. When it's first uploaded, this value is set to False.
- To make the API visible in the developer portal, choose the False button. Its value changes to True, which indicates that the API is now visible.
- Navigate to the APIs panel to see the developer portal as your customers see it. You should see your API listed in the left navigation column. If the API is deployed to a stage that's associated with a usage plan, you should see a Subscribe button for the API. This button causes the customer's API key to be associated with the usage plan that the API is associated with.
### Step 7.3 Enable SDK Generation
- In the Admin Panel API list, choose the Disabled button. Its value changes to Enabled, which indicates that SDK generation is now allowed.
- Navigate to the APIs panel and choose your API in the left navigation column. You should now see Download SDK and Export API buttons.

## Reference: 
- https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-developer-portal.html#apigateway-developer-portal-create
