# AWS Web Application Security Assessment

This repository documents a security assessment performed for a cloud-hosted application in its development phase. The objective was to identify potential security gaps in the application and cloud infrastructure, and provide actionable, standards-based recommendations to improve the security posture before production deployment.

## 📁 Repository Contents
| File                                     | Description                                                      |
| ---------------------------------------- | ---------------------------------------------------------------- |
| `README.md`                              | Project overview, methodology, and activity summary              |
| `security-audit-report.pdf` *(Redacted)* | Final structured security audit report (SANS-style template)     |
| `questionnaire-aws-preassessment.pdf`    | Questionnaire used to gather context about AWS environment       |
| `task-prioritization.xlsx` *(Redacted)*  | Suggested task list, timeline, and owner mapping for remediation |
| `architecture-diagram.png` *(Mock)*      | Sample AWS architecture diagram representing components assessed |

|🔐 Actual findings and sensitive artifacts have been redacted or generalized for confidentiality.

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

### 🧭 Scope of the Assessment

This security assessment focused on a structured evaluation of both the application layer and the AWS cloud infrastructure. Based on AWS’s recommended security domains, the following six areas were covered during the audit:

#### ✅ AWS Security Domains Covered

1. **Identity & Access Management**
2. **Data Protection**
3. **Infrastructure Security**
4. **Logging & Monitoring**
5. **Configuration Management**
6. **Governance & Compliance**

> ⚠️ **Domains Excluded (Out of Scope):**  
> - Incident Response  
> - End-User Device Management  
> - Vulnerability Management  
> - Business Continuity & Disaster Recovery  

These excluded areas are recommended for assessment in a future audit phase prior to production launch.


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

## 📊Security Standards & Control Mapping

Findings and recommendations were mapped against industry standards to ensure alignment with recognized best practices.

| **Control Category**     | **Referenced Standard**                                                                                                                                                    | **Examples from Review**                                                                                                                     |
|--------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| **Authentication**       | [ASVS V2 – Authentication](https://github.com/OWASP/ASVS/blob/master/4.0/en/0x11-V2-Authentication.md)                                | Password policy audit, MFA enforcement for root accounts, Cognito configuration review                                                       |
| **Malicious Code**       | [ASVS V10 – Malicious Code](https://github.com/OWASP/ASVS/blob/master/4.0/en/0x18-V10-Malicious.md)                                   | SAST via SonarQube, secure dependency management, analysis of external APIs and libraries                                                    |
| **Architecture & Design**| [ASVS V1 – Architecture](https://github.com/OWASP/ASVS/blob/master/4.0/en/0x10-V1-Architecture.md)                                    | Review of cloud-native design choices, use of AWS Shared Responsibility Model, absence of layered DDoS defenses                             |
| **Data Protection**      | SOC 2 Principles, NIST SP 800-53, AWS Security Pillars                                                                               | Client-side encryption recommendation, VPC endpoints for DynamoDB & S3, encryption policy checks                                              |
| **Logging & Monitoring** | AWS CloudTrail, CIS AWS Benchmarks, [ASVS V10.4 – Logging](https://github.com/OWASP/ASVS/blob/master/4.0/en/0x18-V10-Malicious.md)   | Verified logging configuration on Lambda & CloudTrail, GuardDuty use, recommendations for log access control & retention policies            |
| **Governance & Compliance** | AWS Well-Architected Tool, AWS Artifact, CIS AWS Foundations Benchmark                                                           | Use of AWS Security Hub, recommendations for security documentation, policy tracking, and centralized compliance coverage                    |


## ✅ Deliverables

The following artifacts were created as part of this engagement:

    ✅ README.md (this document)

    📋 A sanitized version of the Final Report structured using a SANS-inspired layout

    🧩 A project-specific Preliminary Metrics Questionnaire

    🗂️ A risk tracking spreadsheet with priority-tagged controls and responsible parties

    [🔐 Visual network architecture diagram (Redacted – not publicly included)]

Notes

    This repository is intended for demonstration and documentation purposes. Sensitive assets, credentials, and production-specific configurations have been excluded.

    AWS resource names, IAM details, and architectural configurations have been anonymized or abstracted.

    All tools and references used are publicly available or authorized for educational/non-commercial use.
