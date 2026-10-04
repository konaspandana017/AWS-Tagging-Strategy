# AWS Config Required Tags Rule

## Rule Name
required-tags

## Rule Identifier
REQUIRED_TAGS

## Resource Type
AWS::EC2::Instance

## Required Tags
- Project
- Environment
- Owner
- CostCenter

## Evaluation
The rule evaluates EC2 instances whenever their configuration changes.

## Compliance
- COMPLIANT – all required tags are present.
- NON_COMPLIANT – one or more required tags are missing.

## Remediation
Missing tags can be added to the EC2 instance and the resource can be re-evaluated.
