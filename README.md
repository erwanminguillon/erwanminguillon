# Erwan Minguillon

![GitHub](https://img.shields.io/badge/GitHub-erwanminguillon-181717?style=flat&logo=githubithub.com/erwanminguillon)

Greetings from the cloud!

I am a cybersecurity and cloud security student building projects around Azure, SOC workflows, and secure application design.

I like systems that are not just “working on my machine”, but actually explainable, deployable, recoverable, and reasonably hard to break.

> I like projects that survive contact with reality:
>
> - users click weird things,
> - secrets leak if you let them,
> - databases sleep when you need them,
> - deployments fail at the least poetic moment,
> - documentation that may or may not make sense after 2 months.

I am especially interested in the boring-but-critical parts of security engineering: access control, logging, deployment safety, recovery, and knowing exactly where secrets are not supposed to be. Although, nothing is boring when it comes to cloud technologies hehe.

## Flagship project: Secure Serverless Incident Portal

My main project right now is **Secure Serverless Incident Portal** (or **SSIP**).

SSIP is a cloud-native incident reporting and SOC triage platform built on Azure.

It started as a simple idea:

```text
What would a small but realistic security incident portal look like if I had to design, deploy, secure, and document it properly?
```

Eventually, it turned into a full-stack Azure project with:

- public incident submission,
- public incident tracking,
- hashed tracking tokens,
- an admin dashboard,
- secure admin sessions,
- Azure SQL storage,
- CI/CD deployment,
- infrastructure restore scripts,
- and documentation for secrets, recovery, and security decisions.

Repository:

```text
https://github.com/erwanminguillon/secure-serverless-incident-portal
```

### What SSIP does

A public user can submit a security incident and receives:

```text
public incident ID
tracking token
```

The tracking token is only shown once and is stored as a hash.

An admin user can sign in to a protected SOC-style console to:

- triage incidents,
- update status and severity,
- assign reviewers,
- add internal comments,
- review incident details,
- and manage the case lifecycle.

The admin flow does not store the admin key in the browser. Instead, the backend validates the key and issues an HttpOnly session cookie.

### Why I built it this way

I wanted SSIP to show more than frontend polish.

The project includes the parts that usually decide whether an application is actually operational:

```text
Can it be deployed?
Can it be restored?
Can another person understand it?
Are secrets handled correctly?
Does the backend enforce access control?
Can the database structure be recreated?
Can the cloud resources be rebuilt?
```

That is why SSIP includes Bicep templates, SQL schema scripts, GitHub Actions workflows, restore documentation, and a secrets recovery checklist.

It is not perfect, but it is intentionally built like a real system instead of a throwaway demo.

## Technical stack

```text
Frontend: React, TypeScript, Vite
Backend: Azure Functions, Node.js, TypeScript
Database: Azure SQL, T-SQL schema, indexes, reference data
Cloud: Azure App Service, Azure Functions, Storage, Application Insights
Infrastructure: Bicep, Azure CLI, restore scripts
CI/CD: GitHub Actions, Azure OIDC, ZIP deployment packages
Security: HttpOnly sessions, hashed tokens, CORS controls, OWASP review, secret recovery docs
```

## Other projects

### Azure Secure Lab

A cloud security lab focused on Azure resource exposure, trust boundaries, monitoring, and practical security decisions.

```text
https://github.com/erwanminguillon/azure-secure-lab-rg
```

### Doc-K-Leaner

An experiment around vulnerability scanner orchestration and UI-driven security tooling.

```text
https://github.com/iddqdld/doc-k-leaner
```

## How I approach projects

I try to build projects that answer both sides of the equation.

The first side is obvious:

```text
Does it work?
```

The second side is where things get interesting:

```text
How does it fail?
Where are the secrets?
Who is allowed to do what?
What happens after a redeploy?
Can the infrastructure be recreated?
Can someone else operate it without guessing?
```

That second list is where I learn the most.

## Current learning direction

I am currently improving in:

- SOC workflows
- Azure security
- secure web application design
- incident response tooling
- cloud-native deployment
- authentication and session security
- detection and monitoring concepts
- infrastructure automation

## Cybersecurity involvement

I am involved in cybersecurity learning and student security communities, including the ECE cybersecurity ecosystem and 0xECE.

My goal is to build a portfolio that shows practical security engineering: not just knowing the theory, but applying it to systems that actually run.

## Links

GitHub:

```text
https://github.com/erwanminguillon
```

LinkedIn:

```text
https://www.linkedin.com/in/erwan-minguillon
```

## Start here

And hey if you're here, you might as well take a look at SSIP:

```text
https://github.com/erwanminguillon/secure-serverless-incident-portal
```
