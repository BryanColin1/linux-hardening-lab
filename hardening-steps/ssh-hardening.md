# SSH Hardening Review

## Objective

Review SSH availability and document secure SSH configuration recommendations for the Ubuntu VM.

## Commands Used

```bash
systemctl status ssh
ss -tulnp | grep :22
```

## Security Rationale

SSH is commonly used for remote administration. If exposed or misconfigured, it can become a target for brute-force attacks, credential attacks, or unauthorized remote access.

## Findings

| Check | Result |
|---|---|
| SSH service status | SSH service could not be found |
| SSH listening on port 22 | No active SSH listener identified |
| Remote SSH exposure | No SSH exposure observed |
| Hardening action required | No immediate SSH hardening required unless SSH is installed later |

## Recommended Hardening If SSH Is Installed Later
- Disable direct root SSH login.
- Use SSH keys instead of password authentication where possible.
- Restrict SSH access using firewall rules.
- Allow SSH only from trusted IP addresses.
- Disable SSH if remote administration is not required.
- Monitor SSH login attempts through system logs or SIEM alerts.

## Evidence

Screenshot to be added. 

## Conclusion

SSH was not installed or running on the Ubuntu VM during review. This reduces remote access exposure. If SSH is installed in the future, it should be hardened before being enabled.
