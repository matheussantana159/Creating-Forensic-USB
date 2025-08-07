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

<h3>1. Creating Folder Structure</h3>

  ```bash
  mkdir -p ~/Desktop/Projects/"Forensic USB"/{MemoryCapture,DiskImaging,Triage,LogTools,SysInternals,Hashing,PowerShellScripts,CMDTools,Templates,Docs,Tools}
  ```

<h3>2. Memory Acquisition Tools</h3>

  ```bash
  cd ~/Desktop/Projects/"Forensic USB"/MemoryCapture
  git clone https://github.com/504ensicsLabs/LiME.git
  ```
LiME (Linux Memory Extractor) - Captures physical memory from Linux systems.
GitHub: https://github.com/504ensicsLabs/LiME
  
<h3>3. Disk Imaging Tools</h3>

  ```bash
  sudo apt install dcfldd guymager -y
  ```
dcfldd – Enhanced dd with progress meter.

Guymager – GUI disk imaging tool.
  
<h3>4. Triage Tools</h3>

  ```bash
  cd ~/Desktop/Projects/"Forensic USB"/Triage
  curl -LO https://github.com/Velocidex/velociraptor/releases/latest/download/velociraptor-v0.7.1-linux-amd64
  chmod +x velociraptor-v0.7.1-linux-amd64
  mv velociraptor-v0.7.1-linux-amd64 velociraptor
  ```

Velociraptor – Endpoint visibility and DFIR collection.

GitHub: https://github.com/Velocidex/velociraptor
  
<h3>5. Log Parsing Tools</h3>

  ```bash
  cd ~/Desktop/Projects/"Forensic USB"/LogTools
  sudo apt install cargo -y
  git clone https://github.com/omerbenamram/evtx.git
  cd evtx
  cargo build --release
  ```

evtx – Parses Windows Event Logs.

GitHub: https://github.com/omerbenamram/evtx
  
<h3>6. System Analysis Alternatives to SysInternals</h3>

  ```bash
  sudo apt install sysstat net-tools lsof htop strace tcpdump -y
  ```

tcpdump – Packet capture

lsof – Open files

htop – Process monitor

strace – Syscall tracer
  
<h3>7. Hashing Tools</h3>

  ```bash
  sudo apt install hashdeep -y
  ```

hashdeep – Recursive hashing of files.

sha256sum, md5sum already available on most Linux systems.
  
<h3>8. Create Script & Template Files</h3>

  ```bash
  cd ~/Desktop/Projects/"Forensic USB"/PowerShellScripts
  touch analyze_network.ps1 list_processes.ps1
  
  cd ~/Desktop/Projects/"Forensic USB"/CMDTools
  touch netstat_output.sh process_list.sh
  
  cd ~/Desktop/Projects/"Forensic USB"/Templates
  touch CaseNotes_Template.md EvidenceChecklist.md ToolUsage_QuickCommands.md
  
  cd ~/Desktop/Projects/"Forensic USB"/Docs
  touch artifact_locations.md setup_instructions.md
  ```

<h2>Using USB/SSD Drives and Suggested Additions</h2>

Make sure to format USB/SSD as exFAT or NTFS so it can store large files such as RAM dumps
Add custom scripts to CMDTools or PowerShellScripts to streamline downloads.
Maintain research logs, notes, and findings in Docs/
Add Eric Zimmerman's tools and KAPE for Win if dual-booting or building a Win specific toolkit.

<h3>References</h3>

LiME: https://github.com/504ensicsLabs/LiME

Velociraptor: https://github.com/Velocidex/velociraptor

evtx: https://github.com/omerbenamram/evtx

Guymager: https://guymager.sourceforge.io/

Hashdeep: https://packages.debian.org/search?keywords=hashdeep

Sysstat/net-tools: https://linux.die.net/man/1/sysstat




  
