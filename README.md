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

## 🧠 Methodology

This security assessment was conducted using a **structured, standards-aligned, and consultative approach**, designed to ensure thoroughness, clarity, and relevance to the client’s unique environment and objectives.

The workflow followed five interconnected stages:

1. **Information Gathering**  
   A series of stakeholder interviews and working sessions were conducted to understand the application’s architecture, deployment model, security concerns, and business context. This ensured the assessment was informed by real-world use cases and operational constraints.

2. **Scope Definition**  
   Based on the gathered context, the audit scope was explicitly defined to focus on high-priority cloud security domains relevant to the current development phase. This phase also included formal documentation of assumptions, access levels, and compliance drivers (e.g., PCI-DSS, PII handling).

3. **Security Assessment Activities**  
   The assessment itself was split into two main components:
   - **AWS Infrastructure Evaluation**: Configuration review, policy analysis, and security posture validation of services like IAM, RDS, S3, Cognito, Lambda, and Amplify.
   - **Application Code Review**: Manual secure code review and SAST using SonarQube, with feedback shared on secrets management, dependency use, and secure API interactions.

4. **Controls & Standards Mapping**  
   Observations were cross-referenced with well-established security standards, including:
   - [OWASP ASVS](https://owasp.org/www-project-application-security-verification-standard/) for application-layer controls
   - [NIST CSF](https://www.nist.gov/cyberframework) for cloud governance and operational alignment
   - AWS Well-Architected Framework and cloud-native best practices for cloud service configurations

5. **Reporting & Recommendations**  
   The findings were consolidated into professional deliverables, including a technical report and an executive summary, designed to guide remediation and policy improvement efforts. Action items were prioritized based on risk and impact, with guidance on timelines and responsible roles.

This approach ensured the assessment was not only technically rigorous but also **aligned with business priorities**, **compliance goals**, and **real-world cloud operations**.


## 🗣️ Information Gathering

- Conducted stakeholder interviews to understand business context, architecture, and existing security considerations:
  - CEO of the consulting firm overseeing the project.
  - External Project Manager managing development timelines.
  - Development Team responsible for implementation.
  - Organization’s CIO managing AWS infrastructure access.

- Shared a preliminary **security metrics questionnaire** with the Development Team to establish a baseline for evaluation.

- Conducted an initial planning and update session with both the consultant firm’s leadership and the non-profit organization’s stakeholders to finalize scope, timeline, and access requirements.


## 🧭 Scope of the Assessment

This assessment was conducted as a **point-in-time security evaluation** of a cloud-hosted web application during its development phase. The objective was to identify risks across both the application and the AWS infrastructure layers, and provide actionable guidance aligned with best practices and compliance considerations.

### 🎯 Goals

- Identify misconfigurations and potential vulnerabilities in the AWS environment and backend codebase
- Evaluate the effectiveness of existing identity, data protection, and governance mechanisms
- Recommend preventive controls to improve security posture prior to production release
- Ensure alignment with relevant compliance requirements, including **PCI-DSS**, **PII protection standards**, and data residency
- Align assessment practices with recognized frameworks such as the [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/wellarchitected-framework.pdf), [NIST CSF](https://www.nist.gov/cyberframework), and [OWASP ASVS](https://owasp.org/www-project-application-security-verification-standard/)

### 🔍 Assessment Parameters

- The audit covered the **development**, **test**, and **staging** environments within AWS. No live production data was in scope at the time of review.
- Access was provided to the AWS account, backend codebase, and documentation, as well as supporting architecture diagrams and interviews with key stakeholders (CIO, Development Team, and Project Sponsor).
- AWS services assessed include IAM, Cognito, EC2, Lambda, RDS, S3, DynamoDB, AWS Amplify, CloudTrail, and others.
- The backend code (primarily in Python and TypeScript) was evaluated via manual review and static analysis using SonarQube.
- Secure development practices, secrets management, and dependency hygiene were reviewed as part of the application layer assessment.

### 🧪 Security Domains Covered

This audit addresses 6 of the 10 AWS-identified cloud security domains:

1. **Identity & Access Management**
2. **Data Protection**
3. **Infrastructure Security**
4. **Logging & Monitoring**
5. **Configuration Management**
6. **Governance & Compliance**

### 🚫 Exclusions / Out of Scope

Due to the defined engagement scope and timeline, the following domains were excluded from this phase of the assessment:

- Incident Response Planning & Readiness
- End-User Device Management
- Vulnerability Management (including third-party pentesting or active exploitation)
- Business Continuity & Disaster Recovery Planning
- Full assessment of third-party platforms (e.g., SAS Viya) due to limited access

These areas are recommended for review in a **future phase** before go-live to ensure full-spectrum cloud security maturity.



## 🔐 Security Assessment

### 🔍 Assessment Objectives

- Assess the security of the application’s AWS backend architecture at its current stage of development.
- Perform application security testing on code and development workflows.
- Identify misconfigurations or missing controls across key security domains.
- Recommend phased, actionable improvements mapped to AWS best practices and industry standards (e.g., NIST, OWASP ASVS).

### 🔑 Key Activities

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

Assessment activities and recommendations were mapped against industry standards to ensure alignment with recognized best practices.

| **Control Category**     | **Referenced Standard**                                                                                                                                                    | **Examples from Review**                                                                                                                     |
|--------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| **Authentication**       | [ASVS V2 – Authentication](https://github.com/OWASP/ASVS/blob/master/4.0/en/0x11-V2-Authentication.md)                                | Password policy audit, MFA enforcement for root accounts, Cognito configuration review                                                       |
| **Malicious Code**       | [ASVS V10 – Malicious Code](https://github.com/OWASP/ASVS/blob/master/4.0/en/0x18-V10-Malicious.md)                                   | SAST via SonarQube, secure dependency management, analysis of external APIs and libraries                                                    |
| **Architecture & Design**| [ASVS V1 – Architecture](https://github.com/OWASP/ASVS/blob/master/4.0/en/0x10-V1-Architecture.md)                                    | Review of cloud-native design choices, use of AWS Shared Responsibility Model, absence of layered DDoS defenses                             |
| **Data Protection**      | SOC 2 Principles, NIST SP 800-53, AWS Security Pillars                                                                               | Client-side encryption recommendation, VPC endpoints for DynamoDB & S3, encryption policy checks                                              |
| **Logging & Monitoring** | AWS CloudTrail, CIS AWS Benchmarks, [ASVS V7 – Error Handling and Logging](https://github.com/OWASP/ASVS/blob/master/4.0/en/0x15-V7-Error-Logging.md)   | Verified logging configuration on Lambda & CloudTrail, GuardDuty use, recommendations for log access control & retention policies            |
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
