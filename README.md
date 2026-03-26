

#​Mobile Endpoint Remediation and Persistence Removal              

**​Security Researcher**Chaz Pineda
System:**Android OS                                   
​###🚩 Executive Summary
​Successfully identified and neutralized a multi-vector compromise on a personal mobile endpoint.
This project involved deep-system auditing to remove malicious persistence mechanisms, hardening * **network Hardening*. configurations, and securing primary identity credentials to restore device integrity.

 ###​ 🔍 Technical Analysis
* **​Persistence Mechanism:** Identified a rogue **"Note Launcher"** application that had successfully escalated to **Device Administrator** privileges, allowing it to bypass standard uninstallation and monitor system activity.
​* **Network Compromise:** Detected unauthorized **eSIM profiles** creating secondary network paths, which served as potential vectors for data exfiltration and man-in-the-middle attacks.
* **​Indicators of Compromise (IoCs):** Observed system-wide UI glitches, font inconsistencies, and unauthorized background process execution.
  
​### 🛠️ Remediation Steps
​* **Privilege De-escalation:** Manually revoked Device Ad2min rights for the rogue launcher through system settings and performed a full application removal.
* **​Network Hardening:** Audited and purged unauthorized eSIM profiles to restore single-path network integrity and prevent unauthorized cellular data routing.
​* **Identity Security:** Performed a full credential rotation and updated **Multi-Factor Authentication (MFA)** for the primary Google account to prevent session hijacking.
​💡 Developer & Security Takeaways
​Zero Trust Architecture: Applied a "Verify then Trust" approach to all third-party system utilities.
​Least Privilege: Documented the high-risk nature of granting "Admin" or "Accessibility" permissions to non-essential applications.
​Policy Logic: Conceptualized a Kotlin-based check using DevicePolicyManager to programmatically detect and block unauthorized administrative apps in a production environment.
