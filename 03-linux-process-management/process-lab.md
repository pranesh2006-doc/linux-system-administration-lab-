# Process Management Lab

## Task 1 - View Processes

Command:
ps

Observation:
...

## Task 2 - Detailed Process Information

Command:
ps aux

Observation:
...

## Task 3 - Background Process

Command:
sleep 300 &

PID:
...

## Task 4 - Stop and Resume

Commands:
Ctrl + Z
bg
fg

Observation:
...

## Task 5 - Process Signals

Commands:
kill -STOP PID
kill -CONT PID
kill PID
kill -9 PID

Observation:
...

## Task 6 - Process Priority

Commands:
ps -o pid,ni,comm -p PID
renice -n 10 -p PID

Observation:
...
