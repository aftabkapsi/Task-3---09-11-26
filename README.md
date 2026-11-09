# Task-3 09-11-26

# Task 3 – Basic Vulnerability Scan

## Overview
This task involved running a basic vulnerability scan on an authorized lab machine using Greenbone OpenVAS. The aim was to complete the scan, review the generated report, and understand the finding reported by the scanner.

## Tools and Environment
- Greenbone OpenVAS / Greenbone Security Assistant (GSA)
- Kali Linux
- Docker-based lab environment

## Steps Performed
1. Opened the Greenbone Security Assistant web interface.
2. Added the authorized lab machine as a scan target.
3. Created a scan task and selected an available scan configuration.
4. Started the scan and waited until its status changed to **Done**.
5. Opened the generated report and reviewed the severity summary.
6. Opened the reported finding to read its details and recommended mitigation.

## Scan Result

| Item | Result |
|---|---|
| Scan status | Completed |
| Finding | TCP timestamps |
| Severity | Low |
| CVSS score | 2.6 |
| Quality of Detection (QoD) | 80% |
| Additional results | 4 Log results |

No High- or Medium-severity findings were shown in the report summary.

## Finding: TCP Timestamps

The scan detected that the host responds with TCP timestamp information. In some situations, this information may help estimate how long a system has been running.

The scanner classified this as a **Low-severity** information disclosure issue. This finding alone does not indicate that the system has been compromised.

## Recommended Mitigation

If TCP timestamps are not required, the system administrator can consider disabling them after checking that the change will not affect normal network operations.

The scan report suggests the following options:

- **Linux:** Set `net.ipv4.tcp_timestamps = 0` in the system configuration and apply the setting.
- **Windows:** Use the `netsh` command option documented in the scan report to disable global TCP timestamps.

Only make configuration changes with proper authorization. Run another scan afterward to check whether the finding has been resolved.

## Evidence

Add the screenshots captured during the task to the repository. They should show:

- The completed scan overview.
- The report results.
- The TCP timestamps finding and its suggested mitigation.

Host and network details have been kept private in the report and evidence.

## Conclusion

The task provided practical experience in configuring and running a vulnerability scan and reviewing its results. The scan completed successfully and reported one Low-severity TCP timestamps finding. The recommended mitigation was documented for review.

---

**Note:** Perform vulnerability scans only on systems you own or have explicit permission to assess.
