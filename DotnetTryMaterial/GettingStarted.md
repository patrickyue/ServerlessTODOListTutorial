# Getting Started

To get started with this tutorial you need a few things setup first.

## Have an AWS Account

To follow along with this tutorial you will need an AWS account. An AWS 
account can be setup <a href="https://portal.aws.amazon.com/billing/signup" target="_blank">here</a>. There is a <a href="https://aws.amazon.com/free/" target="_blank">free tier</a> for the first year of
AWS accounts. The resources created in this tutorial will qualify under the free tier. 

## AWS Credentials

To access AWS you will need AWS credentials which are made up of an Access Key ID and a Secret Key. The credentials need to be saved as a profile with either the <a target="_blank" href="https://docs.aws.amazon.com/toolkit-for-visual-studio/latest/user-guide/getting-set-up.html">AWS Toolkit for Visual Studio</a> or in the <a target="_blank" href="https://docs.aws.amazon.com/sdk-for-net/v3/developer-guide/net-dg-config-creds.html#creds-file">Shared Credentials</a> file. The AWS SDK for .NET will
use the credentials stored with a profile to make authenticated calls to AWS.

For new users setting up their first profile the name **default** is recommended for the profile name. When a profile isn't specified when using any of the AWS sdks or tools they will use the **default** profile if it exists.

## Security Concerns

The dotnet try tool may look like it is running your code in the browser your AWS credentials are never accessed through the browser or sent over the network.
At a high level what dotnet try is doing is using Blazor and SignalR to talk back to its ASP.NET Core backend. The backend is basically running Roslyn
over the Snippets .NET project in this repository to get intellisense information. When you click the execute button in a code box the backend
takes the code in the code box, injects into the Snippets project, builds it and then executes the console application.

The code boxes are sending code over to be executed in the Snippets project which has access to the machine running this tutorial. For that reason
this tutorial is only meant to run on localhost and not to be shared across a network.

## Choosing a credentials profile and aws region

To build our application we need to choose which AWS credentials profile
to use and what AWS region to use.

One of the ways the AWS SDKs will look for AWS credentials when a profile isn't specified is the existence of the **AWS_PROFILE** and **AWS_REGION** environment variables. Throughout this tutorial whenever a code snippet is run the **AWS_PROFILE** and **AWS_REGION** environment variable will be set in the 
snippets process so that the code snippets will use the appropriate profile and region when making calls to AWS.

# Set AWS Credentials Profile

Enter the profile you wish to use for this tutorial and click the execute button.

```cs --source-file ./Snippets/SetConfiguration.cs --project ./Snippets/Snippets.csproj --region current_aws_profile
```

# Set AWS Region

Enter the region you wish to use for this tutorial and click the execute button. Regions are set with a string like us-east-1 for east coast US (Virginia) , us-west-2 for west coast US (Oregon) and eu-west-1 for Dublin. For a full list of regions look <a target="_blank" href="https://docs.aws.amazon.com/general/latest/gr/rande.html">here</a>.

```cs --source-file ./Snippets/SetConfiguration.cs --project ./Snippets/Snippets.csproj --region current_aws_region
```

<!-- Generated Navigation -->
---

* **Getting Started**
* [What is a serverless application?](./WhatIsServerless.md)
* [Common AWS Serverless Services](./CommonServerlessServices.md)
* [What are we going to build in this tutorial?](./WhatAreWeBuilding.md)
* [TODO List AWS Services Used](./TODOListServices.md)
* [Using DynamoDB to store TODO Lists](./DynamoDBModule/WhatIsDynamoDB.md)
* [Handling service events with Lambda](./StreamProcessing/ServiceEvents.md)
* [Getting ASP.NET Core ready for Serverless](./ASP.NETCoreFrontend/TheFrontend.md)
* [Deploying ASP.NET Core as a Serverless Application](./DeployingFrontend/DeployingFrontend.md)
* [Tear Down](./TearDown.md)
* [Final Wrap Up](./FinalWrapup.md)

Continue on to next page: [What is a serverless application?](./WhatIsServerless.md)

