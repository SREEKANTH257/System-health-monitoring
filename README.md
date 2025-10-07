# System Monitoring Task

# Overview
This project is a **system-administration task** built for the [Terminal-Bench](https://github.com/laude-institute/terminal-bench) environment.  
It periodically logs system resource usage, detects large files, and records key health metrics in a single log file.

---

# Task Description
The script:
- Logs **memory usage**, **CPU consumption**, and **disk utilization** every few seconds.
- Detects **large files (>100 MB)** under the home directory.
- Records all information with timestamps into a single log file.

# Default Configuration
| Parameter   | Value | Description |
|--------------|--------|-------------|
| `LOGFILE`    | `$HOME/system_monitorr.log` | Output log file |
| `INTERVAL`   | `15s` | Time between each sample |
| `DURATION`   | `45s` | Total monitoring duration |
| `ITERATIONS` | `3`   | Automatically calculated from duration / interval |

---

# File Structure
terminal-bench/
├── tasks/
│ └── system-monitoring/
│ ├── task.yaml # Task metadata for Terminal-Bench
│ ├── solution.sh # Main system monitoring script
│ ├── run-tests.sh # Executes pytest-based validation
│ ├── Dockerfile # Container environment setup
│ └── tests/
│ └── test_outputs.py # Pytest validation file

# Example Log Output
=== System Monitoring Started at Mon Oct 6 22:10:12 IST 2025 ===

===== Timestamp: Mon Oct 6 22:10:12 IST 2025 =====
---- Top 5 Memory Consuming Processes ----
PID   COMMAND   %MEM   %CPU
1234  firefox   10.5   15.3
...

---- Large Files (>100MB) in Home Directory ----
-rw-r--r-- 1 user user 120M Oct 6 21:59 /home/user/Downloads/video.mp4

---- Disk Usage ----
Filesystem      Size  Used  Avail  Use%  Mounted on
/dev/sda1        60G   40G    20G   67%  /

