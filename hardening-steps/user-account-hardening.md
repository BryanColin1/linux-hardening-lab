# User Account and Sudo Privilege Hardening

## Objective

Review local user accounts and sudo privileges to support least privilege on the Ubuntu VM.

## Baseline Finding

During the initial security review, user `b` was found to have full sudo privileges:

```text
(ALL : ALL) ALL
```

## Commands Used

```bash
whoami
id
sudo -l
getent group sudo
cat /etc/passwd
```

## Security Rationale

User and privilege review is important because excessive administrator access increases risk. If an account with sudo privileges is compromised, an attacker may gain full control of the system.

## Actions Taken

| Step | Action | Status |
|---|---|---|
| 1 | Reviewed current user context | Completed |
| 2 | Reviewed user group membership | Completed |
| 3 | Reviewed sudo privileges | Completed |
| 4 | Identified administrative user access | Completed |
| 5 | Documented least privilege recommendation | Completed |

## Findings

| Finding | Risk | Recommendation |
|---|---|---|
| User `b` has full sudo privileges | If compromised, the account can execute commands as root | Keep sudo access limited to trusted administrative users only |
| User `b` belongs to multiple groups | Additional group membership may increase access | Review group membership periodically |
| Local users exist on the system | Unused accounts may increase attack surface | Remove or disable accounts that are no longer needed |

## Evidence

![User Account Hardening](../screenshots/user-account-hardening.png)

## Conclusion

The Ubuntu VM uses user b as the primary administrative lab account. The account has full sudo privileges, which is acceptable for this controlled lab but should be reviewed and restricted in real environments based on least privilege.
