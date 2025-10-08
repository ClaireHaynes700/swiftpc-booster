# ⚡ SwiftPC-Booster

**SwiftPC-Booster** is a lightweight Windows batch utility designed to reclaim disk space and improve system responsiveness by deleting temporary files and cached data and emptying the Recycle Bin.

> 🧹 One-click cleanup for safe and effiecient system maintenace.

---

## 🚀 Features

SwiftPC-Booster performs the following operations:
- Deletes temporary files from:
  - `%TEMP%` (user temp folder)
  - `C:\Windows\Temp`
- Clears old prefetch data from `C:\Windows\Prefetch`
- Empties the Recycle Bin via PowerShell
- Automatically requests Administrator privileges
- Provides clear status output for each operation

---

## ⚠️ Important Notes

- **Administrator access is required** to modify system folders.  
  The script will automatically prompt for elevation if needed.
- **Deleting Prefetch data is optional** — it is *not* necessary for performance.  
  Windows automatically manages Prefetch to speed up app loading; the script clears it only if you choose to.
- The cleanup operations are safe, but **use at your own risk**.  
  Always ensure you understand what’s being deleted before automating this.

---

## 📦 Installation

1. Download or clone this repository:
   ```bash
   git clone https://github.com/ASaha-os/switfpc-booster.git
   
2. Open the folder in File Explorer.

3. Right-click **switfpc-booster.bat** and select **Run as administrator**

4. Follow the on-screen messages. The script will do the following:
    - Clear temporary folders
    - Delete unnecessary cached files
    - Empty the Recycle Bin
    - Display a summary when complete
      
---

## ⚙️ Usage

🖱️ Manual Run

Double-click the batch file (right-click → Run as administrator).

⏰ Optional: Automated Run

Schedule cleanup in the Windows Task Scheduler as follows:

1. Open Windows Task Scheduler
   
2. Under **Actions**, click **Create Task**

3. On the **General** tab, select the **Run with highest privileges** checkbox.

4. On the **Actions** tab, click **New**.

5. In the **New Action** window, in the **Action** field, select **Start a Program** from the dropdown menu.
   
6. In the **Program/script** field, click **Browse** and choose switfpc-booster.bat 

7. Set your preferred trigger (e.g., weekly).

---

## 🧠 How It Works

| Step     | Command  | Task     |
|----------|----------|----------|
| 1        | Clear Prefetch files  | del /f /q %windir%\Prefetch\*  |
| 2        | Clear user temp files  | del /f /q %TEMP%\*  |
| 3        | Clear system temp files | del /f /q %windir%\Temp\* |
| 4        | Empty Recycle Bin  | powershell Clear-RecycleBin -Force


---

## 🧩 Compatibility

✅ Windows 10

✅ Windows 11

⚠️ Not needed or compatible with macOS / Linux (they auto-manage temp files)

---

## 🪪 License
This project is released under the MIT License — feel free to modify and redistribute responsibly.

css
Copy code
MIT License © 2025 [Your Name]

---

🧰 Recommended Alternatives (Built-in)
If you prefer not to use scripts, Windows offers native cleanup tools:

Disk Cleanup: cleanmgr.exe

Storage Sense: Settings → System → Storage → Storage Sense

These provide similar cleanup features with full system safety.

---

## 💡 Future Ideas
 Add PowerShell version with progress and logging

 Add command-line switches (/silent, /log, /prefetch-off)

 Create cross-platform version for macOS & Linux (optional)

---

## 💬 Feedback
Found a bug or have a suggestion?
Open an issue or submit a pull request!

SwiftPC-Booster — simple, fast, and effective system cleanup.
