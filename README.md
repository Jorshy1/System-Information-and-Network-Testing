# System Information and Network Testing

## Project Overview
This repository documents a baseline assessment of a Linux-based security environment's core system configurations and network connectivity metrics. [cite_start]It serves as a practical implementation of fundamental system administration commands, hardware resource analysis, and ICMP network diagnostics[cite: 20, 104].

---

## Tools & Environment
* [cite_start]**Operating System:** Kali Linux [cite: 32]
* [cite_start]**Linux Kernel:** Version `6.18.12-kali-amd64` [cite: 32]
* **Terminal Shell:** Standard Linux CLI

---

## [cite_start]Phase 1: System Information & Resources [cite: 20]

### 1. Environment Verification
[cite_start]The initial environment baseline setup confirms the active user context, local network identification, and the current working directory[cite: 7]:
* [cite_start]**User Identity (`whoami`):** `kali` [cite: 17]
* [cite_start]**Hostname:** `kali` [cite: 18]
* [cite_start]**Current Working Directory:** `/home/kali` [cite: 19]

### [cite_start]2. Hardware Resource Utilization [cite: 24]
[cite_start]Using standard Linux resource utilities (`free` and `df`), the system allocations were captured and verified[cite: 39, 67]:

| Resource Component | Allocated / Available Capacity | Metric Details |
| :--- | :--- | :--- |
| **System RAM** | [cite_start]~1.9 GiB (~2 GB) [cite: 94] | [cite_start]**Total Memory:** 1.9Gi [cite: 46] [cite_start]<br>**Used:** 890Mi [cite: 47] [cite_start]<br>**Free:** 228Mi [cite: 48] |
| **Main Partition Storage** | [cite_start]60 GB Available [cite: 95] | [cite_start]**Filesystem:** `/dev/sda1` [cite: 75] [cite_start]<br>**Total Size:** 79G [cite: 76] [cite_start]<br>**Available:** 60G [cite: 76] [cite_start]<br>**Use%:** 21% [cite: 87] |

---

## [cite_start]Phase 2: Network Connectivity Testing [cite: 104]

### [cite_start]1. DNS Diagnostics (Google Public DNS) [cite: 99]
[cite_start]A connection validation test was executed against the Google Public DNS target (`8.8.8.8`) to measure core routing response metrics[cite: 106, 113]:

* **Command Executed:** `ping 8.8.8.8`
* [cite_start]**Packet Loss:** 0% (2 packets transmitted, 2 received) [cite: 110, 115]
* [cite_start]**Round-Trip Time (RTT) Metrics:** [cite: 110]
  * [cite_start]**Minimum Latency:** 22.871 ms [cite: 111]
  * [cite_start]**Average Latency:** 25.477 ms [cite: 111, 114]
  * [cite_start]**Maximum Latency:** 28.063 ms [cite: 111]

### [cite_start]2. Domain Name Resolution & Restricted Latency Testing [cite: 117]
[cite_start]A secondary network utility check was initiated against a domain target (`google.com`) to verify active domain resolution alongside a explicit packet count threshold[cite: 124, 134]:

* **Command Executed:** `ping google.com`
* [cite_start]**Count Parameter Flag:** The command used restricted packet transmission metrics where a `-c 4` option dictates sending exactly 4 packets before stopping automatically[cite: 142].
* [cite_start]**Resolved Destination IP Address:** `142.250.139.139` [cite: 125, 135]
* [cite_start]**Packet Loss:** 0% (4 packets transmitted, 4 received) [cite: 131]
* [cite_start]**Round-Trip Time (RTT) Metrics:** [cite: 132]
  * [cite_start]**Minimum Latency:** 25.638 ms [cite: 132]
  * [cite_start]**Average Latency:** 29.101 ms [cite: 132, 137]
  * [cite_start]**Maximum Latency:** 32.914 ms [cite: 132]

### [cite_start]3. Diagnostic Metrics Comparison & Variance [cite: 136]
[cite_start]The diagnostic data collected indicates an incremental response disparity between the raw IP target and the domain target[cite: 139]:
* [cite_start]**Google DNS (`8.8.8.8`) Latency Average:** ~25.477 ms [cite: 138]
* [cite_start]**Google Domain (`google.com`) Latency Average:** ~29.101 ms [cite: 137]

**Analysis of Variance:**
[cite_start]The operational time differences between these tests are normal behaviors in active environments[cite: 140]. [cite_start]The latency variations stem primarily from dynamic network routing patterns, distributed destination server loads, and distinct physical distances between the source terminal and individual infrastructure nodes[cite: 141].

---

## Core System Utilities Documented
* `whoami` - Print the effective username of the current user.
* `hostname` - Show or set the system's host name.
* `pwd` - Return working directory name.
* `uname` - Print system information and kernel details.
* `free` - Display amount of free and used memory in the system.
* `df` - Report file system disk space usage.
* `ping` - Send ICMP ECHO_REQUEST to network hosts to test connectivity.

For detailed step-by-step instructions on how the original project, please refer to the deployment guide:

https://drive.google.com/file/d/1YY4rcdS2wlv2vNj-f0aiAIemyi0JleGv/view?usp=sharing

```
