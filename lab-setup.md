# Lab Setup

My learning environment for the zero-to-job-ready cybersecurity roadmap.

## Hardware & host OS
- Laptop running Windows
- 8 GB RAM
- Intel CPU with Virtualization Technology (VT-x) enabled in BIOS

## Linux environment
- **WSL2** with **Ubuntu** as my primary Linux terminal
- Username: harustotle
- Verified working with `whoami` and `ls /`

## Why this setup
With 8 GB of RAM, running a full attacker VM and a target VM at the same time
isn't practical, so I use WSL2 (a real Linux terminal inside Windows with very
little overhead) plus browser-based labs where the target machine is hosted
for me (PortSwigger, TryHackMe). This keeps the local footprint light.

## Tools installed / planned
- [x] WSL2 + Ubuntu
- [x] GitHub account + this repository
- [ ] VirtualBox (one lightweight VM, optional)
- [ ] Wireshark (Week 3)

## Setup notes / troubleshooting log
Getting WSL working was a real fight, and documenting it counts as a skill:
1. `wsl --install` installed the WSL components but the Ubuntu download failed
   with error `0x80072ee7` (a name-resolution / network error).
2. Confirmed internet and DNS were fine using `ping 8.8.8.8` and
   `ping google.com`.
3. Discovered I was running the older built-in version of WSL, which didn't
   support newer download options.
4. Installed the **Ubuntu** app from the Microsoft Store instead, which
   downloaded successfully.
5. First launch failed with error `0x80370102` — virtualization was disabled.
6. Enabled **Virtualization Technology (VT-x)** in the BIOS, saved, and rebooted.
7. Relaunched Ubuntu, created my user account, and confirmed a working Linux
   terminal.

## First concepts I picked up during setup
- Linux is **case-sensitive and space-sensitive**: `ls /` works, `Is/` does not.
- I run as a normal user by default, not `root` — `sudo` grants temporary admin
  rights. Running as non-root by default is a deliberate security design.
