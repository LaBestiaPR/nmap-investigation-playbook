```
███╗   ██╗███╗   ███╗ █████╗ ██████╗
████╗  ██║████╗ ████║██╔══██╗██╔══██╗
██╔██╗ ██║██╔████╔██║███████║██████╔╝
██║╚██╗██║██║╚██╔╝██║██╔══██║██╔═══╝
██║ ╚████║██║ ╚═╝ ██║██║  ██║██║
╚═╝  ╚═══╝╚═╝     ╚═╝╚═╝  ╚═╝╚═╝
  INVESTIGATION PLAYBOOK — FOR SECURITY ANALYSTS
```

<div align="center">

![Status](https://img.shields.io/badge/status-active-00ff41?style=for-the-badge&logo=hackthebox&logoColor=white)
![Level](https://img.shields.io/badge/level-SOC%20%7C%20Pentester-ff4757?style=for-the-badge&logo=kalilinux&logoColor=white)
![License](https://img.shields.io/badge/license-Educational-0a84ff?style=for-the-badge)
![Topic](https://img.shields.io/badge/topic-Network%20Recon-ffa502?style=for-the-badge&logo=wireshark&logoColor=white)

**A field-ready, analyst-grade playbook for conducting structured Nmap investigations.**  
*Built for SOC analysts, penetration testers, and digital forensics practitioners.*

</div>

---

## `> whoami`

This playbook was authored by **Andres Rafael Maldonado**  
Systems Engineer @ Oracle | B.S. CIS / Digital Forensics — DeVry University  
GitHub: [@LaBestiaPR](https://github.com/LaBestiaPR)

---

## `> cat overview.txt`

**Nmap** (Network Mapper) is the industry-standard open-source tool for network discovery and security auditing. Used by red teams, blue teams, and everyone in between — it reveals what's alive on a network, what ports are open, what services are running, and what vulnerabilities may be exposed.

This playbook operationalizes Nmap into a structured, repeatable investigation workflow — from initial host discovery all the way through service enumeration and reporting.

---

## `> ls -la contents/`

| Section | Description |
|---|---|
| **Host Discovery** | Ping sweeps, ARP scans, stealth techniques |
| **Port Scanning** | TCP SYN, UDP, full-connect, and targeted scans |
| **Service & Version Detection** | Banner grabbing, version fingerprinting (`-sV`) |
| **OS Detection** | Remote OS fingerprinting with `-O` |
| **NSE Scripts** | Leveraging the Nmap Scripting Engine for vuln detection |
| **Firewall Evasion** | Fragmentation, decoy scans, timing manipulation |
| **Output & Reporting** | Saving results in XML, grepable, and normal formats |
| **Investigation Workflows** | Tiered SOC use cases: triage → deep dive → escalation |

---

## `> nmap --help | grep "quick start"`

```bash
# Host Discovery — Who's alive?
nmap -sn 192.168.1.0/24

# Fast scan — Top 1000 ports
nmap -F 192.168.1.1

# Full TCP SYN scan + service/version detection
nmap -sS -sV -p- 192.168.1.1

# OS detection + aggressive mode
nmap -A -T4 192.168.1.1

# NSE vulnerability scripts
nmap --script vuln 192.168.1.1

# Save output (all formats)
nmap -oA scan_results 192.168.1.1
```

---

## `> cat use_cases.txt`

- **SOC Triage** — Rapidly scope an unknown asset or suspicious internal IP
- **Incident Response** — Map attacker foothold and lateral movement paths
- **Penetration Testing** — Enumerate targets during authorized engagements
- **Network Auditing** — Validate firewall rules and exposed service inventory
- **Threat Hunting** — Detect rogue devices and unexpected open ports

---

## `> cat scan_timing.txt`

| Flag | Template | Use Case |
|---|---|---|
| `-T0` | Paranoid | IDS evasion, extremely slow |
| `-T1` | Sneaky | Low-and-slow recon |
| `-T3` | Normal | Default balanced scan |
| `-T4` | Aggressive | Fast internal network scans |
| `-T5` | Insane | Maximum speed, noisy |

---

## `> cat disclaimer.txt`

> **AUTHORIZED USE ONLY.**  
> This playbook is intended strictly for **defensive security, authorized penetration testing, SOC operations, and educational purposes.**  
> Scanning networks or systems without explicit written permission is **illegal** and unethical.  
> Always obtain proper authorization before conducting any network investigation.  
> The author assumes no liability for misuse of this material.

---

## `> cat resources.txt`

- [Nmap Official Documentation](https://nmap.org/docs.html)
- [NSE Script Database](https://nmap.org/nsedoc/)
- [Nmap Cheat Sheet — StationX](https://www.stationx.net/nmap-cheat-sheet/)
- [SANS Nmap Reference Guide](https://www.sans.org)

---

<div align="center">

*Scan smart. Stay authorized. Document everything.*

`[ LaBestiaPR | Cybersecurity & Digital Forensics ]`

</div>
