# Process Management - Notes

## 1. What is a Process?

A **process** is a program that is currently running.

Example:

```bash
sleep 300
```

Here, `sleep` is a program and its running instance is a process.

---

## 2. PID

PID means **Process ID**.

Linux assigns a unique number to every running process.

Find a process PID:

```bash
pgrep sleep
```

---

## 3. Process Monitoring

### ps

```bash
ps
```

Displays processes associated with the current terminal.

### ps aux

```bash
ps aux
```

Displays detailed information about running processes.

Important columns:

* `USER` → Process owner
* `PID` → Process ID
* `%CPU` → CPU usage
* `%MEM` → Memory usage
* `COMMAND` → Command that started the process

### top

```bash
top
```

Provides a live view of running processes.

### htop

```bash
htop
```

Provides an interactive process-monitoring interface.

---

## 4. Foreground Process

A foreground process runs directly in the terminal and occupies the terminal.

Example:

```bash
sleep 300
```

The terminal cannot be used for another command until the process finishes or is stopped.

---

## 5. Background Process

A background process runs without blocking the terminal.

Use `&`:

```bash
sleep 300 &
```

Check background jobs:

```bash
jobs
```

---

## 6. Stop a Process

### Using Ctrl + Z

For a foreground process:

```text
Ctrl + Z
```

This temporarily stops the process.

### Using SIGSTOP

```bash
kill -STOP PID
```

The process is paused but still exists.

---

## 7. Resume a Process

### Resume in background

```bash
bg %1
```

### Resume in foreground

```bash
fg %1
```

### Using SIGCONT

```bash
kill -CONT PID
```

This resumes a process that was stopped.

---

## 8. Terminate a Process

### Normal termination

```bash
kill PID
```

Normally sends `SIGTERM` (signal 15).

It asks the process to terminate gracefully.

### Forceful termination

```bash
kill -9 PID
```

Sends `SIGKILL` (signal 9).

It forcefully terminates the process.

---

## 9. Important Signals

| Signal    | Number | Purpose            |
| --------- | -----: | ------------------ |
| `SIGINT`  |      2 | Interrupt          |
| `SIGKILL` |      9 | Force termination  |
| `SIGTERM` |     15 | Normal termination |
| `SIGSTOP` |     19 | Stop/pause         |
| `SIGCONT` |     18 | Continue/resume    |

Examples:

```bash
kill PID
kill -9 PID
kill -STOP PID
kill -CONT PID
```

`Ctrl + C` normally sends `SIGINT`.

---

## 10. Nice Value

A **nice value** influences the CPU scheduling priority of a process.

Range:

```text
-20 → Highest priority
  0 → Normal priority
+19 → Lowest priority
```

Remember:

> Lower nice value = Higher priority

> Higher nice value = Lower priority

---

## 11. Checking Nice Value

```bash
ps -o pid,ni,comm -p PID
```

Example:

```text
PID   NI   COMMAND
1234   0   sleep
```

`NI` means **Nice value**.

---

## 12. renice

`renice` changes the nice value of an already-running process.

Syntax:

```bash
renice -n VALUE -p PID
```

Example:

```bash
renice -n 10 -p 1234
```

This sets the nice value of process `1234` to `10`, giving it lower scheduling priority.

To increase priority:

```bash
sudo renice -n -10 -p 1234
```

Negative nice values generally require administrator privileges.

---

## 13. nice vs renice

### nice

Used when starting a process:

```bash
nice -n 10 command
```

### renice

Used to change the priority of an already-running process:

```bash
renice -n 10 -p PID
```

Simple difference:

```text
nice
 ↓
Start process with priority

renice
 ↓
Change priority of running process
```

---

## 14. Process Management Flow

```text
Start Process
     ↓
Running
     ↓
STOP ───────→ Paused
     ↑           ↓
     └── CONT ───┘
     ↓
Running
     ↓
TERM / KILL
     ↓
Terminated
```

## Key Learning

Process management allows a Linux administrator to monitor processes, control their execution, terminate unwanted processes, and adjust their CPU scheduling priority.

