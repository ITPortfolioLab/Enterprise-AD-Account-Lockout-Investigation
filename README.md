# Enterprise Active Directory Account Lockout Investigation

## Project Summary
This project simulates a real corporate help desk incident where a finance user was repeatedly locked out of their Active Directory account due to saved incorrect credentials on a domain-joined workstation.

## Business Scenario
A finance employee was unable to access Windows, Outlook, mapped drives, and internal systems because their AD account kept locking every few minutes. The incident affected productivity and generated repeated help desk tickets.

## Environment
- Windows Server 2022 Domain Controller
- Windows 11 domain-joined client
- Active Directory Domain Services
- Domain: corp.local
- Client: CLIENT01
- User: e.clarke

## Incident Description
User reported: "My account keeps locking even after my password was reset. I can log in for a short time, then everything stops working again."

## Investigation
- Verified user lockout status in Active Directory
- Reviewed Event Viewer Security logs
- Identified Event ID 4740
- Confirmed Caller Computer Name as CLIENT01
- Checked mapped drives and saved credentials
- Found outdated credentials used against a shared folder

## Root Cause
The user had a persistent mapped drive connection on CLIENT01 using an old password. This caused repeated failed authentication attempts and triggered the AD account lockout policy.

## Resolution
- Removed incorrect mapped drive
- Cleared saved Windows credentials
- Unlocked the AD account
- Validated successful login and share access
- Confirmed no further lockouts occurred

## Skills Demonstrated
- Active Directory troubleshooting
- Windows Server administration
- Event Viewer log analysis
- PowerShell investigation
- Account lockout resolution
- Incident management
- Root cause analysis
- Technical documentation

## Evidence
See the `/evidence` folder for screenshots, logs, and command outputs.

## Lessons Learned
This project demonstrates how recurring account lockouts are often caused by cached credentials, mapped drives, mobile devices, services, or scheduled tasks using outdated passwords.
