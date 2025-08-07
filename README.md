# Creating-Forensic-USB
This repo outlines the full setup of a Linux-based forensic USB toolkit designed for incident response, disk and memory acquisition, and triage analysis. All setup steps are performed on a Kali Linux workstation using an organized folder structure and open-source tools.

<h2>Project Folder Structure</h2>

  Local Path: ~/Desktop/Projects/Forensic USB
  
  ```bash
  Forensic USB/
  ├── MemoryCapture/
  ├── DiskImaging/
  ├── Triage/
  ├── LogTools/
  ├── SysInternals/
  ├── Hashing/
  ├── PowerShellScripts/
  ├── CMDTools/
  ├── Templates/
  ├── Docs/
  └── Tools/
  ```
Each folder will contain categories with tools associated with it to acquire documentation used for live and post-modern forensic investigations.

<h2>Step-by-Step Installation</h2>

  1. <h3>Creating Folder Structure</h3>
  ```bash
  mkdir -p ~/Desktop/Projects/"Forensic USB"/{MemoryCapture,DiskImaging,Triage,LogTools,SysInternals,Hashing,PowerShellScripts,CMDTools,Templates,Docs,Tools}
  ```
