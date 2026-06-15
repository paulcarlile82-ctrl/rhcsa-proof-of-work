# Red Hat Enterprise Linux 9 - Technical Proof of Work

Welcome to my systems administration laboratory repository. Below you will find interactive, recorded demonstrations of core enterprise Linux configurations executed on a Rocky Linux 9 environment.

### 🎬 Pacing & Viewer Controls
* **Real-Time Execution:** To maintain transparency, four of these recordings run in real-time exactly as executed in the terminal.
* **Optimized Playback (2x):** The **LVM Creation & Storage Expansion** lab and the **Podman Service Deployment** lab are pre-accelerated to **2x speed**. This ensures a tight, concise viewing experience by keeping the focus on command execution rather than background processing time.
* **Interactive Terminal:** Because these are `asciinema` casts rather than flat video files, you can **pause the player at any time and copy/paste text strings directly out of the screen** to verify syntax or audit the command choices.

---

## 🛠️ Laboratory Demonstrations (Ordered by Infrastructure Stack Hierarchy)

### 1. Rootless Podman Containerization & Systemd Automation
Demonstrates deploying a containerized Nginx web app without root privileges, passing SELinux flags (`:Z`), setting localized environment runtimes, and mapping the workflow to an independent systemd user space service that persists across machine boots.

[![Podman Lab Player](https://asciinema.org/a/h497197hTNWW7gAo.svg)](https://asciinema.org/a/h497197hTNWW7gAo)

---

### 2. Logical Volume Management (LVM) Creation & Space Expansion
A deep dive into dynamic enterprise storage layout manipulation. Demonstrates hot-growing physical volumes, handling volume group bounds, and expanding logical volumes safely with immediate on-the-fly filesystem extensions.

[![LVM Lab Player](https://asciinema.org/a/pYWLOgjccKnWreE7.svg)](https://asciinema.org/a/pYWLOgjccKnWreE7)

---

### 3. SELinux Port Contexts & Firewalld Rich Rules
Demonstrates enterprise-grade network hardening. Includes modifying non-standard port behaviors using `semanage port` and structuring complex traffic filtering using advanced `firewalld` rich language rules.

[![SELinux Lab Player](https://asciinema.org/a/r03G1tcp4PrtWfZ2.svg)](https://asciinema.org/a/r03G1tcp4PrtWfZ2)

---

### 4. Storage Automation (AutoFS & Network File Systems)
Configuring on-demand network storage. Demonstrates linking remote NFS mount targets using `autofs` wildcards, allowing storage mounts to dynamically spin up and map on hardware access and quietly unmount when idle.

[![AutoFS Lab Player](https://asciinema.org/a/wJpc7wrb2GT1qqga.svg)](https://asciinema.org/a/wJpc7wrb2GT1qqga)

---

### 5. File System Permissions (ACLs & SGID)
An exploration of collaborative enterprise directories. Shows the deployment of the `setgid` bit for inherited group ownership alongside POSIX Access Control Lists (ACLs) to manage non-standard access requirements cleanly.

[![Permissions Lab Player](https://asciinema.org/a/wJpc7wrb2GT1qqga.svg)](https://asciinema.org/a/wJpc7wrb2GT1qqga)

---

### 6. Network Topology & Time Sync (Nmcli & Chrony)
Enterprise client initialization. Shows network interface provisioning entirely via the standard RHEL 9 `nmcli` mechanism, followed by configuring NTP synchronization clients utilizing `chrony` to guarantee unified log timestamps.

[![Network Lab Player](https://asciinema.org/a/gFT4hB9uWk0ZND2u.svg)](https://asciinema.org/a/gFT4hB9uWk0ZND2u)

---
*All environments are configured to align with RHEL 9 infrastructure expectations and RHCSA (EX200) production standards.*
