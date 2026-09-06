# AWS Service-to-Control Mapping

## Purpose

This document demonstrates how a GRC control requirement can be mapped to an AWS service, its technical configuration, and machine-readable evidence.

## Control Mapping Template

| Requirement | AWS Service | Configuration | Evidence Method | Expected State | Result |
|---|---|---|---|---|---|
| Control requirement | AWS service | Relevant technical configuration | CLI/API query | Expected configuration | Pass/Fail |

---

## Control 1 – Restrict Public Access to S3

### Requirement

Access to information stored in cloud services should be restricted to authorised users and should not be publicly accessible unless explicitly required.

### AWS Service

Amazon S3

### Configuration

S3 Block Public Access.

The following settings were evaluated:

- BlockPublicAcls
- IgnorePublicAcls
- BlockPublicPolicy
- RestrictPublicBuckets

### Evidence Collection

The configuration was queried using the AWS CLI:

    aws s3api get-public-access-block --bucket <bucket-name>

### Expected State

All four S3 Block Public Access settings should be set to `true`.

### Observed State

    BlockPublicAcls: true
    IgnorePublicAcls: true
    BlockPublicPolicy: true
    RestrictPublicBuckets: true

### Assessment

**PASS**

The observed configuration matched the expected state defined for this lab control.

---

## Control 2 – Encryption of S3 Data at Rest

### Requirement

Information stored in cloud services should be encrypted at rest.

### AWS Service

Amazon S3

### Configuration

Default server-side encryption.

### Evidence Collection

The configuration was queried using the AWS CLI:

    aws s3api get-bucket-encryption --bucket <bucket-name>

### Expected State

Default server-side encryption should be enabled.

### Observed State

    SSEAlgorithm: AES256

### Assessment

**PASS**

Default server-side encryption using SSE-S3 was enabled for the bucket.

---

## GRC Engineering Workflow

The exercise demonstrates the following approach:

    Control Requirement
            ↓
       AWS Service
            ↓
    Technical Configuration
            ↓
       AWS CLI / API
            ↓
    Machine-readable Evidence
            ↓
       Control Assessment

Future iterations of this portfolio will automate the evidence collection and assessment process rather than evaluating the CLI output manually.
