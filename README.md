<img width="522" height="274" alt="image" src="https://github.com/user-attachments/assets/93ca07fb-e10b-48c3-8498-ae369eb6af37" />

# Windows 11 Digital Forensics Investigation

## Project Overview
This project is a hands-on digital forensics investigation of a compromised Windows 11 workstation. The goal of the analysis was to investigate a suspected internal data breach, recover deleted evidence, track user activity, and determine if corporate data policies were violated. 

The analysis was conducted using the **Autopsy Forensic Browser**, ensuring cryptographic integrity via SHA-256 hash verification throughout the lifecycle of the investigation.

---

## Tools Used
* **Autopsy Forensic Browser** - Used for database indexing, file carving, and artifact analysis.
* **SHA-256 Hashing** - Used to verify the integrity of the forensic image (`wgu_scenario.001`).

---

## Step-by-Step Evidence Extraction

### Case Setup & Ingestion
* **Case Name:** [Your Student ID / Case Identifier]
* **Base Directory:** `C:\Users\Administrator\Documents\`
* **Verified Image Hash:** `A5A474BB89829FBE66971F0F085FB80331CEC61C24B3020DA9028E109826389C`

---

### Extracted Evidence Items

#### 1.1 Security Event Log
Retrieved the security event log (`Security.evtx`) showing user login activity, authentication successes/failures, and access attempts.
<img width="949" height="711" alt="image" src="https://github.com/user-attachments/assets/f64f1d5c-d3d8-4136-a29b-d847aec3cb4d" />

#### 1.2 User Intent / Task Planning Document
Located a document inside the user directories indicating explicit task planning or intent related to the suspicious activity.
<img width="991" height="700" alt="image" src="https://github.com/user-attachments/assets/dcb8e82c-d21b-47cd-b9e9-b1d1ecd954ac" />

#### 1.3 Unauthorized Executable
Found an unapproved executable (`.exe`) file hidden in the user account profile folders, indicating potential tool usage or malware.
<img width="948" height="709" alt="image" src="https://github.com/user-attachments/assets/12d3c797-31ad-451b-af9a-3b54f3872ac6" />

#### 1.4 Deleted Text File
Identified and carved a deleted text file from unallocated space that contained potentially sensitive or exfiltrated data.
<img width="957" height="711" alt="image" src="https://github.com/user-attachments/assets/1b0295bc-b863-4618-929b-95bcaa5d9c4f" />

#### 1.5 System Event Log
Retrieved the system event log (`System.evtx`) detailing operating system startup, shutdown, errors, and background service activity.
<img width="886" height="664" alt="image" src="https://github.com/user-attachments/assets/306e17e7-8ec7-42bd-8df3-889d979b181c" />

#### 1.6 Edge Browser Cookies
Located Microsoft Edge browser cookies containing active session tokens and login-related data.
<img width="878" height="656" alt="image" src="https://github.com/user-attachments/assets/7c115a45-7925-4943-afa7-7786b40fc670" />

#### 1.7 Edge Prefetch Artifact
Found the most recently modified Edge Prefetch (`.pf`) file, technically confirming exactly when the browser was executed on the system.
<img width="881" height="662" alt="image" src="https://github.com/user-attachments/assets/16b336d2-c077-4130-b9d1-ce59ed67a2db" />

#### 1.8 Hardware & USB Activity Log
Retrieved the system log tracking hardware installation and external USB mass storage device connections.
<img width="876" height="656" alt="image" src="https://github.com/user-attachments/assets/df301bbd-9c17-439d-99fa-d6b23723f3aa" />

#### 1.9 Cached Thumbnail Data
Identified and parsed cached thumbnail data (`thumbcache_*.db`) used to visually reconstruct recent files accessed by the user.
<img width="946" height="709" alt="image" src="https://github.com/user-attachments/assets/d34cd0d6-e4ba-4b8b-af34-ee7469f5faf9" />

#### 1.10 Edge Browser History
Retrieved the Edge browser history database showing user visits to external web services, personal webmail, or file-sharing platforms.
<img width="987" height="700" alt="image" src="https://github.com/user-attachments/assets/e961fb22-5f6c-4230-a2ec-16f34e63cdf2" />

---

## Skills Learned
* **Forensic Image Ingestion:** Handling and verifying raw `.001` forensic disk images.
* **Artifact Carving:** Navigating the Windows file system to extract event logs, prefetch files, and web artifacts.
* **Anti-Forensics Mitigation:** Reconstructing and restoring deleted text files to uncover hidden data.
* **Timeline Analysis:** Correlating browser history, USB insertions, and system logs to build a reliable timeline of events.
