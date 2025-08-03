# Log-Analysis-Bash-Script
Bash script to analyze log files and extract ERROR, FATAL, and CRITICAL entries.

# 🛠️ Log Analysis Bash Script  
A simple yet powerful **Bash script** to analyze `.log` files and extract important error entries such as **ERROR**, **FATAL**, and **CRITICAL**.  
This script is ideal for **DevOps engineers** and **system administrators** who want to quickly identify critical issues in logs.

---

📌 Features
- ✅ Scans `.log` files updated in the last 24 hours  
- ✅ Detects and counts `ERROR`, `FATAL`, and `CRITICAL` patterns  
- ✅ Generates a detailed report with counts and log entries  
- ✅ Highlights files requiring immediate attention  

---

📂 Project Structure

├── analyse-log.sh # Main Bash script

├── application.log # Sample application log file

├── system.log # Sample system log file

---

## 🚀 How to Use

### 1️⃣ Clone the repository
```bash
git clone https://github.com/Abdulrahman787/Log-Analysis-Bash-Script.git
cd Log-Analysis-Bash-Scrip
```
2️⃣ Make the script executable
```
chmod +x analyse-log.sh
```
4️⃣ Check the generated report
The analysis results will be saved in:
```
/logs/log_analysis_report
```
🧪 Example Output
```
analysing log files
======================

list of log files updated in last 24 hours
/logs/application.log
/logs/system.log

==============================================
========Analysing /logs/application.log==========
Searching for error patterns in /logs/application.log
===============================================

Searching ERROR logs in /logs/application.log file
[2025-06-01 08:17:48] [ERROR] Payment gateway timeout after 30s for transaction TX78901234
[2025-06-01 08:25:48] [ERROR] Insufficient disk space for file upload
[2025-06-01 08:41:33] [ERROR] Invalid product code: PRD-404-NOTFOUND
[2025-06-01 08:55:19] [ERROR] Failed to update product #5678 - Database constraint violation
[2025-06-01 09:12:17] [ERROR] Analytics processing failed - Missing data for region EU-WEST
[2025-06-01 09:30:45] [ERROR] Health check failed for service: message-queue

Number of ERROR logs found in /media/sf_shared/logs/application.log
6

Searching FATAL logs in /logs/application.log file
[2025-06-01 08:47:22] [FATAL] Out of memory error in recommendation engine
[2025-06-01 09:25:33] [FATAL] Kernel panic on worker node worker-03

Number of FATAL logs found in /media/sf_shared/logs/application.log
2

Searching CRITICAL logs in /logs/application.log file
[2025-06-01 08:32:13] [CRITICAL] Database connection lost during backup
[2025-06-01 09:17:22] [CRITICAL] Security alert: Multiple failed login attempts for admin account

Number of CRITICAL logs found in /logs/application.log
2

==============================================
========Analysing /logs/system.log==========
Searching for error patterns in /logs/system.log
===============================================

Searching ERROR logs in /logs/system.log file
Jun  1 01:20:18 server-prod-01 sshd[23954]: [ERROR] Failed password for root from 198.51.100.23 port 63122 ssh2
Jun  1 01:20:19 server-prod-01 sshd[23954]: [ERROR] Failed password for root from 198.51.100.23 port 63122 ssh2
Jun  1 01:20:20 server-prod-01 sshd[23954]: [ERROR] Failed password for root from 198.51.100.23 port 63122 ssh2
Jun  1 01:45:03 server-prod-01 kernel: [49413.345678] [ERROR] JBD2: Detected IO errors while flushing file data on sda1-8
Jun  1 01:45:04 server-prod-01 kernel: [49414.456789] [ERROR] Buffer I/O error on device sda1, logical block 12345678
Jun  1 01:50:24 server-prod-01 kernel: [49734.109876] [ERROR] XFS (sdb1): Please unmount the filesystem and rectify the problem(s)
Jun  1 03:45:23 server-prod-01 mdadm[25134]: [ERROR] RebuildFinished event detected on md device /dev/md0, but rebuild failed
Jun  1 03:45:25 server-prod-01 kernel: [56725.567890] md/raid1:md0: [ERROR] sdc1: rescheduling sector 7654321 for read
Jun  1 03:45:26 server-prod-01 kernel: [56726.678901] md/raid1:md0: [ERROR] sdc1: read error at offset 7654321 on device sdc1
Jun  1 04:40:12 server-prod-01 kernel: [59412.345678] [ERROR] Memory failure: 0x00000000aa2b5000: recovery action unavailable
Jun  1 04:40:13 server-prod-01 kernel: [59413.456789] [ERROR] EDAC MC0: 1 CE memory read error on CPU_SrcID#0_MC#0_Chan#0_DIMM#0
Jun  1 04:40:16 server-prod-01 kernel: [59416.789012] [ERROR] EDAC MC0: 1 CE memory read error on CPU_SrcID#0_MC#0_Chan#0_DIMM#0

Number of ERROR logs found in /logs/system.log
12

Searching FATAL logs in /logs/system.log file
Jun  1 01:45:01 server-prod-01 kernel: [49411.123456] [FATAL] EXT4-fs error (device sda1): ext4_journal_check_start:56: Detected aborted journal
Jun  1 01:45:02 server-prod-01 kernel: [49412.234567] [FATAL] EXT4-fs (sda1): Remounting filesystem read-only
Jun  1 01:45:06 server-prod-01 smartd[1234]: [CRITICAL] Device: /dev/sda [SAT], failed SMART usage Attribute: Reallocated_Sector_Ct.
Jun  1 04:40:14 server-prod-01 kernel: [59414.567890] [CRITICAL] Hardware event. This is not a software error.
Jun  1 04:40:15 server-prod-01 kernel: [59415.678901] [CRITICAL] MCE: [Hardware Error]: CPU 0: Machine Check: 0 Bank 6: ee00000000800400
Jun  1 03:46:01 server-prod-01 smartd[1234]: [CRITICAL] Device: /dev/sdc [SAT], failed SMART usage Attribute: Raw_Read_Error_Rate.

Number of FATAL logs found in /logs/system.log
2

Searching CRITICAL logs in /logs/system.log file
Jun  1 01:20:21 server-prod-01 sshd[23954]: [CRITICAL] Disconnecting: Too many authentication failures for root from 198.51.100.23 port 63122 ssh2
Jun  1 03:46:01 server-prod-01 smartd[1234]: [CRITICAL] Device: /dev/sdc [SAT], failed SMART usage Attribute: Raw_Read_Error_Rate.
Jun  1 04:40:14 server-prod-01 kernel: [59414.567890] [CRITICAL] Hardware event. This is not a software error.
Jun  1 04:40:15 server-prod-01 kernel: [59415.678901] [CRITICAL] MCE: [Hardware Error]: CPU 0: Machine Check: 0 Bank 6: ee00000000800400

Number of CRITICAL logs found in /logs/system.log
4

Log analysis completed and report saved in: /logs/log_analysis_report

```
