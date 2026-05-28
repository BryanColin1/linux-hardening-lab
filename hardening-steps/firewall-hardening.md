# Firewall Hardening

## Objective

Review the Ubuntu VM firewall status and document basic firewall hardening practices using UFW.

## Baseline Finding

During the firewall review, UFW was found to be inactive. This means host-based firewall filtering was not enabled at the time of review.

## Commands Used

```bash
sudo ufw status verbose
sudo ufw status numbered
```

## Security Rationale

A host-based firewall helps reduce attack surface by limiting inbound traffic to only approved services. Even when a system is in a lab environment, reviewing firewall rules is a useful hardening practice.

## Actions Taken

| Step | Action | Status |
|---|---|---|
| 1 | Checked UFW status | Completed |
| 2 | Identified UFW was inactive | Completed |
| 3 | Added required firewall allowances for Wazuh services | Completed |
| 4 | Enabled UFW | Completed |
| 5 | Verified firewall status and numbered rules | Completed |


## Recommended Firewall Baseline

| Control | Recommendation |
|---|---|
| Default inbound policy | Deny incoming traffic unless required |
| Default outbound policy | Allow outgoing traffic unless stricter controls are needed |
| Management access | Restrict SSH to trusted networks if SSH is enabled |
| Unused services | Do not allow ports for unnecessary services |
| Rule review | Review UFW rules regularly |

## Evidence

Screenshot to be added.

## Conclusion

Firewall rule review helps confirm that the system is not unnecessarily exposed to inbound network traffic.
