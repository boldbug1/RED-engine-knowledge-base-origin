# 💻 Computers: Knowledge Base

> Everything you actually need to know, without the fluff.

---

## How a Computer Works (The Short Version)

A computer is fundamentally a machine that reads instructions and processes data.

```
Input → CPU processes → Output
           ↑
         RAM (working memory)
           ↑
        Storage (long-term memory)
```

| Component | Role | Analogy |
|---|---|---|
| **CPU** | Executes instructions | Brain |
| **RAM** | Holds active data | Desk |
| **Storage (SSD/HDD)** | Stores data long-term | Filing cabinet |
| **GPU** | Parallel processing, graphics/AI | Math co-processor |
| **Motherboard** | Connects everything | Nervous system |
| **PSU** | Supplies power | Heart |

---

## Operating Systems

An OS manages hardware and provides an environment for software to run.

- **Windows** — Dominant in consumer and enterprise desktop. Broad software compatibility.
- **macOS** — Unix-based, Apple hardware only. Excellent developer and creative tooling.
- **Linux** — Open-source, highly customizable. Dominant in servers, cloud, and embedded systems.
- **Android / iOS** — Mobile OS variants (Linux-based and Unix-based respectively).

**Kernel:** The core of an OS. Manages memory, processes, and hardware communication. Everything else is built on top of it.

---

## Networking Fundamentals

**IP Address:** A unique identifier for a device on a network. Like a postal address.
- IPv4: `192.168.1.1` (running out of space)
- IPv6: `2001:db8::1` (virtually unlimited)

**DNS:** Domain Name System — translates `google.com` into an IP address. The internet's phone book.

**TCP/IP:** The foundational protocol suite of the internet.
- **TCP** — Reliable, ordered delivery (websites, file transfers)
- **UDP** — Fast, unordered delivery (video calls, games)

**Ports:** Virtual doors on a device. Common examples:
- `80` — HTTP
- `443` — HTTPS
- `22` — SSH
- `3306` — MySQL

**LAN vs WAN:**
- LAN (Local Area Network) — your home/office network
- WAN (Wide Area Network) — the internet

---

## File Systems

How operating systems organize data on storage.

| File System | OS | Notes |
|---|---|---|
| NTFS | Windows | Supports large files, permissions |
| ext4 | Linux | Fast, journaled, default on most distros |
| APFS | macOS | Optimized for SSDs |
| FAT32 | Universal | Max 4GB file size, used on USB drives |
| exFAT | Universal | FAT32 successor, no 4GB limit |

---

## Command Line Essentials

**Linux/macOS (Bash/Zsh):**

```bash
ls -la          # List files with details
cd /path        # Change directory
pwd             # Print working directory
cp src dst      # Copy file
mv src dst      # Move / rename
rm -rf dir/     # Delete directory (dangerous — no undo)
cat file.txt    # Print file contents
grep "term" f   # Search text in file
chmod +x file   # Make file executable
sudo command    # Run as superuser
ssh user@host   # Connect to remote machine
```

**Windows (PowerShell):**

```powershell
Get-ChildItem      # List files
Set-Location       # Change directory
Copy-Item          # Copy file
Move-Item          # Move/rename
Remove-Item -Recurse  # Delete directory
Get-Content        # Print file
Select-String      # Search text
```

---

## Security Basics

- **Use a password manager.** Reusing passwords is how accounts get compromised.
- **Enable 2FA** everywhere you can. Authenticator app > SMS.
- **Keep software updated.** Most successful attacks exploit known, patched vulnerabilities.
- **Principle of Least Privilege:** Only give software/users the permissions they need.
- **Encrypt your disk.** BitLocker (Windows), FileVault (macOS), LUKS (Linux).
- **Phishing** is still the #1 attack vector. Verify before you click.

---

## Performance Bottlenecks

When a computer is slow, the culprit is almost always one of:

1. **CPU** — Maxed out on a task (check Task Manager / `htop`)
2. **RAM** — Not enough, causing swap (paging to disk)
3. **Storage I/O** — Slow HDD or full SSD (SSDs degrade when near capacity)
4. **Network** — High latency or low bandwidth

**Upgrade priority:** SSD > RAM > CPU for most common bottlenecks.

---

## Data Storage Hierarchy (Speed vs. Cost)

```
Registers (CPU)    → Nanoseconds, bytes
CPU Cache (L1-L3)  → Nanoseconds, MB
RAM                → ~100ns, GBs
SSD (NVMe)         → Microseconds, TBs
HDD                → Milliseconds, TBs
Cloud/Tape         → Seconds/minutes, unlimited
```

Moving data between these levels is often where performance is won or lost.

---

## Virtualization & Containers

- **Virtual Machine (VM):** Full OS running inside another OS. Isolated, resource-heavy.
- **Container (Docker):** Shares the host kernel, just isolates the process environment. Lightweight and fast.
- **Hypervisor:** Software that runs VMs (e.g., VMware, Hyper-V, KVM).

**Use case:** Containers dominate modern deployment (cloud, microservices). VMs dominate security isolation and legacy compatibility.

---

## Binary & Hexadecimal

Computers think in binary (base-2). Humans use hex (base-16) as a shorthand.

```
Binary:   0000 0001 0010 0011 0100 0101 0110 0111
Decimal:  0    1    2    3    4    5    6    7
Hex:      0    1    2    3    4    5    6    7

Binary:   1000 1001 1010 1011 1100 1101 1110 1111
Decimal:  8    9    10   11   12   13   14   15
Hex:      8    9    A    B    C    D    E    F
```

1 byte = 8 bits. `0xFF` in hex = `255` in decimal = `11111111` in binary.

---

*Computers aren't magic. They're just really fast at following simple instructions.*
