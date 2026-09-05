# Linux Networking Lab

## Objective

Learn and practice basic Linux networking and network troubleshooting commands.

## Topics

* IP Address
* MAC Address
* Network Interface
* Loopback
* Gateway
* DNS
* Ports
* TCP
* UDP
* HTTP
* Network Troubleshooting

## Day 6 Commands

```bash
ip addr
ip link
hostname -I
ip route
ping -c 4 8.8.8.8
ping -c 4 google.com
curl https://example.com
```

## Day 7 Commands

```bash
ping
curl
ss
nslookup
dig
```

## Important Concept

```text
Domain
   ↓
DNS
   ↓
IP Address
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
Java Process
      ↓
Spring Boot
```

## Goal

Understand how Linux communicates with other machines and how to troubleshoot networking problems before deploying Spring Boot applications to AWS.

