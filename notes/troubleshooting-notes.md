# Troubleshooting Notes

## Problem

Temp folder not opening.

### Solution

Use:

```

%TEMP%

```

or

```

%LOCALAPPDATA%\Temp

```

---

## Problem

Get-FileHash cannot find file.

### Solution

Verify filename and path.

Example:

```powershell
Get-ChildItem $env:TEMP
```

---

## Problem

File extension hidden.

### Solution

Explorer

View

Enable

```

File name extensions

```

---

## Problem

Permission denied.

### Solution

Open PowerShell as Administrator.

---

## Problem

File already exists.

### Solution

Delete previous lab artifacts.

```powershell
Remove-Item C:\TempArtifactLab -Recurse
```

---

## Problem

Properties do not show metadata.

### Solution

Verify the file exists and refresh Explorer.

---

## Lessons Learned

- Never execute suspicious files.
- Preserve evidence first.
- Collect hashes immediately.
- Document timestamps.
- Temporary folders should always be examined during DFIR investigations.
