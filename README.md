# Sauron – YARA-Based Malware Scanner

> Developed and maintained by **Rodney Hester**

**Sauron** is a lightweight, Rust-based malware scanner that uses YARA rules for detecting malicious files. It features real-time filesystem monitoring and is ideal for cybersecurity professionals looking to analyze threats across multiple platforms.

---

## 🔍 Features

- Realtime scanning of file system changes (create/modify)
- Cross-platform support:  
  - Linux (`inotify`)  
  - macOS (`FSEvents`)  
  - Windows (`ReadDirectoryChanges`)  
  - Polling fallback for others
- Full YARA engine integration
- Single-scan mode for folder analysis
- Parallel scanning using configurable thread pool
- Output in text, log, and JSON formats

---

## ⚠️ Limitations

While Sauron is fast and efficient, it is designed for passive monitoring and does **not** block malware execution. Limitations include:

- No blocking/quarantining features
- May fail to scan files with exclusive locks
- Doesn't detect fileless malware
- No correlation between detected files and the originating processes

---

## 🛠️ Build Instructions

Make sure you have `libssl-dev` installed (required by Rust libraries):
```bash
sudo apt install libssl-dev
