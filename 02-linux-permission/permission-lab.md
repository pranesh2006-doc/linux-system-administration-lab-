# Permissions Lab

## chmod 600

Command:

chmod 600 permission-test/file.txt

Result:

-rw-------

Owner → rw-
Group → ---
Others → ---

---

## chmod 644

Command:

chmod 644 permission-test/file.txt

Result:

-rw-r--r--

Owner → rw-
Group → r--
Others → r--

---

## chmod 755

Command:

chmod 755 permission-test/file.txt

Result:

-rwxr-xr-x

Owner → rwx
Group → r-x
Others → r-x
