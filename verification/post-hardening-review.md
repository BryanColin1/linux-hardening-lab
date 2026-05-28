# Post-Hardening Review

## Objective

Verify the Ubuntu VM security posture after completing basic Linux hardening review steps.

## Verification Summary

| Area | Verification | Result |
|---|---|---|
| Updates | Package updates reviewed and applied where possible | Completed |
| Firewall | UFW reviewed and enabled with required rules | Completed |
| User privileges | Sudo privileges reviewed | Completed |
| SSH | SSH service reviewed and not found running | Completed |
| Services | Running services and listening ports reviewed | Completed |

## Commands Used

```bash
apt list --upgradable
sudo ufw status verbose
sudo ufw status numbered
getent group sudo
sudo -l
systemctl status ssh
ss -tulnp | grep :22
systemctl --type=service --state=running
ss -tulnp
```

## Key Improvements

- Package updates were reviewed and most available updates were applied.
- UFW firewall was reviewed and configured.
- Sudo privileges were documented for the administrative lab user.
- SSH was confirmed as not installed or not running.
- Running services and listening ports were reviewed.
- Wazuh-related services were identified as expected because the VM is used as a Wazuh server.

## Remaining Notes

- Some Netplan-related packages remained pending and were noted for further review.
- User `b` retains full sudo privileges because it is the primary administrative lab account.
- Wazuh services and ports remain active because this VM is also used as the Wazuh server.
- Service disabling was not performed because no unnecessary service was confirmed safe to disable during this review.

## Evidence

Screenshot to be added.

## Conclusion

The post-hardening review confirms that basic Linux security review and hardening steps were completed. The system now has documented update status, firewall posture, sudo access, SSH exposure, and running service review.
