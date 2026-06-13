# RHCSA Proof of Work: Network Time Protocol (NTP) Sync

This repository contains live terminal demonstrations and technical documentation for configuring and verifying Network Time Protocol (NTP) synchronization on Rocky Linux 9 / RHEL 9 enterprise environments.

---

## 📺 Live Terminal Demonstrations

### 1. Network NTP Synchronization (Full System Walkthrough)
*Recorded on: June 13, 2026* This demonstration showcases the complete configuration flow of `chronyd`, editing configuration files, managing systemd units, and validating upstream peer connectivity.

[![asciinema](https://asciinema.org/a/gFT4hB9uWk0ZND2u.svg)](https://asciinema.org/a/gFT4hB9uWk0ZND2u)

### 2. Network NTP Synchronization (Initial Walkthrough)
*Recorded on: June 12, 2026* This demonstration captures the initial baseline validation and environment discovery.

[![asciinema](https://asciinema.org/a/pYWLOgjccKnWreE7.svg)](https://asciinema.org/a/pYWLOgjccKnWreE7)

---

## 🛠️ Technical Implementation Details

In enterprise deployments, precise clock synchronization is critical for security logs (SELinux auditing), Kerberos authentication, and multi-node cluster sequencing. This project implements time synchronization using the default RHEL 9 NTP client, **Chrony**.

### Core Components Configured:
* **Service Daemon:** `chronyd` (replaces legacy `ntpd`)
* **Configuration Path:** `/etc/chrony.conf`
* **Management Utility:** `chronyc`

### System Administration Workflow Executed:

1. **Verify Baseline Status:**
   Inspected the initial synchronization state using the RHEL 9 native tool structure:
   ```bash
   chronyc tracking
