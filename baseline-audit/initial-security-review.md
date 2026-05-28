# Initial Linux Security Review

## Objective

Perform a baseline security review of a Linux virtual machine before applying hardening steps.

## System Information

| Check | Command | Result |
|---|---|---|
| Hostname | `hostname` | To be added |
| Kernel version | `uname -a` | To be added |
| Operating system | `cat /etc/os-release` | To be added |
| Current user | `whoami` | To be added |

## User and Privilege Review

| Check | Command | Notes |
|---|---|---|
| Current user | `whoami` | To be added |
| User ID and groups | `id` | To be added |
| Sudo privileges | `sudo -l` | To be added |
| Local users | `cat /etc/passwd` | Review only; do not upload sensitive details unnecessarily |

## Network and Service Review

| Check | Command | Notes |
|---|---|---|
| Open listening ports | `ss -tulnp` | To be added |
| Running services | `systemctl --type=service --state=running` | To be added |
| Firewall status | `sudo ufw status verbose` | To be added |

## Update and Patch Review

| Check | Command | Notes |
|---|---|---|
| Package updates | `sudo apt update` | To be added |
| Upgrade status | `apt list --upgradable` | To be added |

## Initial Observations

- To be added after running baseline commands.
- Identify open ports, unnecessary services, weak configurations, or missing controls.

## Planned Hardening Steps

1. Apply system updates.
2. Review sudo privileges.
3. Enable and configure firewall rules.
4. Harden SSH configuration if SSH is installed.
5. Disable unnecessary services.
6. Verify changes after hardening.

## Evidence

Screenshot to be added.

## Conclusion

This baseline review establishes the initial security posture of the Linux VM before hardening changes are applied.
