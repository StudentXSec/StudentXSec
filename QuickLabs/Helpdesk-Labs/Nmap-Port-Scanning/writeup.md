# QuickLab: Nmap Port Scanning (Helpdesk)

**Source:** TCM Helpdesk optional lab  
**Date Completed:** 2025-09-20  
**Difficulty:** Beginner — Recon / Sysadmin fundamentals  
**Tools Used:** `nmap` (Ubuntu VM)

---

## 🎯 Objective
Perform authorized reconnaissance using `nmap` against a sanctioned test host (`scanme.nmap.org`), capture raw outputs and screenshots, and document results as part of a Vulnerability Management workflow.

---

## 🛠 Environment
- Target (authorized): `scanme.nmap.org`  
- VM: Ubuntu (VirtualBox on Windows host)  
- Repo paths used in this lab:
  - `raw-data/` — raw `.nmap/.txt/.xml/.gnmap` outputs  
  - `screenshots/` — terminal screenshots

---

## 🔢 Commands I ran
1. Install nmap:
`bash
sudo apt update
sudo apt install -y nmap`

2. Quick/basic sanity scan:
`bash
nmap -v scanme.nmap.org`
(Screenshot: ./screenshots/nmap-basic-scan.png)

3. Aggressive all-ports archival scan:
`bash
nmap --stats-every 10s -p- -A -T4 scanme.nmap.org -oA raw-data/scanme_nmap_A-full`
(Raw outputs: raw-data/scanme_nmap_A-full.nmap, raw-data/scanme_nmap_A-full.xml, raw-data/scanme_nmap_A-full.gnmap)
(Screenshot: ./screenshots/nmap-aggressive-output.png)

4. Stealth SYN scan (saved output used in this writeup):
`bash
sudo nmap -sS -p- -T4 scanme.nmap.org -oN raw-data/scanme_nmap_syn.txt`
(Screenshot: ./screenshots/nmap-stealth-final.png)

---

## 🔎 Results (stealth scan)
Nmap scan report for scanme.nmap.org (45.33.32.156)
Host is up (0.0013s latency).
Other addresses for scanme.nmap.org (not scanned): 2600:3c01::f03c:91ff:fe18:bb2f
Not shown: 50202 filtered tcp ports (no-response), 15329 closed tcp ports (reset)
PORT      STATE SERVICE
22/tcp    open  ssh
80/tcp    open  http
9929/tcp  open  nping-echo
31337/tcp open  Elite

Nmap done: 1 IP address (1 host up) scanned in 6138.92 seconds

---

## Summary (recruiter-friendly):

Open ports discovered: 22 (SSH), 80 (HTTP), 9929 (nping-echo), 31337 (Elite).

Scan runtime: 6138.92 seconds (≈102 minutes) for the full SYN scan.

Host latency: 0.0013s, host is reachable.

Many TCP ports were filtered or closed (see raw output); only the above services responded.

✍️ Key takeaways

This QuickLab documents ethical reconnaissance using nmap on an authorized test host. Saving raw outputs and screenshots produces reproducible evidence and demonstrates an end-to-end reconnaissance step in a Vulnerability Management workflow (Recon → Scan → Analyze → Remediate).
