# CyberOps Academy — Day 7: Identity & Access Management

![Phase](https://img.shields.io/badge/Phase-1%20Foundation-blue) ![Day](https://img.shields.io/badge/Day-7%20of%2030-orange) ![XP](https://img.shields.io/badge/XP-100-green) ![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

---

## Mission Overview

**Day 7** of the CyberOps Academy 30-Day Analyst Bootcamp focuses on **Identity & Access Management (IAM)** — the foundation of every secure system. Understanding who can access what, how they prove their identity, and how permissions are controlled is critical for any cybersecurity analyst.

| Field | Details |
|---|---|
| **Bootcamp** | CyberOps Academy — 30-Day Analyst Program |
| **Phase** | Phase 1: Foundation |
| **Day** | Day 7 |
| **Topic** | Identity & Access Management (IAM) |
| **XP Reward** | 100 XP |
| **Date Completed** | April 16, 2026 |
| **Status** | Completed |

---

## Topics Covered

- Authentication (AuthN)
- Authorization (AuthZ)
- Multi-Factor Authentication (MFA)
- Role-Based Access Control (RBAC)
- OAuth 2.0
- Zero Trust Architecture

---

## 1. Authentication vs Authorization

### Authentication (AuthN)
Authentication is the process of **verifying who you are**.

| Method | Description | Example |
|---|---|---|
| Password | Something you know | Username + Password |
| Biometric | Something you are | Fingerprint, Face ID |
| Token | Something you have | OTP, Smart Card |
| Certificate | Cryptographic proof | SSL/TLS Client Certs |

### Authorization (AuthZ)
Authorization is the process of **verifying what you can do** after authentication.

```
User logs in (AuthN) --> System checks permissions (AuthZ) --> Access granted/denied
```

**Key Principle:** Authentication always comes before Authorization.

---

## 2. Multi-Factor Authentication (MFA)

MFA requires **two or more** verification factors from different categories:

| Factor Type | Examples |
|---|---|
| Something You Know | Password, PIN, Security Questions |
| Something You Have | OTP App, Hardware Token, SMS Code |
| Something You Are | Fingerprint, Retina Scan, Face ID |
| Somewhere You Are | GPS Location, IP Geolocation |

### Why MFA Matters
- Passwords alone are compromised in 81% of data breaches
- MFA blocks 99.9% of automated attacks (Microsoft research)
- Mandatory in PCI DSS, HIPAA, ISO 27001 compliance

### Types of MFA
- **TOTP** (Time-based One-Time Password) — Google Authenticator, Authy
- **HOTP** (HMAC-based One-Time Password) — Counter-based tokens
- **Push Notifications** — Duo Security, Microsoft Authenticator
- **Hardware Keys** — YubiKey, FIDO2

---

## 3. Role-Based Access Control (RBAC)

RBAC assigns permissions to **roles**, not individual users. Users are then assigned to roles.

```
User --> Role --> Permissions --> Resources
```

### RBAC Example Structure

| Role | Permissions |
|---|---|
| Admin | Read, Write, Delete, Manage Users |
| Analyst | Read, Write Reports |
| Viewer | Read Only |
| Guest | Limited Read |

### Benefits of RBAC
- Principle of Least Privilege (PoLP) enforcement
- Easy to audit and manage
- Scalable for large organizations
- Reduces insider threat risk

### Access Control Models Comparison

| Model | Description | Use Case |
|---|---|---|
| DAC | Discretionary — Owner controls access | Personal files |
| MAC | Mandatory — System enforces labels | Military/Government |
| RBAC | Role-Based — Permissions via roles | Enterprise |
| ABAC | Attribute-Based — Context-aware rules | Cloud environments |

---

## 4. OAuth 2.0

OAuth 2.0 is an **authorization framework** that allows third-party applications to access user resources without exposing credentials.

### OAuth 2.0 Flow

```
1. User clicks "Login with Google"
2. App redirects to Google Authorization Server
3. User grants permission
4. Google sends Authorization Code to App
5. App exchanges code for Access Token
6. App uses Access Token to access user's Google data
```

### Key Components

| Component | Role |
|---|---|
| Resource Owner | The user who owns the data |
| Client | The application requesting access |
| Authorization Server | Issues tokens (e.g., Google Auth) |
| Resource Server | Hosts the protected data (e.g., Google API) |

### OAuth 2.0 Grant Types

| Grant Type | Use Case |
|---|---|
| Authorization Code | Web apps (most secure) |
| Implicit | Legacy SPAs (deprecated) |
| Client Credentials | Machine-to-machine |
| Resource Owner Password | Trusted first-party apps |

### OAuth 2.0 vs OpenID Connect
- **OAuth 2.0** → Authorization (access to resources)
- **OpenID Connect (OIDC)** → Authentication (identity verification) built on top of OAuth 2.0

---

## 5. Zero Trust Architecture

**Zero Trust** follows the principle: **"Never Trust, Always Verify"**

Traditional security assumed everything inside the network was trusted. Zero Trust eliminates this assumption.

### Core Principles

1. **Verify Explicitly** — Always authenticate and authorize based on all available data points
2. **Use Least Privileged Access** — Limit user access with Just-In-Time and Just-Enough-Access
3. **Assume Breach** — Minimize blast radius, segment access, verify end-to-end encryption

### Zero Trust vs Traditional Perimeter Security

| Aspect | Traditional | Zero Trust |
|---|---|---|
| Trust Model | Trust inside network | Never trust anyone |
| Access Control | Network-based | Identity-based |
| Verification | One-time at login | Continuous |
| Lateral Movement | Possible | Prevented by microsegmentation |

### Zero Trust Pillars

- **Identity** — Strong authentication, MFA, SSO
- **Devices** — Device compliance, health checks
- **Network** — Microsegmentation, encrypted traffic
- **Applications** — App-level access controls
- **Data** — Data classification, DLP

---

## 6. Key IAM Concepts Summary

| Concept | Definition |
|---|---|
| SSO (Single Sign-On) | One login grants access to multiple systems |
| PAM (Privileged Access Management) | Controls admin/root level accounts |
| IAM Policy | Rules defining who can access what |
| Principle of Least Privilege | Grant only minimum necessary access |
| Identity Federation | Linking identities across multiple systems |
| Directory Services | LDAP, Active Directory — central user management |
| JIT Access | Just-In-Time access — temporary elevated privileges |

---

## 7. Real-World IAM Attack Scenarios

| Attack | Description | Prevention |
|---|---|---|
| Credential Stuffing | Using leaked password lists | MFA, Rate limiting |
| Privilege Escalation | Gaining higher permissions than allowed | RBAC, PAM |
| Pass-the-Hash | Reusing hashed credentials | MFA, Privileged access management |
| Token Hijacking | Stealing OAuth/JWT tokens | Short token expiry, HTTPS |
| Insider Threat | Malicious internal user | Least privilege, audit logs |
| Account Takeover | Unauthorized access to an account | MFA, anomaly detection |

---

## 8. IAM Tools & Technologies

| Category | Tools |
|---|---|
| Identity Providers | Okta, Azure AD, AWS IAM, Google Workspace |
| MFA Solutions | Google Authenticator, Duo, YubiKey |
| PAM Solutions | CyberArk, BeyondTrust, Thycotic |
| SSO Platforms | Okta SSO, Ping Identity, Auth0 |
| Directory Services | Microsoft Active Directory, OpenLDAP |
| SIEM (IAM events) | Splunk, IBM QRadar, Microsoft Sentinel |

---

## 9. Compliance & Standards Related to IAM

| Standard/Regulation | IAM Requirement |
|---|---|
| ISO 27001 | Access control policy (A.9) |
| NIST CSF | Identify (ID), Protect (PR) functions |
| PCI DSS | MFA for privileged access, least privilege |
| HIPAA | Unique user identification, access controls |
| GDPR | Data access controls and audit trails |
| SOC 2 | Access management and monitoring controls |

---

## 10. Key Takeaways

- **Authentication** proves identity; **Authorization** controls access
- **MFA** is the single most effective control to prevent account compromise
- **RBAC** simplifies management and enforces least privilege at scale
- **OAuth 2.0** enables secure delegated access without sharing credentials
- **Zero Trust** is the modern security model — verify everything, trust nothing
- IAM is the backbone of cloud security (AWS IAM, Azure AD, GCP IAM)

---

## Progress Tracker

```
Phase 1 — Foundation (Days 1-8)
[x] Day 1 — Cybersecurity Fundamentals
[x] Day 2 — Networking Basics
[x] Day 3 — Operating System Security
[x] Day 4 — Threat Types & Attack Vectors
[x] Day 5 — Cryptography Essentials
[x] Day 6 — Security Frameworks & Standards
[x] Day 7 — Identity & Access Management  <-- YOU ARE HERE
[ ] Day 8 — Phase 1 Review & Knowledge Check
```

---

## Connect

- GitHub: [0407ganesh](https://github.com/0407ganesh)
- Bootcamp: CyberOps Academy — 30-Day Analyst Program

---

*Day 7 of 30 — CyberOps Academy Bootcamp | Identity & Access Management | April 16, 2026*
