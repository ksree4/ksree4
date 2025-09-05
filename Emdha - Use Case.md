<p style="color:#0067cd; font-weight:700; font-size:22px">Table of Contents </p>

[TOC]

---

<div style="page-break-after: always;"></div>

# 1. Emdha, KSA - Overview

Emdha, based in the Kingdom of Saudi Arabia, has established itself as a reliable pillar of the nation’s digital trust landscape, delivering secure, compliant, and resilient digital signature solutions.

As a licensed Trust Service Provider, Emdha delivers a suite of services including digital signatures, certificates, and time-stamping. These solutions empower government institutions, enterprises, and individuals to sign documents electronically through a robust PKI-enabled infrastructure. The platform further enhances security with multi-layered KYC verification and a dedicated User Account Vault (UAV) for safeguarding identity data.

On the cybersecurity front, Emdha demonstrates strong maturity by aligning with international standards, employing advanced encryption protocols, and maintaining continuous system monitoring to ensure reliability and data protection.


## 1.1. Cybersecurity & Infrastructure Capabilities

- **Security & Standards:** Emdha aligns with globally recognized standards, including ISO 20000-1:2018 (IT service management), ISO 22301:2019 (business continuity), ISO 27001:2013 (information security), and ISO 27701:2019 (privacy). The company also undergoes annual WebTrust audits to ensure ongoing compliance and trustworthiness.
- **High Availability & Resilience:** Core systems are continuously monitored to maintain high availability and optimal performance, underscoring Emdha’s commitment to reliability and operational continuity.
- **Infrastructure & Workflow:** The platform delivers cloud-based, paperless digital signing processes, supporting device-agnostic access and RESTful API integrations. The User Account Vault (UAV) enables secure enrollment, authentication, and identity management for individuals, enterprises, and legal entities.
- **Multi-Environment Architecture:** Emdha operates across three environments — IT, Development, and Production — each supported by multiple servers and workstations running Microsoft operating systems.
- **User Directories:** Although users may access all environments, each environment operates its own independent directory service. Consequently, every user is provisioned with a unique set of credentials for each directory, ensuring logical separation and security. By default, users authenticate with passwords supported by the underlying operating systems.


## 1.2. Requirement for Secure Authentication to On-Prem Resources

Emdha has insisted the following requirements for the secure authentication within their critical infrastructures.

1. **Secure Access to On-Premises Systems:** 
The critical infrastructure includes multiple on-premises Windows servers and workstations. Users must authenticate securely to access these systems, which operate independently and are not connected to any cloud identity provider.

2. **Strong Authentication Methods**
Emdha intends to adopt biometric FIDO2 security keys as the primary method for secure authentication to servers and workstations.
   - **Biometric FIDO2 Security Keys** – Hardware-based, phishing-resistant authentication devices that provide strong, passwordless login.
   - **Temporary Access Passcode (TAP)** – A fallback mechanism that grants limited-time or limited-attempt access, designed for scenarios where a user’s registered FIDO2 security key is unavailable. 
   
   In addition, some users may utilize a mobile authenticator application for flexible access. The following authentication processes are required:
   - **Self-Registration and Authentication with Mobile Authenticator** – Users register themselves using the mobile app and authenticate with the app, including QR code scanning.
   - **TOTP Login** – Time-based one-time passcodes generated through Mobile Authenticator apps.

3. **Remote Authentication**
Remote users connect to on-premises servers through the RDP protocol. These RDP endpoints must support FIDO2 authentication including mobile authenticator, ensuring that remote sessions are secured with strong cryptographic login mechanisms.

4. **Secure IAM Platform**
A dedicated Identity and Access Management (IAM) platform will have to be deployed in each environment (IT, Development, and Production). The IAM platform should:
   - Integrate seamlessly with the respective user directories.
   - Provide centralized identity governance and access management.
   - Enforce strong authentication policies consistently across environments.

5. **One-Time Registration Across Environments**
Biometric FIDO2 security keys should follow a “register once, use everywhere” principle. Once a key is registered in any one environment (IT, Development, or Production), it should enable authentication across all environments. This ensures:
   - A consistent user experience.
   - Reduced administrative overhead.
   - Portability of secure credentials across systems.
	
These requirements establish the foundation for a zero-trust, passwordless authentication model, ensuring that Emdha’s critical infrastructure is protected with cryptographic, phishing-resistant, and user-friendly access controls.


---

<div style="page-break-after: always;"></div>

# 2. Ensurity Solution

Ensurity Solutions is a pioneer in delivering passwordless, cryptographic, and phishing-resistant authentication solutions that address the challenges of securing critical enterprise infrastructure. In environments where organizations manage multiple on-premises servers and workstations, Ensurity enables secure access without reliance on cloud identity providers. XSense integrates seamlessly with existing on-prem user directories, enabling secure login to Windows systems with strong authentication.

With support for Biometric FIDO2 Security Keys and optional mobile authenticator apps, XSense provides flexible and scalable authentication options that align with enterprise security and usability needs. The platform ensures one-time registration of FIDO2 credentials, allowing users to authenticate consistently across all environments, regardless of where the credential was enrolled.

By combining standards-based cryptography, centralized policy enforcement, and adaptive access controls, XSense not only strengthens security but also reduces administrative complexity and operational overhead. It delivers a resilient identity foundation that supports compliance, business continuity, and long-term digital transformation goals.

## 2.1. Solution Modules

At the center of this approach is XSense, Ensurity’s software-based Identity and Access Management (IAM) platform, designed to deliver unified, secure, and passwordless authentication across the enterprise. The solution is composed of the following modules:

1. **Software IAM Platform (XSense)** The central layer that manages authentication, authorization, and access control across all environments. XSense ensures centralized policy enforcement, secure credential management, and seamless integration with enterprise infrastructure.

   **Key Capabilities:**
   - **Flexible Deployment:** Can be deployed in both on-premises setups and air-gapped infrastructures, making it suitable for high-security environments.
   - **Passwordless MFA for Windows Systems:** Provides secure, passwordless multi-factor authentication for on-prem Windows devices (workstations, servers, and RDP systems) through the XSense Credential Provider Plugin (CPP).
   - **Application Integration:** Provides SAML and OIDC interfaces to integrate a wide range of enterprise and third-party applications.
   - **Lifecycle Management for FIDO2 Keys:** Integrates with the Asset Management System (AMS) to oversee the complete lifecycle of Ensurity’s Biometric FIDO2 Security Keys—from issuance to revocation. The AMS module provides centralized lifecycle management of security keys within the IAM framework.
     - Tracks issuance, assignment, and usage of FIDO2 keys.
     - Supports revocation or reassignment when employees change roles or leave the organization.

2. **Passwordless MFA for Windows Systems:** The XSense Credential Provider Plugin (CPP) is installed on Windows servers, workstations, and RDP systems to replace the default login interface.
   - Enables passwordless multi-factor authentication (MFA) for all on-prem Windows systems.
   - Provides strong cryptographic authentication using FIDO2 standards.
   - Ensures compliance with zero-trust access requirements by securing critical infrastructure endpoints.

3. **Passwordless MFA for RDP systems:** The XSense CPP is installed on RDP systems across all environments to enable secure, passwordless multi-factor authentication. In addition, Ensurity has provided a software utility, RDP Connect, which allows users to seamlessly switch between environments and conveniently select the desired RDP system for secure access.

4. **Corporate-edition of ThinC-AUTH Biometric FIDO2 Security Keys:** A critical hardware component of the solution, these biometric-enabled FIDO2 keys are user-attributable, and form the foundation of strong, phishing-resistant authentication.
	- **Biometric Support:** Provides an additional layer of identity assurance through fingerprint verification.
	- **Lifecycle Managed via AMS:** Fully supported within the XSense AMS module, enabling secure provisioning, usage tracking, and revocation.
	- **Portability:** Users carry their ThinC-AUTH key across environments (IT, Dev, Prod) for seamless and secure access.

Together, these modules establish a comprehensive, passwordless IAM solution that strengthens security, simplifies user experience, and reduces the risks associated with password-based authentication.


## 2.2. Deployment

Ensurity has implemented the complete solution at Emdha’s data centers in alignment with the organization’s critical security requirements. Additionally, a dedicated test lab was provisioned in Emdha’s User Acceptance Testing (UAT) environment to validate functionality before deploying into live operations.

- **UAT Environment for Testing:** The full solution was deployed in Emdha’s UAT environment, which is isolated from production systems. This setup allows validation of new features, configuration changes, and server patch updates prior to rollout across the IT, Development, and Production environments.
- **Operations Environment for real-time Use:** After successful UAT verification, the XSense IAM Platform was deployed across all operational environments — IT, Development, and Production — for real-time secure access.
- **Passwordless MFA for On-Prem Windows systems:** The XSense Credential Provider Plugin (CPP) was installed on all required Windows servers and workstations. By replacing the default Windows login interface, CPP enables passwordless multi-factor authentication for secure access. Users successfully logged into their workstations using the assigned Biometric Security Key integrated with XSense CPP.
  - For the convenience of Remote Users, XSense platform can be configured to support offline authentication using the FIDO2 Security Key. 
- **Authentication Options:** In addition to FIDO2-based authentication, enterprise login scenarios were validated with and without passwords, where credentials are cross-verified with Active Directory.
- **MFA for RDP systems:** With the **RDP Connect** Tool, users can seamlessly switch between environments and select the desired RDP system for secure, passwordless multi-factor authentication.
- **One-Time Registration Across Environments:** 
  - Through the XSense AMS module, each user is issued a Biometric FIDO2 Security Key in a selected environment. The user then enrolls the required fingerprints using the AUTH Manager Tool.
  - Once enrolled, the AUTH Manager Tool can also be connected to other environments to perform additional functions, such as profile registration or unlocking the device after multiple unsuccessful fingerprint attempts etc...
  - After fingerprint enrollment, the same Security Key is securely registered in the other two environments via a web-based registration process within the XSense Portal, ensuring portability and consistent authentication across IT, Development, and Production environments.



---

