# AWS Web Application Security Assessment

## Overview

This repository documents a security assessment performed for a cloud-hosted application in its development phase. The project involved evaluating both the AWS backend infrastructure and the application codebase to provide actionable recommendations aligned with industry best practices.

This review was conducted in collaboration with stakeholders including the CIO of the organization, the Project Manager, the Tech Lead, and the Development Team. Findings and recommendations were mapped to standards such as the [OWASP Application Security Verification Standard (ASVS) v4.0](https://github.com/OWASP/ASVS) and relevant AWS security guidelines.

|⚠️ Note: Sensitive implementation details, diagrams, and policy documents have been redacted or omitted to maintain confidentiality. Only sanitized or illustrative examples are included.

## 🔍 Assessment Objectives

- Assess the security of the application’s AWS backend architecture at its current stage of development.
- Perform application security testing on code and development workflows.
- Identify misconfigurations or missing controls across key security domains.
- Recommend phased, actionable improvements mapped to AWS best practices and industry standards (e.g., NIST, OWASP ASVS).

## 🔑 Key Activities

The assessment was conducted in two broad phases:

**1. AWS Infrastructure & Architecture Evaluation**
  - Reviewed architecture deployed primarily with AWS Amplify, Cognito (User Pools), Lambda, DynamoDB, RDS, and API Gateway.
  - Evaluated Identity and Access Management practices, including IAM users, roles, access key usage, and password policies.
  - Reviewed existing network configurations (Security Groups, NACLs), use of VPC endpoints, and S3 bucket policies.
  - Assessed encryption policies (in-transit and at-rest) for data in S3, RDS, and DynamoDB.
  - Evaluated logging and monitoring coverage using AWS Config, CloudTrail, and GuardDuty.
  - Reviewed governance posture and provided a control checklist for services such as AWS WAF, Shield, Security Hub, and Trusted Advisor.
  - Provided high-priority, medium-priority, and phase-based action plans for implementing required policies and hardening controls.


**2. Application Code Review & Software Assurance**
- Reviewed the backend code written in Python, Node.js, and TypeScript, with APIs connecting to SAS Intelligent Decisioning and external third-party APIs.
- Manual code inspection and Static Application Security Testing (SAST) were performed using SonarQube.
- Reviewed third-party library and dependency usage for known vulnerabilities (e.g., via filename.txt in the CodeCommit repository).
- Provided the development team with secure coding feedback and recommendations tailored to the current development phase.
- Submitted a Preliminary Metrics Questionnaire to gather architectural, documentation, and code ownership insights.
