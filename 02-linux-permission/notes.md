# Day 2 — Users & Permissions

## Topics Learned

- Linux users
- Linux groups
- File ownership
- File permissions
- Read (r)
- Write (w)
- Execute (x)
- sudo
- chmod
- chown
- chgrp

## Permission Structure

-rwxr-xr--

Owner  → rwx
Group  → r-x
Others → r--

## Permission Values

r = 4
w = 2
x = 1

## Common Permissions

600 → Owner can read/write only
644 → Owner read/write, others read
755 → Owner full access, others read/execute
