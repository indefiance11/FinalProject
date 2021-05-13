# Blue Team: Summary of Operations

## Table of Contents
- Network Topology
- Description of Targets
- Monitoring the Targets
- Patterns of Traffic & Behavior
- Suggestions for Going Further

### Network Topology
_TODO: Fill out the information below._

The following machines were identified on the network:
- Capstone
  - **Operating System**: 
  - **Purpose**:
  - **IP Address**: 192.168.1.100
- ELK
  - **Operating System**:Ubuntu
  - **Purpose**:ELK Server
  - **IP Address**:192.168.1.105
- Kali
  - **Operating System**:KALI Linux
  - **Purpose**:Pentesting machine
  - **IP Address**:192.168.1.90
- Target 1
  - **Operating System**:Debian 
  - **Purpose**: Target Machine for Pentesting
  - **IP Address**:192.168.1.110
- Target 2
  - **Operating System**:Debian 
  - **Purpose**:Target Machin for Pentesting
  - **IP Address**:192.168.1.105

### Description of Targets
_TODO: Answer the questions below._

The target of this attack was: `Target 1` 192.168.1.110

Target 1 is an Apache web server and has SSH enabled, so ports 80 and 22 are possible ports of entry for attackers. As such, the following alerts have been implemented:

### Monitoring the Targets

Traffic to these services should be carefully monitored. To this end, we have implemented the alerts below:

#### CPU Usage Monitor


Alert 1 is implemented as follows:
  - **Metric**: system.process.cpu.total.pct
  - **Threshold**: > 0.5
  - **Vulnerability Mitigated**: no
  - **Reliability**: medium

#### Excessive http Errors

Alert 2 is implemented as follows:
  - **Metric**: http.response.status_code
  - **Threshold**: > 400 for last 5 minutes
  - **Vulnerability Mitigated**: unknown
  - **Reliability**: no false positives and a high reliability

#### http Request Type Monitor

Alert 3 is implemented as follows:
  - **Metric**: http.request.bytes
  - **Threshold**: > 3500 for the last minute
  - **Vulnerability Mitigated**: unknown
  - **Reliability**: low

_TODO Note: Explain at least 3 alerts. Add more if time allows._

### Suggestions for Going Further (Optional)
_TODO_: 
- Each alert above pertains to a specific vulnerability/exploit. Recall that alerts only detect malicious behavior, but do not stop it. For each vulnerability/exploit identified by the alerts above, suggest a patch. E.g., implementing a blocklist is an effective tactic against brute-force attacks. It is not necessary to explain _how_ to implement each patch.

The logs and alerts generated during the assessment suggest that this network is susceptible to several active threats, identified by the alerts above. In addition to watching for occurrences of such threats, the network should be hardened against them. The Blue Team suggests that IT implement the fixes below to protect the network:
- Vulnerability 1
  - **Patch**: TODO: E.g., _install `special-security-package` with `apt-get`_
  - **Why It Works**: TODO: E.g., _`special-security-package` scans the system for viruses every day_
- Vulnerability 2
  - **Patch**: TODO: E.g., _install `special-security-package` with `apt-get`_
  - **Why It Works**: TODO: E.g., _`special-security-package` scans the system for viruses every day_
- Vulnerability 3
  - **Patch**: TODO: E.g., _install `special-security-package` with `apt-get`_
  - **Why It Works**: TODO: E.g., _`special-security-package` scans the system for viruses every day_
