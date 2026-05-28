# Service Hardening Review

## Objective

Review running services on the Ubuntu VM and document recommendations for reducing unnecessary background services.

## Baseline Finding

During the initial security review, multiple services were running on the Ubuntu VM. Some services are required for normal system operation, while others should be reviewed to confirm whether they are necessary.

## Commands Used

```bash
systemctl --type=service --state=running
ss -tulnp
```

## Security Rationale

Running services can increase attack surface, especially if they expose network ports or unnecessary functionality. Service hardening helps reduce risk by disabling services that are not required.

## Service Review Summary

| Area | Observation | Recommendation |
|---|---|---|
| Running services | 36 loaded running service units were observed | Review services regularly and keep only required services enabled |
| Wazuh services | `wazuh-dashboard`, `wazuh-indexer`, and `wazuh-manager` were running | Keep enabled because this VM is used as the Wazuh server |
| Logging services | `rsyslog` and `systemd-journald` were running | Keep enabled for logging and troubleshooting |
| Desktop services | `gdm` and desktop-related services were running | Keep enabled if using Ubuntu Desktop |
| Network-facing services | Ports `443`, `1514`, `1515`, `55000`, `9200`, and `9300` were observed | Confirm these are required for Wazuh and restrict access with firewall rules |
| Unnecessary services | No services were disabled during this review | Review periodically before disabling anything |

## Key Observations

- The Ubuntu VM is being used as a Wazuh server, so Wazuh-related services are expected.
- Several Wazuh-related ports were listening, including `443`, `1514`, `1515`, `55000`, `9200`, and `9300`.
- Logging and system services should remain enabled.
- Services should not be disabled unless their purpose is understood.
- Firewall rules should be used to restrict access to required Wazuh ports.

## Review Questions
| Question | Purpose |
|---|---|
| Is this service required for the system role? | Helps identify unnecessary services |
| Does this service expose a network port? | Helps identify attack surface |
| Is the service monitored or logged? | Helps support detection and troubleshooting |
| Can the service be safely disabled? | Prevents accidental system disruption |

## Recommended Hardening
- Review running services regularly.
- Disable unnecessary services.
- Keep logging and monitoring services enabled.
- Document services required for the system role.
- Review network-facing services with ss -tulnp.
- Avoid disabling services without understanding their purpose.

## Evidence

Screenshot to be added.

## Conclusion

The Ubuntu VM runs several services required for desktop operation, logging, and Wazuh functionality. Service review is important to reduce unnecessary attack surface while keeping required security and system services active.
