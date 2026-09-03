# Day 4 – System Monitoring

## 🎯 Objective

Learn how to monitor the health and performance of a Linux system.

The main areas monitored are:

* CPU
* Memory (RAM)
* Disk
* Processes
* System load
* Virtual memory
* System uptime

---

## 🖥️ Commands Practiced

| Command      | Purpose                                   |
| ------------ | ----------------------------------------- |
| `nproc`      | Shows number of available CPUs            |
| `lscpu`      | Displays detailed CPU information         |
| `free -h`    | Shows RAM and swap usage                  |
| `df -h`      | Shows filesystem/disk usage               |
| `du -sh`     | Shows directory size                      |
| `uptime`     | Shows system uptime and load average      |
| `vmstat 1 5` | Monitors processes, memory, I/O and CPU   |
| `top`        | Real-time process and resource monitoring |
| `htop`       | Interactive process monitoring            |

---

## 🔍 System Information

### CPU

```bash
nproc
lscpu
```

The Ubuntu VM has:

* **2 CPUs**
* Architecture: **x86_64**
* CPU: **AMD Ryzen 5 7520U**
* Virtualization: **KVM**

---

### Memory

```bash
free -h
```

Observed:

* Total RAM: approximately **3.3 GiB**
* Used: approximately **1.2 GiB**
* Available: approximately **2.1 GiB**
* Swap: **0 B**

The available memory is healthy. Linux uses RAM for caching, so low `free` memory alone does not necessarily indicate a problem.

---

### Disk

```bash
df -h
```

Root filesystem:

* Total: **35 GB**
* Used: **9.1 GB**
* Available: **24 GB**
* Usage: **29%**

Disk usage is currently healthy.

---

### Directory Usage

```bash
du -sh ~
du -sh linux-admin-lab
```

Observed:

* Home directory: approximately **18 MB**
* `linux-admin-lab`: approximately **448 KB**

---

### System Uptime

```bash
uptime
```

Example output:

```text
11:19:16 up 20 min, 1 user, load average: 0.40, 0.23, 0.28
```

The system had been running for approximately 20 minutes.

Since the VM has 2 CPUs, the load averages were low and did not indicate CPU saturation.

---

### Virtual Memory Statistics

```bash
vmstat 1 5
```

Important observations:

* Swap usage: **0**
* Swap in/out: **0**
* Blocked processes: **0**
* CPU idle: approximately **92–97%**
* I/O wait: **0%**

This indicates that the system was mostly idle and healthy during the monitoring period.

---

## 📊 Overall System Health

| Resource          | Status                 |
| ----------------- | ---------------------- |
| CPU               | 🟢 Healthy             |
| RAM               | 🟢 Healthy             |
| Disk              | 🟢 Healthy             |
| Swap              | 🟢 Not configured/used |
| CPU Idle          | 🟢 High                |
| I/O Wait          | 🟢 0%                  |
| Blocked Processes | 🟢 0                   |

---

## 🧠 What I Learned

* How to check CPU resources.
* How Linux manages RAM and cache.
* How to monitor disk usage.
* How to understand system load average.
* How to inspect running processes.
* How to monitor virtual memory and I/O.
* How to identify basic server health problems.

---

## 🚀 Next Step

Next I will learn **Disk Management**, including:

```bash
lsblk
df -h
du -sh
mount
umount
```

and understand disks, partitions, filesystems and mount points.

