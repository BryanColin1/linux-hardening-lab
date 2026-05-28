# Linux Hardening Checklist

## Overview

This checklist summarizes the Linux hardening actions reviewed during the lab.

## Patch Management

| Control | Recommendation | Status |
|---|---|---|
| Package updates | Run `sudo apt update` regularly | Reviewed |
| Package upgrades | Apply available security and system updates | Reviewed |
| Remaining packages | Review packages that remain pending after upgrade | Reviewed |

## Firewall

| Control | Recommendation | Status |
|---|---|---|
| UFW status | Enable UFW if inactive | Completed |
| Default inbound policy | Deny incoming traffic by default | Completed |
| Default outbound policy | Allow outgoing traffic unless stricter controls are required | Completed |
| Required ports | Allow only required services such as Wazuh ports | Reviewed |
| Rule review | Review firewall rules regularly | Recommended |

## User and Privilege Management

| Control | Recommendation | Status |
|---|---|---|
| Sudo users | Limit sudo access to trusted administrative users | Reviewed |
| Group membership | Review user group membership regularly | Reviewed |
| Unused accounts | Remove or disable unused accounts | Recommended |
| Privilege monitoring | Monitor sudo activity through logs or SIEM | Recommended |

## SSH Security

| Control | Recommendation | Status |
|---|---|---|
| SSH service | Keep SSH disabled if not required | Completed |
| Root login | Disable direct root login if SSH is installed later | Recommended |
| Authentication | Prefer SSH keys over password authentication | Recommended |
| Network restriction | Restrict SSH access to trusted IP addresses only | Recommended |

## Service Hardening

| Control | Recommendation | Status |
|---|---|---|
| Running services | Review running services regularly | Reviewed |
| Network-facing services | Confirm exposed ports are required | Reviewed |
| Wazuh services | Keep enabled because this VM is used as a Wazuh server | Reviewed |
| Unnecessary services | Disable only after confirming they are not required | Recommended |

## Logging and Monitoring

| Control | Recommendation | Status |
|---|---|---|
| System logs | Keep logging services enabled | Reviewed |
| Wazuh services | Keep Wazuh services enabled for monitoring | Reviewed |
| Authentication logs | Review login and sudo activity | Recommended |
| Firewall logs | Enable logging if firewall investigation is required | Recommended |

## Priority Actions

1. Keep the system updated.
2. Keep UFW enabled and review rules regularly.
3. Limit sudo access to trusted users.
4. Keep SSH disabled unless required.
5. Review running services and listening ports periodically.
6. Monitor authentication and privilege activity.

## Conclusion

This checklist provides a practical Linux hardening baseline for a controlled lab environment. The focus is on reducing attack surface, reviewing privilege access, applying updates, and maintaining visibility through logging and monitoring.
