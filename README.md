# AWS Web Application Security Assessment

This repository documents a security assessment performed for a cloud-hosted application in its development phase. The objective was to identify potential security gaps in the application and cloud infrastructure, and provide actionable, standards-based recommendations to improve the security posture before production deployment.

## 🧠 Context

The web application, commissioned by a non-profit organization, was still under active development at the time of assessment. The consulting firm responsible for the application’s delivery engaged me to perform an independent security evaluation. The scope included assessing the application codebase and the AWS-hosted infrastructure to ensure alignment with industry best practices.

This review was conducted in collaboration with stakeholders including the CIO of the organization, the CEO of the consulting firm, the Project Manager, and the Development Team. Findings and recommendations were mapped to standards such as the [OWASP Application Security Verification Standard (ASVS) v4.0](https://github.com/OWASP/ASVS) and relevant AWS security guidelines.

|⚠️ Note: Sensitive implementation details, diagrams, and policy documents have been redacted or omitted to maintain confidentiality. Only sanitized or illustrative examples are included.

## 🔍 Methodology

The assessment followed a structured, standards-aligned process.

### 🗣️ Information Gathering

- Conducted stakeholder interviews to understand business context, architecture, and existing security considerations:
  - CEO of the consulting firm overseeing the project.
  - External Project Manager managing development timelines.
  - Development Team responsible for implementation.
  - Organization’s CIO managing AWS infrastructure access.

- Shared a preliminary **security metrics questionnaire** with the Development Team to establish a baseline for evaluation.

- Conducted an initial planning and update session with both the consultant firm’s leadership and the non-profit organization’s stakeholders to finalize scope, timeline, and access requirements.

### 🔐 Security Assessment

#### 🔍 Assessment Objectives

- Assess the security of the application’s AWS backend architecture at its current stage of development.
- Perform application security testing on code and development workflows.
- Identify misconfigurations or missing controls across key security domains.
- Recommend phased, actionable improvements mapped to AWS best practices and industry standards (e.g., NIST, OWASP ASVS).

#### 🔑 Key Activities

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
