# AWS Architecture – GRC Perspective

## Basic AWS Structure

AWS operates infrastructure across multiple geographic Regions.

A simplified view:

AWS
│
├── Region
│   ├── Availability Zone
│   └── Availability Zone
│
├── Identity and Access Management (IAM)
│
├── Logging and Monitoring
│
└── AWS Resources


## GRC Relevance

| AWS Concept | GRC Relevance | Example Evidence |
|---|---|---|
| Region | Data residency and regulatory requirements | Resource location/configuration |
| Availability Zone | Resilience and availability | Architecture/configuration |
| IAM | Access control and least privilege | IAM users, roles and policies |
| Logging | Audit trails and security monitoring | CloudTrail/log configuration |
| AWS APIs | Automated evidence collection | API responses |
| AWS Resources | Assets within the control environment | Resource inventory |


## From Manual GRC to GRC Engineering

A traditional GRC assessment might request evidence manually:

**Control requirement**

> Administrative access must be restricted to authorised users.

**Traditional evidence**

Screenshot or exported list of privileged users.

**GRC Engineering approach**

AWS configuration could potentially be queried programmatically:

AWS → API → Configuration → Control Test → Evidence

This could allow control evidence to be collected consistently and repeatedly.


## What I Want to Learn

As my AWS knowledge develops, I want to understand how to:

1. Identify AWS resources relevant to security controls.
2. Retrieve configuration through AWS APIs.
3. Evaluate configuration against control requirements.
4. Generate evidence automatically.
5. Map technical tests to frameworks such as ISO 27001.
