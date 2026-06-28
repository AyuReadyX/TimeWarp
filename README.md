# TimeWarpX v1.0

A tool similar to RunAsDate that allows you to run specific applications under a modified system date and time.

---


### CMD / PowerShell Usage
`timewarp.exe` has no GUI and is ideal for automated startup scripts.

```bash
# Syntax
.\timewarp.exe [-x32|-x64] YYYY-MM-DD HH:MM [App] [Wildcards...]
# <------------------- Mandatory ------------> <- Optional ->

# Examples
.\timewarp.exe -x64 2017-09-24 09:30 testdate64.exe
.\timewarp.exe -x32 2025-05-11 06:00 testdate32.exe App2 App3
.\timewarp.exe -x64 2019-02-19 18:00 "C:\Program Files\testdateapp\testdate64.exe" App2 App3
```

#### Alternative Standalone Syntax:
```bash
.\timewarpx32.exe YYYY-MM-DD HH:MM TestDate32.exe [Wildcards...]
.\timewarpx64.exe YYYY-MM-DD HH:MM TestDate64.exe [Wildcards...]
```

### PowerShell One-Liner (Startup Example)
All included executables accept arguments and can run standalone. Use this snippet to launch silently at startup:

```powershell
Start-Process -FilePath ".\timwarp.exe" -ArgumentList "-x64", "2024-05-11", "12:00", "C:\Program Files\testdateapp\testdate64.exe", "AppChildProcess1" , "AppChildProcess2" -WindowStyle Hidden
```

⚠️ **Important Notes:**
* The first target `.exe` argument must use an **absolute path** unless `timewarp.exe` is placed directly inside the target executable's directory.

---

## 🛡️ Antivirus & False Positives

* **`timewarp.exe` (No GUI):** Completely clean. Passes all Antivirus checks.

> 💡 **Tip:** If your Antivirus flags the GUI, you do not need to use it. The CLI tools provide full functionality and are completely clean.

### VirusTotal Scans
* [VirusTotal Scan - timewarp.exe (No GUI)](https://www.virustotal.com/gui/file/c13ba4c17736dea32c29a255b12e78854805764cd05383b146b6c48750f6d935)

