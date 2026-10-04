# Implementation

## 1. Tagging Strategy

The project defines four mandatory tags for AWS resources:

- Project
- Environment
- Owner
- CostCenter

## 2. Preventive Enforcement

An IAM policy is used to prevent EC2 instances from being created when any mandatory tag is missing.

If all required tags are provided, the EC2 creation request is allowed.

## 3. Compliance Monitoring

AWS Config uses the `required-tags` managed rule to evaluate EC2 instances.

- COMPLIANT: All required tags are present.
- NON_COMPLIANT: One or more required tags are missing.

## 4. Testing

The solution was tested using two scenarios:

1. EC2 creation without required tags was blocked by IAM.
2. EC2 creation with all required tags was successfully allowed.

AWS Config was also used to verify tag compliance.

## 5. Bottleneck Cases

- Missing resource ownership information
- Inaccurate cost allocation
- Inconsistent tagging across teams
- Difficulty managing large numbers of resources
- Manual compliance monitoring

## 6. Real-World Applications

- Enterprise cloud governance
- FinOps and cost management
- Development, testing and production environments
- Multi-team AWS environments
- Compliance and auditing
- Resource ownership tracking

## 7. Future Scope

- Automated remediation of missing tags
- EventBridge-based compliance workflows
- SNS notifications
- Support for additional AWS resource types
- Centralized tagging dashboards
