# AWS Tagging Strategy and Enforcement

## Problem Statement
Implement a centralized AWS tagging strategy and enforcement mechanism to ensure resources are properly tagged for governance, ownership, environment tracking and cost management.

## Required Tags
- Project
- Environment
- Owner
- CostCenter

## AWS Services Used
- Amazon EC2 – Represents cloud resources
- AWS IAM – Controls permissions and prevents creation of resources without required tags
- AWS Config – Monitors resource configuration and tag compliance
- Amazon S3 – Stores AWS Config configuration data
- Amazon SNS – Notification service for compliance alerts
- Amazon EventBridge – Connects compliance events with notification workflows

## Project Flow

1. User attempts to create an EC2 instance.
2. IAM policy checks whether the required tags are included.
3. If required tags are missing, the EC2 creation request is blocked.
4. If all required tags are present, the EC2 instance is created.
5. AWS Config evaluates the EC2 instance against the required-tags rule.
6. The resource is marked COMPLIANT or NON_COMPLIANT.
7. Compliance events can be connected to EventBridge and SNS for notifications.
8. Missing tags can be added and the resource can be re-evaluated.

## Sample Tags

- Project: StudentPortal
- Environment: Development
- Owner: PlatformTeam
- CostCenter: EDU-ENG-001

## Key Features

- Preventive tag enforcement using IAM
- Automated compliance monitoring using AWS Config
- Detection of non-compliant resources
- Event-based notification architecture
- Centralized tagging strategy
- Support for cost allocation and resource ownership

## Real-World Applications

- Enterprise cloud governance
- FinOps and cost management
- Development, testing and production environments
- Multi-team AWS environments
- Compliance and auditing
- Resource ownership tracking

## Bottleneck Cases

- Resources created without required tags
- Incorrect or inconsistent tag values
- Difficulty identifying resource owners
- Inaccurate cost allocation
- Large numbers of resources requiring manual monitoring
- Lack of centralized cloud governance
