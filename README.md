**Project Overview**

This project documents a hands-on Splunk SIEM investigation completed as part of the Blue Team Labs Online (BTLO) – MiddleMayhem challenge. The objective was to analyze real-world style log data to identify malicious activity, trace attacker behavior, and accurately interpret security events based strictly on SIEM evidence.

The investigation covers initial compromise, payload delivery, and post-exploitation behavior, with a strong focus on log-driven analysis rather than assumption-based conclusions.

**Objectives**

Identify the external attacker responsible for the compromise

Analyze web server logs to detect exploitation and payload delivery

Investigate reverse shell execution and outbound callback behavior

Discover sensitive site locations exposed through misconfiguration

Identify post-compromise authentication activity and lateral movement attempts

Accurately report attacker techniques as recorded in SIEM logs

**Tools & Technologies**

Splunk Enterprise – log analysis and correlation

Linux authentication logs (sshd, pam_unix)

Web server access logs

Network / flow telemetry

Blue Team Labs Online (BTLO)

**Investigation Highlights**
**1️ Attacker Identification**

Correlated suspicious web activity to a single external source IP:

218.92.0.204

**2️ Web Exploitation & Reverse Shell**

Detected access to a malicious PHP file (shell.php)

Confirmed execution of a reverse shell payload

Identified outbound callback behavior consistent with post-exploitation access

**3️ Sensitive Location Discovery**

Identified exposed administrative paths via site-discovery files:

/admin
/admin/file-upload

**4️ Post-Compromise Authentication Activity**

Analyzed Linux authentication logs showing repeated password failures followed by successful access

Correctly identified the technique as explicitly recorded in the SIEM logs:

SSH brute-force

**Key Takeaways**

Effective SIEM investigations rely on what the logs actually record, not assumptions

Raw log parsing is often required when structured fields are inconsistent

Site-discovery files remain a common source of sensitive exposure

Understanding the distinction between evidence and interpretation is critical in SOC work
