# DAY 7 — Network Troubleshooting

## 1. Check Connectivity

```bash
ping -c 4 google.com
```

Purpose:

Tests network connectivity and DNS resolution.

---

## 2. Test HTTP

```bash
curl https://example.com
```

Purpose:

Tests whether an HTTP/HTTPS server responds.

---

## 3. Check DNS

```bash
nslookup google.com
```

Purpose:

Finds the IP address associated with a domain name.

Result:

```text
Write your result here
```

---

## 4. Detailed DNS Information

```bash
dig google.com
```

Purpose:

Provides detailed DNS information.

Short version:

```bash
dig google.com +short
```

Result:

```text
Write your result here
```

---

## 5. Check Listening Ports

```bash
ss -tuln
```

Purpose:

Shows TCP and UDP listening sockets.

Important options:

```text
-t → TCP
-u → UDP
-l → Listening
-n → Numeric
```

Ports I found:

```text
Write your ports here
```

---

## 6. Find Processes Using Ports

```bash
sudo ss -tulpn
```

Purpose:

Shows listening ports and the processes using them.

Example:

```text
Port 8080
   ↓
Java
   ↓
Spring Boot
```

---

# Network Troubleshooting Model

```text
DNS
 ↓
IP
 ↓
Port
 ↓
Process
 ↓
Application
```

## Spring Boot Example

```text
localhost:8080
      ↓
127.0.0.1
      ↓
Port 8080
      ↓
Java
      ↓
Spring Boot
```

## What I Learned

1. Write your learning here.
2. Write your learning here.
3. Write your learning here.

