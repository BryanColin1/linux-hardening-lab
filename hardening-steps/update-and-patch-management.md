# Update and Patch Management

## Objective

Apply available package updates to reduce exposure to known vulnerabilities and improve system stability.

## Baseline Finding

During the initial security review, package repositories were checked and 13 packages were identified as upgradable.

## Commands Used

```bash
sudo apt update
apt list --upgradable
sudo apt upgrade -y
```

## Security Rationale

Keeping packages updated is one of the most important Linux hardening practices. Outdated packages may contain known vulnerabilities, bugs, or insecure behavior that can be corrected through security and system updates.

## Actions Taken

## Actions Taken

| Step | Action | Status |
|---|---|---|
| 1 | Checked package repositories | Completed |
| 2 | Reviewed upgradable packages | Completed |
| 3 | Applied available updates using `sudo apt upgrade -y` | Completed |
| 4 | Ran `sudo apt full-upgrade -y` for remaining packages | Completed |
| 5 | Reviewed remaining Netplan-related packages | Completed |
| 6 | Verified upgrade status | Completed with remaining packages noted |

## Verification

After applying updates, the number of available upgrades was reduced from 13 packages to 4 remaining Netplan-related packages.

Remaining packages observed:

```text
libnetplan0
netplan-generator
netplan.io
python3-netplan
```

## Evidence

```md
## Evidence

![Update and Patch Management](../screenshots/update-and-patch-management.png)
```

## Conclusion

Applying package updates reduces the risk of known vulnerabilities and improves the system’s baseline security posture.
