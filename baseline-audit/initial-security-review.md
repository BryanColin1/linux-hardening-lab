# Initial Linux Security Review

## Objective

Perform a baseline security review of a Linux virtual machine before applying hardening steps.

## System Information

| Check | Command | Result |
|---|---|---|
| Hostname | `hostname` | `b-VirtualBox` |
| Kernel version | `uname -a` | `Linux b-VirtualBox 6.8.0-117-generic x86_64 GNU/Linux` |
| Operating system | `cat /etc/os-release` | `Ubuntu 22.04.5 LTS (Jammy Jellyfish)` |
| Current user | `whoami` | `b` |

## User and Privilege Review

| Check | Command | Notes |
|---|---|---|
| Current user | `whoami` | Current user is `b` |
| User ID and groups | `id` | User `b` belongs to several groups including `sudo`, `adm`, `plugdev`, `lpadmin`, and `sambashare` |
| Sudo privileges | `sudo -l` | User `b` can run all commands as root: `(ALL : ALL) ALL` |
| Local users | `cat /etc/passwd` | |

## Network and Service Review

| Check | Command | Notes |
|---|---|---|
| Open listening ports | `ss -tulnp` | Several local and network-facing ports were observed, including ports `53`, `443`, `1514`, `55000`, `9200`, and `9300` |
| Running services | `systemctl --type=service --state=running` | Multiple services were running, including system services, desktop services, logging services, and Wazuh-related services |
| Firewall status | `sudo ufw status verbose` | UFW firewall was active at the time of review |

## Update and Patch Review

| Check | Command | Notes |
|---|---|---|
| Package updates | `sudo apt update` | Package repositories were successfully checked |
| Upgrade status | `apt list --upgradable` | 13 packages were available for upgrade |

## Initial Observations

- The Ubuntu VM is running Ubuntu 22.04.5 LTS.
- The current user `b` has full sudo privileges.
- UFW firewall is already active.
- Several services are running and should be reviewed to confirm whether they are required.
- Several listening ports were observed, including ports commonly associated with Wazuh services.
- 13 packages were available for upgrade, meaning patching should be part of the hardening process.
- User and sudo access should be reviewed to ensure least privilege.
- Running services should be reviewed to reduce unnecessary attack surface.

## Baseline Findings

| ID | Finding | Severity | Recommendation |
|---|---|---|---|
| LH-001 | Full sudo privileges assigned to user `b` | Medium | Confirm this access is required and avoid unnecessary administrator privileges |
| LH-002 | Multiple listening services detected | Medium | Review each listening service and disable anything unnecessary |
| LH-003 | Pending package updates available | Medium | Apply available security and system updates |
| LH-004 | Several background services running | Low / Medium | Review running services and disable unused services |
| LH-005 | Firewall active but rules not yet reviewed | Low | Review UFW rules and confirm only required traffic is allowed |

## Planned Hardening Steps

1. Apply available package updates.
2. Review sudo privileges.
3. Review listening ports and running services.
4. Confirm UFW firewall rules.
5. Harden SSH configuration if SSH is installed or enabled.
6. Disable unnecessary services.
7. Verify the system after hardening.

## Evidence

![Initial Security Review](../screenshots/initial-security-review.png)

## Conclusion

This baseline review establishes the initial security posture of the Ubuntu VM before hardening changes are applied. The main areas for improvement are package updates, service review, privilege review, and firewall rule verification.
