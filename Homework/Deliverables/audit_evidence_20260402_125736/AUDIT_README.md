
# Lab 3B — APPI Compliance Audit Evidence Package
Generated: 2026-04-02T17:57:56.159892Z

## Evidence Included

### 1. Data Residency Proof
- File: data_residency_proof.json
- Purpose: Prove PHI resides ONLY in Tokyo (ap-northeast-1)
- Command: python3 malgus_data_residency_enhanced.py

### 2. Network Corridor Proof
- File: network_corridor_proof.json  
- Purpose: Prove controlled routing via Transit Gateway
- Command: python3 malgus_network_corridor_proof.py

### 3. Change Trail Evidence
- Included in: audit_evidence_package.json (change_trail section)
- Purpose: CloudTrail events showing who changed what
- Retention: 90 days in CloudTrail, 7 years in S3

### 4. Edge Security Proof
- Included in: audit_evidence_package.json (edge_security section)
- Purpose: CloudFront + WAF protecting application endpoints
- WAF Rules: Rate limiting, AWS Managed Rules

### 5. Flow Log Summary
- Included in: audit_evidence_package.json (flow_logs section)
- Purpose: Network traffic monitoring for audit trail

## Compliance Status
 COMPLIANT WITH APPI REQUIREMENTS

## What Auditors Want to See

 Data Residency: RDS in Tokyo only, no cross-region replication
 Access Trail: CloudTrail logs all API calls
 Change Trail: CloudTrail + S3 with 7-year retention
 Network Corridor: TGW-only routing, no VPC peering
 Edge Security: CloudFront + WAF blocking malicious traffic
 Retention: S3 versioning enabled, lifecycle policies in place

## Log Storage Locations
- CloudTrail: s3://chrisbarm-cloudtrail-logs-[account-id]/
- CloudFront: s3://chrisbarm-cloudfront-logs-[account-id]/
- WAF: CloudWatch Logs aws-waf-logs-liberdade
- Flow Logs: s3://chrisbarm-flowlogs-[account-id]/

## Key Files in This Package
1. audit_evidence_package.json - Main evidence bundle
2. data_residency_proof.json - PHI location proof
3. network_corridor_proof.json - TGW routing proof
4. README.md - This file
