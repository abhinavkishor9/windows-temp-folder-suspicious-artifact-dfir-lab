# windows-temp-folder-suspicious-artifact-dfir-lab
## Overview

Windows temporary folders are frequently abused by attackers to stage malware, unpack payloads, execute scripts, and store intermediate files. During DFIR investigations, analysts routinely inspect these directories because malicious files are often created and executed from temporary locations before disappearing.

This lab demonstrates a safe forensic investigation of suspicious files placed inside the Windows Temp directory without executing them.

---

# Executive Summary

During this investigation, several suspicious files were identified within the Windows temporary directory, including an executable, a PowerShell script, and a batch file. These artifacts were examined using Windows-native forensic techniques including file metadata inspection, SHA256 hashing, timestamp analysis, and naming convention review.

No execution of the files was performed. Instead, the investigation focused on evidence preservation and triage, following standard DFIR methodology.

---

# Objectives

- Understand Windows temporary folders
- Investigate suspicious files safely
- Collect forensic evidence without execution
- Calculate SHA256 hashes
- Review metadata and timestamps
- Identify common attacker staging locations

---

# DFIR Concepts Covered

- Windows Temp directories
- Artifact triage
- Metadata analysis
- File hashing
- Evidence preservation
- Initial malware triage
- IOC collection

---

# Tools Used

- PowerShell
- Windows Explorer
- File Properties
- Get-FileHash
- Windows Temp Folder

---

# Lab Environment

| Component | Value |
|----------|---------|
| OS | Windows 10 x64 |
| Environment | VMware Workstation |
| User | Standard Windows User |
| Investigation Type | Host-Based DFIR |
| Execution | None (Static Investigation Only) |

---

# Investigation Scenario

A Windows workstation contains several unfamiliar files inside the Windows temporary directory.

Examples include:

- temp_loader.exe
- invoice_update.ps1
- update.bat

The analyst must determine whether these files require further investigation.

---

# MITRE ATT&CK Mapping

| Technique | ID |
|------------|-----|
| PowerShell | T1059.001 |
| Command and Scripting Interpreter | T1059 |
| User Execution | T1204 |
| Masquerading | T1036 |
| Staged Payload | T1105 (possible delivery staging) |

---

# Skills Demonstrated

- Windows DFIR
- Artifact triage
- Metadata analysis
- SHA256 hashing
- IOC collection
- Evidence preservation
- Windows forensic methodology
- Initial malware assessment
- Static file analysis
- Temporary folder investigation

---

# Evidence Collected

- File metadata
- SHA256 hashes
- File timestamps
- File names
- File paths
- Windows Temp directory contents

---

# Evidence Correlation

The collected evidence was correlated to determine:

- Whether multiple suspicious files appeared together
- Common creation timestamps
- Similar naming conventions
- Shared storage location inside Temp
- Hash uniqueness for future IOC lookup

Although no malicious behavior was observed, the artifacts collectively resemble files commonly used during malware staging.

---

# Investigation Findings

- Suspicious executable identified
- PowerShell script located
- Batch script discovered
- All files stored inside Temp directory
- SHA256 hashes successfully calculated
- Metadata preserved
- No execution performed
- Evidence suitable for escalation

---


# Learning Outcome

This lab demonstrates why Windows temporary folders are one of the highest-priority locations during host-based investigations. Analysts learned to safely collect evidence without risking accidental execution of suspicious files.

---

# Key Takeaway

Never execute suspicious files during an investigation. Preserve evidence first, calculate hashes, inspect metadata, and document findings before moving to deeper malware analysis.
