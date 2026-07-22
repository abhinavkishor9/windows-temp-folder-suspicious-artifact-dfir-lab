# Investigation Notes

## Lab Summary

A static DFIR investigation was conducted on suspicious files located inside the Windows Temp directory. The objective was to identify potentially malicious artifacts while preserving forensic integrity.

---

# Analyst Methodology

The investigation followed a standard DFIR triage workflow:

1. Identify suspicious storage location.
2. Locate newly created artifacts.
3. Record filenames.
4. Preserve original evidence.
5. Examine file metadata.
6. Calculate SHA256 hashes.
7. Compare timestamps.
8. Avoid executing files.
9. Document findings.

---

# Investigation Steps

### Step 1

Created a dedicated lab folder.

### Step 2

Generated sample suspicious files.

- temp_loader.exe
- invoice_update.ps1
- update.bat

### Step 3

Copied the files into:

```

%LOCALAPPDATA%\Temp

```

### Step 4

Inspected Temp directory.

Observed multiple executable/script artifacts.

### Step 5

Opened Properties.

Collected:

- Created time
- Modified time
- Size
- Extension

### Step 6

Calculated SHA256 hashes.

PowerShell:

```powershell
Get-FileHash "$env:TEMP\temp_loader.exe"

Get-FileHash "$env:TEMP\invoice_update.ps1"
```

### Step 7

Compared timestamps.

Files were created within the same timeframe.

### Step 8

Did NOT execute files.

Evidence remained intact.

### Step 9

Removed artifacts.

---

# Evidence Collected

- SHA256 hashes
- File metadata
- Temp directory contents
- File properties
- Creation timestamps

---

# Analyst Observations

- Multiple suspicious artifacts stored together.
- Executable, script, and batch files commonly appear during malware staging.
- Temporary folders remain high-risk forensic locations.
- Hash collection completed successfully.
- Evidence was preserved throughout the investigation.

---

# Conclusion

The investigation successfully demonstrated safe artifact triage within Windows temporary folders. No files were executed, ensuring forensic integrity while collecting valuable evidence for potential escalation.
