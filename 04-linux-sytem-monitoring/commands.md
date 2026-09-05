# Day 4 – System Monitoring Notes

## 1. What is System Monitoring?

System monitoring means continuously checking the health and performance of a Linux system.

We mainly monitor:

```text
CPU
RAM
Disk
Processes
Load
Network
I/O
```

This is important for servers because problems such as high CPU, low memory or full disk can make applications slow or unavailable.

---

# 2. CPU Monitoring

## `nproc`

```bash
nproc
```

Shows the number of processing units available to Linux.

My output:

```text
2
```

Therefore, my Ubuntu VM has **2 available CPUs**.

---

## `lscpu`

```bash
lscpu
```

Displays detailed CPU information.

Important fields:

```text
Architecture
CPU(s)
Core(s) per socket
Thread(s) per core
Model name
Virtualization
```

My VM:

```text
Architecture: x86_64
CPU(s): 2
Core(s) per socket: 2
Thread(s) per core: 1
```

### Important

`lscpu` shows the CPU resources available **inside the virtual machine**.

It does not necessarily represent the total CPU resources of the physical computer.

---

# 3. Memory Monitoring

## `free -h`

```bash
free -h
```

Shows RAM and swap usage.

My output:

```text
Total:       3.3 GiB
Used:        1.2 GiB
Free:        225 MiB
Buff/cache:  2.1 GiB
Available:   2.1 GiB
Swap:        0 B
```

### Important terms

**Total**

Total RAM available to the VM.

**Used**

RAM currently being used by the system and applications.

**Free**

RAM that is completely unused.

**Buff/cache**

RAM used by Linux for buffers and filesystem cache.

**Available**

An estimate of RAM that can be given to applications without significant swapping.

### Important concept

Do not assume that low `free` memory means the system is running out of RAM.

Linux intentionally uses unused RAM for caching.

---

# 4. Disk Monitoring

## `df -h`

```bash
df -h
```

Shows filesystem disk usage.

My root filesystem:

```text
Size:  35G
Used:  9.1G
Avail: 24G
Use%:  29%
```

### Important

`/` is the root of the Linux filesystem.

Example:

```text
/
├── home
├── etc
├── var
├── usr
├── tmp
└── ...
```

My disk is currently only **29% used**, so there is plenty of available space.

---

# 5. Directory Size

## `du -sh`

```bash
du -sh
```

Shows the total size of the current directory.

Output:

```text
18M .
```

### Options

`-s`

Summary only.

`-h`

Human-readable format.

---

## Check home directory

```bash
du -sh ~
```

Output:

```text
18M /home/ubuntu
```

`~` represents the current user's home directory.

---

## Check project directory

```bash
du -sh linux-admin-lab
```

Output:

```text
448K linux-admin-lab
```

This means the Linux administration lab currently uses approximately **448 KB**.

---

# 6. Understanding `~`

Correct:

```bash
du -sh ~/linux-admin-lab
```

Incorrect:

```bash
du -sh ~linux-admin-lab
```

`~` represents the home directory.

For my Ubuntu user:

```text
~
↓
/home/ubuntu
```

Therefore:

```text
~/linux-admin-lab
```

means:

```text
/home/ubuntu/linux-admin-lab
```

---

# 7. System Uptime

## `uptime`

```bash
uptime
```

Example:

```text
11:19:16 up 20 min, 1 user, load average: 0.40, 0.23, 0.28
```

It provides:

* Current time
* System uptime
* Number of logged-in users
* Load average

---

# 8. Load Average

Example:

```text
load average: 0.40, 0.23, 0.28
```

These represent:

```text
0.40 → 1 minute
0.23 → 5 minutes
0.28 → 15 minutes
```

Load average represents the amount of work waiting for or using CPU and certain other system resources.

It is **not the same thing as CPU percentage**.

Since my VM has 2 CPUs and the load was well below 2, there was no indication of CPU saturation.

---

# 9. VMSTAT

## Command

```bash
vmstat 1 5
```

Meaning:

```text
1 → collect data every 1 second
5 → collect 5 samples
```

`vmstat` means **Virtual Memory Statistics**.

It provides information about:

```text
Processes
Memory
Swap
I/O
System activity
CPU
```

---

# 10. VMSTAT Important Columns

### Processes

```text
r
b
```

`r` = runnable processes.

`b` = blocked processes.

My blocked process value was:

```text
0
```

This is good.

---

### Swap

```text
swpd
si
so
```

`swpd` = swap memory used.

`si` = swap in.

`so` = swap out.

My values were:

```text
0
0
0
```

Therefore, there was no swap activity.

---

### Memory

```text
free
buff
cache
```

These show free memory, buffers and filesystem cache.

My cache was around:

```text
2 GB
```

This is normal Linux behavior.

---

### I/O

```text
bi
bo
```

`bi` = blocks read from storage.

`bo` = blocks written to storage.

There was some I/O activity in the first sample, but it quickly dropped to zero.

---

### CPU

```text
us
sy
id
wa
st
```

**us** = CPU time used by user processes.

**sy** = CPU time used by the kernel.

**id** = CPU idle time.

**wa** = time waiting for I/O.

**st** = CPU time stolen by the hypervisor.

My results showed:

```text
us: 1–4%
sy: 2–4%
id: 92–97%
wa: 0%
st: 0%
```

This indicates that the VM was mostly idle.

---

# 11. Overall Result

My Ubuntu VM was healthy during monitoring.

```text
CPU       → Healthy
RAM       → Healthy
Disk      → Healthy
Swap      → No swap activity
I/O Wait  → 0%
CPU Idle  → 92–97%
Blocked   → 0
```

---

# 12. Real Server Connection

These commands are important for backend and cloud engineering.

For example, if a Spring Boot application becomes slow:

```text
Application
     ↓
Check process
     ↓
Check CPU
     ↓
Check RAM
     ↓
Check disk
     ↓
Check I/O
     ↓
Check load
     ↓
Find bottleneck
```

Useful commands:

```bash
top
htop
free -h
df -h
uptime
vmstat
ps aux
```

These are basic tools used for diagnosing Linux server problems.

---

# 13. Key Commands to Remember

```bash
# CPU
nproc
lscpu

# Memory
free -h

# Disk
df -h
du -sh

# System load
uptime

# Virtual memory/system statistics
vmstat 1 5

# Processes
ps aux
top
htop
```

## Day 4 Status

```text
[x] CPU monitoring
[x] RAM monitoring
[x] Disk monitoring
[x] Directory monitoring
[x] Uptime
[x] Load average
[x] vmstat
[ ] top
[ ] htop
```

`top` and `htop` should still be practiced before considering Day 4 completely finished.

