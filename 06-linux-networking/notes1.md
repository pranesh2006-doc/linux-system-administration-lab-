# DAY 6 — Linux Networking

## 1. Check Network Interfaces

Command:

```bash
ip link
```

Purpose:

Shows network interfaces available on the Linux machine.

Important interfaces:

```text
lo → Loopback
eth0 / enp0s3 → Network interface
wlan0 → Wi-Fi interface on some systems
```

---

## 2. Check IP Address

Command:

```bash
ip addr
```

Purpose:

Shows interfaces and their assigned IP addresses.

My active interface:

```text
Write your interface here
```

My IP address:

```text
Write your IP here
```

---

## 3. Check IP Quickly

Command:

```bash
hostname -I
```

Purpose:

Displays IP addresses assigned to the machine.

My result:

```text
Write your result here
```

---

## 4. Check Routing Table

Command:

```bash
ip route
```

Purpose:

Shows how Linux decides where to send network traffic.

My default gateway:

```text
Write your gateway here
```

---

## 5. Test Internet Connectivity

Command:

```bash
ping -c 4 8.8.8.8
```

Purpose:

Tests network connectivity to a public IP address.

Result:

```text
Write your result here
```

---

## 6. Test DNS + Connectivity

Command:

```bash
ping -c 4 google.com
```

Purpose:

Tests DNS resolution and network connectivity.

Result:

```text
Write your result here
```

---

## 7. Test HTTP/HTTPS

Command:

```bash
curl https://example.com
```

Purpose:

Sends an HTTP/HTTPS request and displays the server response.

Result:

```text
Write what you observed here
```

---

# Key Understanding

```text
Your Ubuntu
     ↓
Network Interface
     ↓
IP Address
     ↓
Gateway
     ↓
Internet
```

DNS converts:

```text
Domain Name → IP Address
```

Example:

```text
google.com → IP address
```

