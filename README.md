# IT Support Network Incident 01 — Incorrect IP Configuration

## Scenario
A Sales employee, Sara Kim, reported that she could not access company network resources from her Windows 10 workstation. She stated that the connection had been working earlier.

## Environment
- Windows 10 Client
- Windows Server / Active Directory environment
- DHCP
- DNS
- ServiceNow
- Lab domain: IsaacA.local

## Incident
**User:** Sara Kim  
**Department:** Sales  
**Category:** Network  
**Subcategory:** Connectivity  
**Incident State:** Resolved

### User Report
> "I can't access the company network from my computer. It was working earlier today."

## Troubleshooting Performed

1. Created a ServiceNow incident before beginning troubleshooting.
2. Checked the workstation's IP configuration using `ipconfig`.
3. Identified that the workstation was using manually configured static network settings.
4. Tested connectivity to the default gateway.
5. Tested DNS/server connectivity.
6. Tested hostname resolution using `nslookup`.
7. Initial connectivity and DNS tests failed.
8. Restored the workstation to automatic IP and DNS configuration.
9. Confirmed that DHCP provided the correct network configuration.
10. Retested gateway connectivity and DNS/name resolution.
11. Confirmed that company network resources were accessible.
12. User confirmed that network access was restored.

## Root Cause
The workstation had incorrect static IP, default gateway, and DNS configuration instead of obtaining the correct network settings automatically from DHCP.

## Resolution
Restored Client 10 to automatic IP and DNS configuration. DHCP provided the correct network settings, after which network connectivity and DNS resolution were successfully verified.

## Skills Practiced
- Windows network troubleshooting
- IP configuration
- DHCP
- DNS
- Default gateway troubleshooting
- `ipconfig`
- `ping`
- `nslookup`
- ServiceNow incident management
- Root-cause identification
- User verification
- Incident documentation

## Help Desk Workflow
**Report → Log → Triage → Diagnose → Fix → Verify → Document → Resolve**

## Key Lesson
The user reports the symptom; the technician investigates and identifies the underlying cause. A Help Desk technician should verify the network layer by layer rather than immediately assuming that DNS, DHCP, or the entire network is down.
