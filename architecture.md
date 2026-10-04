# Architecture

User
  ↓
IAM Tag Enforcement Policy
  ↓
EC2 Creation Request
  ↓
Missing required tags?
  ├── YES → BLOCKED ❌
  └── NO  → EC2 Created ✅
                ↓
           AWS Config
                ↓
       COMPLIANT / NON_COMPLIANT
                ↓
          EventBridge
                ↓
              SNS

AWS Config
    ↓
S3
(Config data storage)
