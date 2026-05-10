---
author: "Kyle Jones"
date_published: "September 23, 2024"
date_exported_from_medium: "November 10, 2025"
canonical_link: "https://medium.com/@kyle-t-jones/key-concepts-for-aws-cdk-constructs-stacks-and-apps-3efb391e67fc"
---

# Key concepts for AWS CDK: Constructs, Stacks, and Apps The AWS Cloud Development Kit (CDK) simplifies cloud infrastructure
provisioning. AWS CDK abstracts much of the complexity associated with...

### Key concepts for AWS CDK: Constructs, Stacks, and Apps
The AWS Cloud Development Kit (CDK) simplifies cloud infrastructure provisioning. AWS CDK abstracts much of the complexity associated with AWS services and makes cloud management more accessible. It integrates with AWS CloudFormation to provide a robust, scalable infrastructure management solution.

One of the foundational elements of AWS CDK is its use of constructs, stacks, and apps to organize and manage infrastructure. These concepts define how developers interact with and organize cloud infrastructure using AWS CDK.

#### **Constructs**
At the heart of CDK are constructs. Constructs are the basic building blocks of AWS CDK applications and represent AWS resources like S3 buckets, Lambda functions, and DynamoDB tables. Constructs encapsulate the configuration and management of AWS resources, making it easier for developers to define and deploy infrastructure.

Constructs are organized into three layers of abstraction:

**Level 1 (L1) Constructs:** These directly represent AWS CloudFormation resources. Each L1 construct corresponds 1:1 to an AWS resource, providing complete control over the configuration but requiring more manual setup. For instance, an L1 construct for an S3 bucket would require you to specify all the properties that CloudFormation supports.

**Level 2 (L2) Constructs:** These provide more abstract, opinionated constructs that simplify the configuration of AWS resources by setting sensible defaults and best practices. For example, an L2 construct for an S3 bucket might enable versioning or encryption by default, saving you the effort of manually specifying each option.

**Level 3 (L3) Constructs or Patterns:** These constructs represent high-level, reusable patterns for standard infrastructure setups. An L3 construct might combine multiple AWS services into a coherent, ready-to-deploy solution. For example, an L3 construct could configure a complete serverless application with an API Gateway, Lambda function, and DynamoDB table.

Constructs are written as classes in the supported CDK programming languages (e.g., TypeScript, Python), providing a programmatic way to define the behavior and configuration of AWS resources.

#### **Stacks**
A stack in AWS CDK is a collection of AWS resources defined and managed together. It represents a single unit of deployment in CloudFormation. Each CDK stack is synthesized into a CloudFormation template, which AWS CloudFormation uses to provision and manage the resources. Stacks are essential because they allow you to logically group related resources together.

**Benefits of Stacks**

**Isolation:** Resources within a stack can be isolated from other stacks, enabling more granular control and separation of concerns. For example, you might have a separate stack for networking resources (VPCs, subnets) and another for application resources (EC2 instances, S3 buckets).

**Cross-Stack References:** AWS CDK allows stacks to reference resources in other stacks. This is useful when sharing a resource, such as a VPC, between multiple applications.

**Separate Environments:** Each stack can be deployed to different AWS environments (regions or accounts), making it easier to maintain infrastructure across multiple environments (development, staging, production).

#### **Apps**
An app is the root of your AWS CDK application. It contains one or more stacks and orchestrates the deployment of the entire infrastructure. An app can represent a complete cloud environment, with multiple stacks defining various components.

Apps allow you to define your infrastructure code in a structured and modular way. Each app can contain multiple stacks, each stack can contain various constructs, and each construct can represent one or more AWS resources. This hierarchical structure ensures that your infrastructure is easy to manage, scale, and reuse.

### Related Stories
- [[Setting up AWS CDK for your projects](https://medium.com/@kylejones_47003/setting-up-aws-cdk-for-your-projects-713d1d518b9a)]
- [[Building cloud resources with AWS CDK](https://medium.com/@kylejones_47003/building-cloud-resources-with-aws-cdk-7a8ee677e309)]
- [[How AWS CDK turns code into CloudFormation Templates](https://medium.com/@kylejones_47003/how-aws-cdk-turns-code-into-cloudformation-templates-8f725301ef17)]
