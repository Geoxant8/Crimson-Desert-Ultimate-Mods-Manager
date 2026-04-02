# Crimson-Desert-Ultimate-Mods-Manager


<img width="1250" height="817" alt="image" src="https://github.com/user-attachments/assets/2bd2c6e2-d88f-45d0-a77b-8e7a022f8349" />


# 🌵 Crimson Desert Ultimate Mods Manager (CDUMM)

## 🧩 About
Crimson Desert Ultimate Mods Manager (CDUMM) is a powerful desktop tool designed specifically for modding **Crimson Desert** in a safe, flexible, and fully reversible way.

Unlike basic mod installers, CDUMM deeply understands the game's archive system (**PAZ / PAMT / PAPGT**) and allows multiple mods to modify the same files without breaking the game. It achieves this through delta-based patching, intelligent conflict resolution, and integrity-aware file composition.

The goal of the project is simple: make modding stable, predictable, and user-friendly — even when combining complex or incompatible mods.

⚠️ This project is currently in **beta**, but already stable for everyday use.

---

## 🚀 Core Features
CDUMM focuses on automation and safety while keeping the workflow extremely simple.

You can install mods via drag-and-drop using multiple formats including ZIP archives, loose folders, script installers (.bat / .py), binary patches (.bsdiff), and ASI plugins. Script-based mods are executed normally, while the manager automatically detects and captures file changes.

Every imported mod goes through a **health check system** that detects duplicate files, broken archive integrity, incorrect file sizes, and version mismatches. When possible, issues are automatically fixed to prevent crashes.

Mods are stored as **binary deltas**, meaning only changed bytes are saved instead of full files. This allows multiple mods to safely modify the same archive while keeping disk usage minimal and ensuring everything remains reversible.

The manager includes a **3-level conflict detection system** that clearly shows how mods overlap:
- Metadata conflicts are handled automatically  
- Archive-level conflicts are usually safe  
- Byte-level conflicts are resolved via load order  

A full **ASI plugin manager** is also included, allowing you to install, update, enable/disable, and configure plugins without touching the game directory manually.

---

## ⚙️ How It Works
CDUMM uses a structured pipeline to ensure stability and compatibility.

On first launch, the manager creates a **snapshot of your vanilla game files** using SHA-256 hashes. This snapshot acts as the baseline for all future operations.

When you import a mod, the manager compares modified files against the vanilla snapshot and stores only the binary differences. Before applying, all mods are validated to detect potential issues early.

When you click **Apply**, CDUMM composes all enabled mods in priority order. If a mod changes archive structure (PAZ-shift), the system automatically adjusts offsets so other mods remain compatible.

The integrity chain (PAPGT) is rebuilt every time, ensuring the game accepts modified files. All operations are atomic, meaning if anything fails mid-process, changes are rolled back automatically.

---

## 🧠 Mod Management
Managing mods in CDUMM is designed to be flexible and transparent.

You can reorder mods using Move Up / Move Down or drag-and-drop. Mods higher in the list are applied last and take priority in conflicts.

Mods can be enabled or disabled at any time without being removed. The manager will correctly apply or remove their changes during the next Apply operation.

A built-in **dry-run test system** allows you to analyze a mod before installing it. It shows which files will be affected and detects conflicts with your current setup.

Additionally, a detailed **conflict tree view** displays exactly what overlaps between mods, including byte ranges, making it easy to understand what is happening under the hood.

---

## 🔄 Apply, Revert & Safety
Safety is a core design principle of CDUMM.

Applying mods uses atomic file operations, ensuring the game is never left in a partially modified state. If something goes wrong, the system automatically rolls back changes.

At any time, you can click **Revert to Vanilla** to instantly restore your original game files. Since only byte-level changes are stored, this process is fast and reliable.

Even in worst-case scenarios, you can always use **Steam → Verify Integrity** to fully restore the game.

The manager also includes a built-in **bug report generator** that collects logs, system info, and mod data into a ready-to-send report for troubleshooting.

---

## 📥 Installation & Requirements
Getting started is quick and requires no additional dependencies.

1. Download `CrimsonDesertModManager.msi`  
2. Place it anywhere on your system  
3. Launch the application  
4. Select your Crimson Desert installation folder  
5. Wait for the initial snapshot to complete  
6. Start installing mods via drag-and-drop  

Requirements:
- Windows 10 / 11  
- Crimson Desert (Steam version)  
- Minimal disk space (delta storage, not full backups)  

No Python or external tools are required — the application is fully standalone.

---

## ❓ FAQ
**Is it safe to use?**  
Yes. All changes are reversible and protected by atomic operations. You can revert to vanilla at any time.

**What if a mod shows a warning?**  
The health check detects packaging issues. Most are auto-fixed. For critical issues, you can generate a bug report and send it to the mod author.

**Can I use mods installed manually?**  
It is strongly recommended to start from a clean game and import all mods through CDUMM for best compatibility.

**What happens if mods conflict?**  
Conflicts are clearly displayed. In most cases, load order resolves them automatically.

**Does it support ASI plugins?**  
Yes, fully. They are managed separately with their own tools and conflict detection.

**What after a game update?**  
Verify game files via Steam, reset the snapshot, and re-import mods.

---

## 📝 Patch Notes
The project is actively maintained and continuously improved.

**v1.0.0**
- JSON patch support  
- Loose-file mod support  
- Full UI redesign (sidebar + action bar)  
- Drop-to-update system  
- Launch game button  

**v0.9.x – v0.7.x**
- Mod profiles and auto-update system  
- Improved script mod handling  
- Stability fixes and performance improvements  
- PAPGT rebuild fixes and archive handling improvements  

**v0.6.x – v0.5.x**
- Initial release  
- Delta-based patching system  
- Conflict detection and load order  
- ASI plugin support  

---

## ⭐ Final Notes
CDUMM is built to simplify complex mod setups and eliminate common issues like crashes, broken archives, and incompatible mods.

It combines deep technical understanding of the game’s file system with a simple user experience, making it suitable for both beginners and advanced users.

If you want a reliable way to mod Crimson Desert without constantly fixing your game — this manager is designed for exactly that.
