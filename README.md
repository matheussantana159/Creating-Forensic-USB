# Creating-Forensic-USB
This repo outlines the full setup of a Linux-based forensic USB toolkit designed for incident response, disk and memory acquisition, and triage analysis. All setup steps are performed on a Kali Linux workstation using an organized folder structure and open-source tools.

<h2>Project Folder Structure</h2>

  Local Path: ~/Desktop/Projects/Forensic USB
  
  ```bash
Forensic USB/
├── Linux/
│   ├── MemoryCapture/
│   ├── DiskImaging/
│   ├── Triage/
│   ├── LogTools/
│   ├── SysInternals/
│   ├── Hashing/
│   ├── CMDTools/
│   └── Docs/
├── Windows/
│   ├── MemoryCapture/
│   ├── DiskImaging/
│   ├── Triage/
│   ├── LogTools/
│   ├── SysInternals/
│   ├── Hashing/
│   ├── PowerShellScripts/
│   ├── Templates/
│   └── Docs/
└── Tools/
  ```
Each folder will contain categories with tools associated with it to acquire documentation used for live and post-modern forensic investigations.

<h2>Linux Workstation Setup</h2>

<h3>1. Creating Linux Folder Structure</h3>

  ```bash
  mkdir -p ~/Desktop/Projects/"Forensic USB"/Linux/{MemoryCapture,DiskImaging,Triage,LogTools,SysInternals,Hashing,CMDTools,Docs}
  ```

<h3>2. Memory Acquisition</h3>

  ```bash
  cd ~/Desktop/Projects/"Forensic USB"/Linux/MemoryCapture
  git clone https://github.com/504ensicsLabs/LiME.git
  ```
- LiME (Linux Memory Extractor) - Captures physical memory from Linux systems.
- GitHub: https://github.com/504ensicsLabs/LiME
  
<h3>3. Disk Imaging</h3>

  ```bash
  sudo apt install dcfldd guymager -y
  ```
- dcfldd – Enhanced dd with progress meter.
- Guymager – GUI disk imaging tool.
  
<h3>4. Triage Tools</h3>

  ```bash
  cd ~/Desktop/Projects/"Forensic USB"/Linux/Triage
  curl -LO https://github.com/Velocidex/velociraptor/releases/latest/download/velociraptor-v0.7.1-linux-amd64
  chmod +x velociraptor-v0.7.1-linux-amd64
  mv velociraptor-v0.7.1-linux-amd64 velociraptor
  ```

- Velociraptor – Endpoint visibility and DFIR collection.
- GitHub: https://github.com/Velocidex/velociraptor
  
<h3>5. Log Parsing Tools</h3>

  ```bash
  cd ~/Desktop/Projects/"Forensic USB"/Linux/LogTools
  sudo apt install cargo -y
  git clone https://github.com/omerbenamram/evtx.git
  cd evtx
  cargo build --release
  ```

- evtx – Parses Windows Event Logs.
- GitHub: https://github.com/omerbenamram/evtx
  
<h3>6. System Tools</h3>

  ```bash
  sudo apt install sysstat net-tools lsof htop strace tcpdump -y
  ```

- tcpdump – Packet capture
- lsof – Open files
- htop – Process monitor
- strace – Syscall tracer
  
<h3>7. Hashing Tools</h3>

  ```bash
  sudo apt install hashdeep -y
  ```

- hashdeep – Recursive hashing of files.
- sha256sum, md5sum already available on most Linux systems.
  
<h3>8. CMD Scripts</h3>

  ```bash
  cd ~/Desktop/Projects/"Forensic USB"/Linux/CMDTools
  touch netstat_output.sh process_list.sh
  ```

<h3>Windows Workstation Toolkit</h3>

<h2>1. Creating Windows Folder Structure</h2>

  ```ps
  New-Item -ItemType Directory -Path "~/Desktop/Projects/Forensic USB/Windows" -Name "MemoryCapture","DiskImaging","Triage","LogTools","SysInternals","Hashing","PowerShellScripts","Templates","Docs"
  ```

<h2>2. Memory Acquisition Tools (Manual Download)</h2>

  - DumpIt (MOONSOLS)
  - Magnet RAM Capture
  - Belkasoft RAM Capturer

<h2>3. Disk Imaging</h2>

  - FTK Imager Lite
  - dd for Windows

<h2>4. Triage</h2>

  - KAPE
  - Eric Zimmerman's Tools

<h2>5. Log Tools</h2>
  
  - EvtxECmd (EZ Tools)
  - MFTECmd
  - SRUM-Dump

<h2>6. SysInternals</h2>

  - Sysinternals Suite

<h2>7. Hashing Tools</h2>

  - HashMyFiles (Nirsoft)
  - fciv.exe (Legacy Microsoft tool)
  - Built-in: certutil -hashfile <filename> SHA256

<h2>8. Scripts and Templates</h2>

  ```bash
  cd "~/Desktop/Projects/Forensic USB/Windows/PowerShellScripts"
  New-Item -Name analyze_network.ps1, list_processes.ps1 -ItemType File
  
  cd "~/Desktop/Projects/Forensic USB/Windows/Templates"
  New-Item -Name CaseNotes_Template.md, EvidenceChecklist.md, ToolUsage_QuickCommands.md -ItemType File
  
  cd "~/Desktop/Projects/Forensic USB/Windows/Docs"
  New-Item -Name artifact_locations.md, setup_instructions.md -ItemType File
  ```

<h2>Using USB/SSD Drives and Suggested Additions</h2>

- Make sure to format USB/SSD as exFAT or NTFS so it can store large files such as RAM dumps.
- Add custom scripts to CMDTools or PowerShellScripts to streamline downloads.
- Maintain research logs, notes, and findings in Docs/

<h3>References</h3>

  1. LiME: https://github.com/504ensicsLabs/LiME
  2. Velociraptor: https://github.com/Velocidex/velociraptor
  3. evtx: https://github.com/omerbenamram/evtx
  4. Guymager: https://guymager.sourceforge.io/
  5. Hashdeep: https://packages.debian.org/search?keywords=hashdeep
  6. Sysinternals Suite: https://learn.microsoft.com/en-us/sysinternals/
  7. FTK Imager: https://accessdata.com/product-download
  8. KAPE: https://www.kroll.com/en/services/cyber-risk/incident-response-litigation-support/kroll-artifact-parser-extractor-kape
  9. EZ Tools: https://ericzimmerman.github.io/
  10. DumpIt: https://www.moonsols.com/software/memoryze/
  11. Magnet RAM Capture: https://www.magnetforensics.com/resources/magnet-ram-capture/
  12. Belkasoft RAM Capturer: https://belkasoft.com/ram-capturer
  13. HashMyFiles: https://www.nirsoft.net/utils/hash_my_files.html






  
