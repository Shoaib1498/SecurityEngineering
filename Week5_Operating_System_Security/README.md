# Week 5

### Grading

Task #|Points|Description|
-----|:---:|----------|
[Task 1](#task1-bring-your-own-devices) | 1 | Bring Your Own Device
[Task 2](#task2-attacks-on-cpu-execution) | 1 | Attacks on CPU Execution
[Task 3](#task3-securing-os) | 1 | Securing OS
[Task 4](#task4-logging) | 1 | Logging 

---

# Tasks

### Task1: Bring your own devices

Following link containing NIST:s [security recommendations for workplace bring your own device](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.1800-22.pdf). On the page 12 is listed following 9 threat events, and your job is to make one A4 sized poster or otherwise shortly summarize what each listed threat event means based on the document or your own research.

- Intrusive application practices:
Certain mobile apps seek excessive permissions or do activities that are outside their intended purpose. These activities can result in unlawful data gathering, device tracking, or malware infection. NIST recommends evaluating and monitoring app permissions to avoid this sort of infiltration.
- Account credential theft through phishing:
Phishing attacks are a frequent way of acquiring login credentials by deceiving users into disclosing personal information via bogus websites or apps. These credentials can then be used to obtain illegal access to both personal and business information.
- outdated phones:
Phones without the newest operating system or security patches are subject to a variety of risks, including malware and hacking. Maintaining device updates is an essential component of a BYOD policy.
- Sensitive data transmissions:
Attackers can intercept sensitive data delivered unencrypted via insecure networks. This includes unsecured Wi-Fi networks. Encryption and secure VPNs are advised for protecting these transmissions.
- Brute-force attacks to unlock a phone:
In a brute-force attack, attackers utilize automated methods to guess a phone’s passcodes until they successfully unlock it. This exposes both personal and business data on the device. Strong password regulations and biometric access can help to mitigate these assaults.
- Application credential storage vulnerability:
Certain programs save passwords and other sensitive data locally on the device, making them accessible to hackers. To safeguard these credentials, secure storage procedures and appropriate encryption should be used.
- Unmanaged device protection:
Unmanaged devices, or those that are not under the organization’s control or management, provide a risk since the business is unable to enforce security regulations, manage upgrades, or identify threats. To handle these devices, organizations had to implement mobile device management (MDM) systems.
- Lost or stolen data protection:
Data on mobile devices must be protected since they are easily misplaced or stolen. By using the remote wipe feature, businesses can remove confidential data from misplaced or pilfered devices.
- Protecting enterprise data from being:
Workers may inadvertently backup work-related data to personal cloud services, which, if these services are not secure, could result in data breaches. Policies that prohibit data backup to unauthorized cloud providers should be enforced by organizations.


---

### Task2: attacks on CPU execution
spectre and meltdown are two original side channel attacks discovered in 2017 that target cpu, and over the years more have been discovered. [This wikipedia article](https://en.wikipedia.org/wiki/Transient_execution_CPU_vulnerability) list some of them. Pick 3 of them to research about how exactly each exploits the system,their differences, which systems they targeted and how they can be mitigated. 

1. **Foreshadow (L1 Terminal Fault - L1TF)**
Using speculative execution, Foreshadow targets Intel's Software Guard Extensions (SGX) and extracts data from the L1 cache in Intel processors. Attackers have the ability to get over the SGX's defenses, exposing private information kept in the L1 cache. SGX-enabled Intel processors are vulnerable to this exploit. To stop speculative execution attacks, mitigation involves microcode changes that clean the L1 cache during context shifts.
2. **ZombieLoad (Microarchitectural Data Sampling - MDS)**
A larger family of attacks known as Microarchitectural Data Sampling (MDS) includes ZombieLoad. By taking advantage of Intel's speculative execution, it permits attackers to read data from CPU buffers—such as the fill buffers—while the program is running. Starting in 2011, Intel chips are affected by the vulnerability. It has the ability to reveal private information handled by other programs, such as browser history and encryption keys. To lessen the attack surface, mitigation techniques include implementing operating system upgrades, microcode updates, and turning off hyper-threading.
3. **RIDL (Rogue In-flight Data Load)**
During speculative execution, RIDL targets internal CPU buffers, giving attackers access to in-flight data. Though it targets different internal buffers, this attack is similar to ZombieLoad and works well against Intel processors that exploit speculative execution optimizations. It has the ability to steal system and user data that is being processed in real time. Operating system patches, microcode upgrades, and turning off speculative execution capabilities like hyper-threading are examples of mitigation.

To sum up, even though all attacks take advantage of Intel CPUs speculative execution vulnerabilities, they all concentrate on distinct underlying processes. Updates to the microcode, OS-level patches, and sometimes turning off particular CPU functions are needed to mitigate these assaults.



---

### Task3: Securing OS
Following is a list of some of the more common vulnerabilities and attack vectors existing in operating systems.  

- Malware and Viruses
Harm: Malware has the ability to steal confidential information, corrupt files, bring down systems, or grant unauthorized users access to your system.
Mitigation:
1)OS Functionality: Malware is found and eliminated by Windows Defender, an integrated antivirus program.
2)External Tools: Additional security layers, such as firewall management and real-time scanning, are added by third-party antivirus programs like Norton or McAfee. 

- Exploiting Software Vulnerabilities
•	Harm: Via software vulnerabilities, attackers can escalate privileges, obtain unauthorized access, and run harmful code.
•	Mitigation: 
1.	OS Functionality: To address known vulnerabilities, Windows Update often releases security upgrades. 
2.	External programs: Software vulnerabilities can be found and mitigated by using vulnerability scanners like Nessus and endpoint security programs. 

- Phishing and Social Engineering
•	Harm: Phishing attacks deceive people into divulging sensitive information, such passwords or bank account information, which frequently results in identity theft or financial loss. 
• Mitigation:
1.	OS Functionality: Windows comes with SmartScreen, which alerts users to dubious files and websites. 
2.	External software: By blocking phony websites, browser plugins like uBlock Origin and email filtering software can assist stop phishing. 
- Drive-by Downloads
•	Harm: When a person visits an infected website, malicious software is downloaded automatically without their knowledge, which frequently results in data theft or system compromise.
•	Mitigation:
1.	OS Features: Windows SmartScreen identifies and prevents dubious downloads.
2.	External applications: Additional security can be obtained by using browser-based security applications like Malwarebytes Browser Guard. 
- Zero-Day Exploits
• Harm: By utilizing vulnerabilities before a patch is released, zero-day exploits enable attackers to compromise systems covertly. 
• Mitigation: Windows Defender Exploit Guard is an OS functionality that helps to reduce the impact of zero-day attacks. 
External Tools: Advanced threat intelligence for zero-day defense can be obtained from threat detection platforms such as FireEye or CrowdStrike. 
- USB/Removable Media Attacks
• Harm: Infected USB drives have the ability to automatically launch malware, which compromises the system and disseminates malware. 
• Mitigation: 
1.	OS Functionality: You can disable Windows’ AutoPlay feature to stop files from external media from opening automatically. 
2.	External Tools: Unauthorized external devices can be blocked by endpoint protection programs like Symantec Endpoint Protection. 
- Password Cracking
•	Harm: Password cracking techniques can be used by attackers to access accounts, which can result in identity theft or system compromise. 
•	Attenuation: 
1.	OS Functionality: Windows offers additional security layers with support for Windows Hello biometric authentication and Account Lockout policies. 
2.	External Tools: Users can establish strong, one-of-a-kind passwords for each account by using password managers like LastPass or Bitwarden. 
Users can have tiered protection against each of these attack vectors by utilizing a combination of external security solutions and operating system built-in capabilities. 

---

### Task4: Logging
Log files are records of events or actions that occur in a system, application, or program. Logs are essential for troubleshooting, debugging, and analyzing the behavior of software or hardware.

Find answers to following questions:
1. What kind of information would be saved into following types of log files
- Application logs:Keep track of events that are unique to a given program, like crashes, user communications, resource consumption, or performance indicators.
- Event logs: Record all system-wide activities, such as system startup, shutdown, security incidents, and logins and logouts.
- Service logs: Provide information on how network, database, and web server services—among other background services—are operated.
- System logs: Hold details regarding hardware malfunctions, boot procedures, system crashes, and general system activity.

2. Where in each of the common Operating Systems those logs would be stored (Windows, Mac, Linux(changes per distro so provide in answer which you are using)


Windows: Application Logs: C:\Windows\System32\winevt\Logs\Application.evtx


Mac (macOS): Application Logs: ~/Library/Logs and /Library/Logs


Linux (Ubuntu/Debian): Application Logs: /var/log/


3. What kind of threats could you notice by monitoring each log file?


Application Logs: Software malfunctions, unauthorized application usage, or data exfiltration attempts.


Event Logs: Failed login attempts, privilege escalation, and unusual system file changes.

4. How would you go about monitoring logs on your personal computer?


Windows: The Event Viewer allows users to monitor logs.


Mac: The Console app is used to view system logs.


Linux: journalctl, tail -f, or rsyslog can be used to monitor logs.



https://en.wikipedia.org/wiki/Transient_execution_CPU_vulnerability

