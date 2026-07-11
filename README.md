# SOC Home Lab

A personal Security Operations Center lab simulating real-world attack
and detection scenarios using industry-standard tools.

## Lab Environment

| Machine | OS | IP | Role |
|---------|----|----|------|
| Host | Windows 10 | — | Hypervisor |
| Attacker | Kali Linux | 192.168.65.3 | Analyst machine |
| Target | Ubuntu | 192.168.65.4 | Target server |

## Tools Used

- **Nmap** — network reconnaissance and asset discovery
- **Nessus** — vulnerability scanning and assessment
- **Hydra** — SSH brute force simulation
- **Metasploit** — service fingerprinting
- **Nikto** — web server vulnerability scanning
- **Wireshark** — network traffic capture and analysis
- **Splunk** — SIEM, log ingestion and detection (in progress)

## Project Phases

### Phase 1 — Asset Discovery ✅
- Nmap scan identified open ports 22 (SSH) and 80 (HTTP)
- OS fingerprinted as Ubuntu Linux
- Aggressive scan revealed service versions

### Phase 2 — Vulnerability Assessment ✅
- Nessus identified 24 Low severity vulnerabilities
- SSH and HTTP confirmed as attack surface
- Raw scan results saved as .nessus file

### Phase 3 — Attack Simulation ✅
- Hydra SSH brute force — 29 attempts recorded in auth.log
- Metasploit fingerprinted OpenSSH service version
- Nikto scanned Apache2 for misconfigurations
- All traffic captured via Wireshark pcap

### Phase 4 — Detection and Alerting (in progress) ⏳
- Ubuntu auth.log ingested into Splunk SIEM
- Brute force attempts detected via log analysis
- Dashboard under construction

## Key Findings

- SSH brute force attack generated 29 failed login attempts
- All attempts logged and detectable in auth.log
- Attacker IP 192.168.65.3 identifiable via SIEM analysis
- No credentials compromised during simulation

## Evidence Files
