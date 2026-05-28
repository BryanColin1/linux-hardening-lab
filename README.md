# Linux Hardening Lab

## Overview

This project demonstrates basic Linux system hardening in a controlled lab environment. The objective is to review an Ubuntu Linux VM baseline, identify common security improvement areas, apply basic hardening steps, and document before-and-after verification.

## Lab Environment

| Component | Description |
|---|---|
| Target System | Ubuntu 22.04.5 LTS VM |
| Platform | Oracle VirtualBox |
| Network | Local lab environment |
| Additional Context | VM also hosts Wazuh services from a previous SOC lab |
| Documentation | Markdown and GitHub |

## Objectives

- Perform a basic Linux security baseline review
- Review users, sudo access, services, open ports, firewall status, and update status
- Apply practical Linux hardening steps
- Document evidence with screenshots
- Create a post-hardening verification review
- Build a reusable Linux hardening checklist

## Project Structure

```text
linux-hardening-lab/
├── baseline-audit/
│   └── initial-security-review.md
├── hardening-steps/
│   ├── firewall-hardening.md
│   ├── service-hardening.md
│   ├── ssh-hardening.md
│   ├── update-and-patch-management.md
│   └── user-account-hardening.md
├── notes/
│   └── lab-scope.md
├── remediation/
│   └── linux-hardening-checklist.md
├── screenshots/
├── verification/
│   └── post-hardening-review.md
└── README.md
```

## Hardening Areas Reviewed

| Area | Description |
|---|---|
| [Initial Security Review](baseline-audit/initial-security-review.md) | Documents the system baseline before hardening |
| [Update and Patch Management](hardening-steps/update-and-patch-management.md) | Reviews package update status and applies updates where possible |
| [Firewall Hardening](hardening-steps/firewall-hardening.md) | Reviews and configures UFW firewall posture |
| [User Account and Sudo Review](hardening-steps/user-account-hardening.md) | Reviews administrative access and sudo privileges |
| [SSH Hardening Review](hardening-steps/ssh-hardening.md) | Confirms SSH exposure and provides secure SSH recommendations |
| [Service Hardening Review](hardening-steps/service-hardening.md) | Reviews running services and listening ports |
| [Post-Hardening Review](verification/post-hardening-review.md) | Verifies system posture after hardening review |
| [Linux Hardening Checklist](remediation/linux-hardening-checklist.md) | Summarizes recommended Linux hardening controls |

## Key Findings and Actions

| ID | Area | Summary |
|---|---|---|
| LH-001 | Sudo Privileges | User `b` has full sudo privileges and should remain limited to trusted administrative use |
| LH-002 | Package Updates | Pending updates were reviewed and most updates were applied |
| LH-003 | Firewall | UFW was reviewed and configured to support required services |
| LH-004 | SSH | SSH was not installed or running, reducing remote access exposure |
| LH-005 | Services | Running services and listening ports were reviewed, including expected Wazuh services |

## Skills Demonstrated

- Linux security baseline review
- Patch management
- UFW firewall review
- User and sudo privilege review
- SSH exposure review
- Running service and open port analysis
- Post-hardening verification
- Security documentation
- Remediation checklist creation

## Disclaimer

This project was performed in a controlled local lab environment for educational and defensive security purposes only. No production systems, third-party systems, or unauthorized targets were tested.
