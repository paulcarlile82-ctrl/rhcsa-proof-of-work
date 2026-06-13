# RHCSA Proof of Work: Enterprise System Administration

This repository serves as a professional portfolio demonstrating enterprise Linux engineering capabilities on Rocky Linux 9 / RHEL 9 environments. Below are live terminal demonstrations showcasing core storage management and networking tasks.

---

## 📺 Live Terminal Demonstrations

### 1. Dynamic LVM Storage Expansion
*Topics Covered: Physical Volumes, Volume Groups, Logical Volumes, XFS Live Resizing*  
Click the player badge below to watch the dynamic storage expansion workflow without system downtime:

[![asciinema](https://asciinema.org/a/pYWLOgjccKnWreE7.svg)](https://asciinema.org/a/pYWLOgjccKnWreE7)

---

### 2. Network NTP Synchronization
*Topics Covered: chronyd Configuration, Upstream Strata Pools, systemd Units, Validation*  
Click the player badge below to watch the complete network time synchronization and peer verification process:

[![asciinema](https://asciinema.org/a/gFT4hB9uWk0ZND2u.svg)](https://asciinema.org/a/gFT4hB9uWk0ZND2u)

---

## 🛠️ Technical Implementation Details

### I. Logical Volume Management (LVM) Architecture
In production deployments, storage demands fluctuate. Using LVM allows raw block devices to be aggregated into abstract pools that can be carved out or scaled up dynamically.

*   **Workflow Executed:** 
    1. Audited block layer geometry with `pvs`, `vgs`, and `lvs`.
    2. Extended the logical volume using `lvextend`.
    3. Grew the online XFS file system using `xfs_growfs` to reflect changes immediately without unmounting.

### II. Network Time Protocol (NTP) Synchronization
Precise system time synchronization is non-negotiable in enterprise infrastructure to ensure valid security logging (SELinux audit trails), Kerberos authentication tickets, and correct multi-node database clustering sequence.

*   **Workflow Executed:**
    1. Baseline synchronization checked using `chronyc tracking`.
    2. Configured secure public NTP strata sources inside `/etc/chrony.conf`.
    3. Persisted configuration using `systemctl restart chronyd` and `systemctl enable chronyd`.
    4. Verified active source offset metrics via `chronyc sources -v`.
