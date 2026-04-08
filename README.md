<div align="center">

<a href="https://github.com/notfawadmir">
  <img src="https://capsule-render.vercel.app/api?type=venom&color=0:0d1117,50:001a0d,100:0d1117&height=220&section=header&text=FAWAD%20AHMED%20MIR&fontSize=52&fontColor=00ff41&fontAlignY=55&desc=Self-Taught%20Penetration%20Tester%20%7C%20Offensive%20Security%20%7C%20Red%20Team%20Tooling&descSize=16&descAlignY=75&descColor=4af626&animation=twinkling&stroke=00ff41&strokeWidth=1" alt="Header" width="100%"/>
</a>

<a href="https://git.io/typing-svg">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=700&size=20&pause=1000&color=00FF41&center=true&vCenter=true&random=false&width=650&lines=%24+whoami+--+self-taught+penetration+tester;%24+nmap+-sV+-sC+--script+vuln+target.lab;%24+msfconsole+-q+-x+%22use+exploit%2Fmulti%2Fhandler%22;%24+sqlmap+-u+target+--dbs+--batch;%24+gobuster+dir+-u+http%3A%2F%2Ftarget+-w+big.txt;Built+custom+labs.+Broke+them.+Fixed+them." alt="Typing SVG" />
</a>

<br/><br/>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Fawad_Mir-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/fawad-ahmed-mir/)
[![Medium](https://img.shields.io/badge/Medium-Writeups-12100E?style=flat-square&logo=medium&logoColor=white)](https://medium.com/@fawadmeer000)
[![Email](https://img.shields.io/badge/Email-fawadmeer000@gmail.com-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:fawadmeer000@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-notfawadmir-181717?style=flat-square&logo=github&logoColor=00ff41)](https://github.com/notfawadmir)
[![Profile Views](https://komarev.com/ghpvc/?username=notfawadmir&color=00ff41&style=flat-square&label=PROFILE+VIEWS)](https://github.com/notfawadmir)

</div>

---

```
┌──────────────────────────────────────────────────────────────────────┐
│  $ ./fawad --init                                                    │
│                                                                      │
│  [+] Loading profile...                                              │
│  [+] Self-taught pentester detected — no hand-holding, no degrees   │
│  [+] Custom home lab: ONLINE                                         │
│  [+] Offensive tools: LOADED                                         │
│  [+] Ethics module: ACTIVE                                           │
│  [*] Status: Ready to break things responsibly.                      │
└──────────────────────────────────────────────────────────────────────┘
```

<br/>

## `$ whoami`

I'm **Fawad Ahmed Mir** — a **self-taught penetration tester and security researcher** from Pakistan who learned by doing, not by sitting in classrooms.

No bootcamp walked me through it. I built my own vulnerable environments from scratch, attacked them, documented what broke and why, and built the tools I wished existed. That process — of constructing real attack surfaces and systematically dismantling them — is how I learned to think like both an attacker and a defender simultaneously.

My work spans web application exploitation, network penetration testing, offensive tool development, and malware analysis. Every project I publish started as a question I couldn't find a good answer to. Every tool I've written is a weapon I needed and built myself.

> *"The self-taught hacker doesn't wait for permission to learn — they build the lab, set up the target, and start scanning."*

**Current focus:** Advanced web application pentesting · Red team tooling · Malware mechanics · Network exploitation

<br/>

---

## `$ cat /home/fawad/lab/README` — Custom Home Lab Setup

> This is what separates me from people who only watch tutorials. I built real, exploitable environments — and then broke them.

<table>
  <tr>
    <td width="50%" valign="top">

### 🖥️ Windows Lab Targets

| Service | Platform | Purpose |
|---------|----------|---------|
| 🗂️ **SMB (Samba)** | Windows 7 | EternalBlue / credential attacks / lateral movement practice |
| 📁 **WebDAV** | Windows | File upload exploitation, RCE via WebDAV misconfiguration |
| 📤 **FTP Server** | Windows | Anonymous login, brute force, file exfil simulation |
| 🌐 **HTTP Services** | Windows/Linux | Web app vuln testing, directory busting, auth bypass |

    </td>
    <td width="50%" valign="top">

### ⚙️ Lab Methodology

```
Phase 1: Service Setup
  → Deliberately misconfigure services
  → Expose known vulnerabilities

Phase 2: Attack
  → Recon → Enumeration → Exploitation
  → Post-exploitation → Lateral movement

Phase 3: Analyze
  → Review logs, packet captures
  → Document attack chain

Phase 4: Harden
  → Patch, reconfigure, re-attack
```

    </td>
  </tr>
</table>

**Why this matters:** Anyone can run Metasploit against a pre-built VM. Building and configuring the *targets themselves* requires understanding how services work at the system level — why they're exploitable, not just *that* they're exploitable. That deeper understanding is what makes the difference in real engagements.

<br/>

---

## `$ ls -la /projects` — Featured Arsenal

> These aren't portfolio pieces. They're proof of work — built to solve real problems in real engagements.

---

<details open>
<summary>🦷 &nbsp;<strong>Scanibal</strong> — Recon & Vulnerability Scanner &nbsp;<code>[ACTIVE]</code></summary>
<br/>

[![Repo](https://img.shields.io/badge/GitHub-Scanibal-181717?style=flat-square&logo=github&logoColor=00ff41)](https://github.com/notfawadmir/Scanibal)
![Language](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Category](https://img.shields.io/badge/Recon-Offensive-00ff41?style=flat-square)

The gap between "I have a target" and "I know what to hit" is where most pentesters waste hours. **Scanibal closes it.** It chains target enumeration → service fingerprinting → vulnerability identification into one streamlined pipeline — so you walk into exploitation with a clear attack surface map, not guesswork.

Built because I got tired of running five tools manually and stitching the output together by hand.

```
Capabilities: Automated scanning · Service enumeration · Vuln fingerprinting · Target profiling
```

</details>

---

<details open>
<summary>🦅 &nbsp;<strong>WebHawk</strong> — Web Application Security Tool &nbsp;<code>[ACTIVE]</code></summary>
<br/>

[![Repo](https://img.shields.io/badge/GitHub-WebHawk-181717?style=flat-square&logo=github&logoColor=00ff41)](https://github.com/notfawadmir/WebHawk)
![Language](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Category](https://img.shields.io/badge/Web-Red_Team-ff4444?style=flat-square)

Web applications are the most attacked surface — and most organizations are completely unaware of their exposure until it's too late. **WebHawk** maps injection points, authentication flaws, and misconfigurations that automated scanners routinely miss. Built for precision, not noise.

Tested and refined against my own custom web lab environments before release.

```
Capabilities: SQLi/XSS detection · Auth bypass testing · Misconfiguration discovery · Recon automation
```

</details>

---

<details open>
<summary>🔒 &nbsp;<strong>Ransomware</strong> — Educational Malware Implementation &nbsp;<code>[⚠️ Research Only]</code></summary>
<br/>

[![Repo](https://img.shields.io/badge/GitHub-Ransomware-181717?style=flat-square&logo=github&logoColor=ff4444)](https://github.com/notfawadmir/Ransomeware)
![Language](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Category](https://img.shields.io/badge/Malware-Analysis-ff0000?style=flat-square)

> ⚠️ *Strictly educational. Built and run in isolated lab environments only.*

You cannot build effective ransomware defenses without understanding ransomware internals. This project dissects **encryption workflows, key lifecycle management, and payload delivery mechanics** at the code level — giving defenders and analysts the inside view they need to detect and neutralize real-world variants before they trigger.

```
Internals: AES file encryption · Key lifecycle management · Payload delivery mechanics
```

</details>

---

<details open>
<summary>⌨️ &nbsp;<strong>Keylogger</strong> — Keystroke Capture Research Tool &nbsp;<code>[⚠️ Research Only]</code></summary>
<br/>

[![Repo](https://img.shields.io/badge/GitHub-Keylogger-181717?style=flat-square&logo=github&logoColor=ff4444)](https://github.com/notfawadmir/Keylogger)
![Language](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Category](https://img.shields.io/badge/Endpoint-Research-ff0000?style=flat-square)

> ⚠️ *Strictly educational. Built and run in isolated lab environments only.*

Endpoint security can't catch what it doesn't understand. This cross-platform implementation maps **input event capture at the OS level, privilege handling, and exfiltration simulation** — exposing the exact attack surface your EDR needs to monitor. Built to answer "how does this actually work" — not just "does it work."

```
Internals: Cross-platform input hooks · Stealth techniques · Keystroke buffering & exfil simulation
```

</details>

<br/>

---

## `$ skill --list --verbose`

### ⚔️ Offensive Security Toolkit

> Methodology-driven approach: Recon → Enumeration → Exploitation → Post-Exploitation → Reporting

<div align="center">

#### 🔴 Exploitation & Post-Exploitation

| Tool | Proficiency | Notes |
|------|-------------|-------|
| 💥 **Metasploit Framework** | ████████░░ Expert | Used against custom lab targets (SMB, WebDAV, HTTP) |
| 🐚 **Netcat** | ████████░░ Expert | Reverse shells, port pivoting, banner grabbing |
| 🔓 **John the Ripper** | ███████░░░ Advanced | Hash cracking, custom rules, wordlist optimization |
| #️⃣ **Hashcat** | ███████░░░ Advanced | GPU-accelerated cracking, mask attacks |

#### 🟠 Credential Attacks

| Tool | Proficiency | Notes |
|------|-------------|-------|
| 🔑 **Hydra** | ████████░░ Expert | Brute forced FTP/SSH/HTTP in lab environments |
| 🧠 **Medusa** | ████████░░ Expert | Parallel login attacks, protocol coverage |
| 🗝️ **CrackMapExec** | ██████░░░░ Intermediate | SMB enumeration, pass-the-hash attacks |

#### 🟡 Recon & Enumeration

| Tool | Proficiency | Notes |
|------|-------------|-------|
| 🗺️ **Nmap** | ████████░░ Expert | Service fingerprinting, NSE scripts, OS detection |
| 🌾 **theHarvester** | ███████░░░ Advanced | OSINT, email/subdomain harvesting |
| 🔍 **enum4linux** | ███████░░░ Advanced | SMB/Samba enumeration (used against custom Windows lab) |
| 📡 **Netdiscover** | ███████░░░ Advanced | ARP-based host discovery |

#### 🟢 Web Application Testing

| Tool | Proficiency | Notes |
|------|-------------|-------|
| 🕷️ **Burp Suite** | ████████░░ Expert | Intercept, repeater, intruder, active scanning |
| 💉 **sqlmap** | ████████░░ Expert | Manual verification + automated exploitation |
| 🦆 **Gobuster** | ████████░░ Expert | Dir/DNS/VHost busting against custom HTTP services |
| 🌐 **OWASP ZAP** | ███████░░░ Advanced | Automated + manual web scanning |
| 🔬 **Nikto** | ███████░░░ Advanced | Server misconfiguration discovery |
| 🕸️ **WhatWeb** | ██████░░░░ Intermediate | Technology fingerprinting |

#### 🔵 Network & Wireless

| Tool | Proficiency | Notes |
|------|-------------|-------|
| 🦈 **Wireshark** | ███████░░░ Advanced | Packet analysis of lab traffic captures |
| ✂️ **tcpdump** | ██████░░░░ Intermediate | CLI filtering, session reconstruction |
| 📶 **Aircrack-ng** | ██████░░░░ Intermediate | WPA/WPA2 capture & cracking |

</div>

---

### 💻 Languages & Development

<div align="center">

<table>
  <tr>
    <td align="center" width="96">
      <img alt="Python" width="48" height="48" src="https://raw.githubusercontent.com/HighAmbition211/HighAmbition211/auxiliary/languages/python.svg" />
      <br/><sub><b>Python</b></sub>
      <br/><sub>Primary · Tool Dev</sub>
    </td>
    <td align="center" width="96">
      <img alt="C++" width="48" height="48" src="https://raw.githubusercontent.com/HighAmbition211/HighAmbition211/auxiliary/languages/c++.svg" />
      <br/><sub><b>C++</b></sub>
      <br/><sub>Systems · Low-level</sub>
    </td>
    <td align="center" width="96">
      <img alt="Bash" width="48" height="48" src="https://github.com/devicons/devicon/blob/ca28c779441053191ff11710fe24a9e6c23690d6/icons/bash/bash-original.svg?raw=true" />
      <br/><sub><b>Bash</b></sub>
      <br/><sub>Scripting · Automation</sub>
    </td>
    <td align="center" width="96">
      <img alt="JavaScript" width="48" height="48" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" />
      <br/><sub><b>JavaScript</b></sub>
      <br/><sub>Web Attack Surface</sub>
    </td>
    <td align="center" width="96">
      <img alt="MySQL" width="48" height="48" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg" />
      <br/><sub><b>MySQL</b></sub>
      <br/><sub>SQLi Practice</sub>
    </td>
  </tr>
</table>

</div>

---

## `$ cat ~/philosophy.conf`

```yaml
# fawad.yaml — Operational Mindset

origin: Self-taught — no university, no bootcamp, no shortcuts
method: Build it. Break it. Document it. Repeat.

principles:
  - If you can't build the target, you don't understand the attack
  - Tool users are operators. Tool builders are engineers.
  - Every lab session is a paper trail — document or it didn't happen
  - Ethics aren't a constraint. They're what separates security research from crime.

specializations:
  - Offensive tool development (Python, C++)
  - Web application penetration testing (OWASP Top 10 + beyond)
  - Custom vulnerable lab construction & exploitation
  - Malware mechanics & analysis
  - Network reconnaissance & service exploitation

home_lab:
  services_attacked: [SMB, WebDAV, FTP, HTTP, HTTPS]
  platforms: [Windows 7, Windows 10, Linux]
  approach: Build → Misconfigure → Attack → Analyze → Harden

operating_system: Kali Linux
coffee: mission-critical
```

---

## `$ cat /certs/verified`

<div align="center">

### 🏅 Certifications

<a href="https://www.credly.com/badges/e79e2be1-d5cc-4cf2-b54f-2c1f1a781bdb/public_url" target="_blank">
  <img src="https://images.credly.com/size/340x340/images/af8c6b4e-fc31-47c4-8dcb-eb7a2065dc5b/I2CS__1_.png" alt="Introduction to Cybersecurity — Cisco" width="160"/>
</a>

<br/><br/>

> 🎯 *Currently grinding toward eJPT and eventually OSCP — the only cert that matters in this field.*

[![Credly](https://img.shields.io/badge/Credly-View_All_Badges-FF6B00?style=for-the-badge&logo=credly&logoColor=white)](https://www.credly.com/users/notfawadmir)

</div>

---

## `$ git log --oneline` — GitHub Activity

<div align="center">

<img width="49%" src="https://github-readme-stats.vercel.app/api?username=notfawadmir&count_private=true&show_icons=true&theme=radical&border_color=00ff41&border_radius=6&bg_color=0d1117&title_color=00ff41&icon_color=00ff41&text_color=c9d1d9" alt="GitHub Stats"/>
<img width="49%" src="https://github-readme-stats.vercel.app/api/top-langs?username=notfawadmir&layout=compact&theme=radical&border_color=00ff41&border_radius=6&bg_color=0d1117&title_color=00ff41&text_color=c9d1d9&langs_count=8" alt="Top Languages"/>

<br/><br/>

<img width="98%" src="https://streak-stats.demolab.com/?user=notfawadmir&theme=dark&border=00ff41&ring=00ff41&fire=ff4444&currStreakLabel=00ff41&sideLabels=00ff41&background=0d1117&border_radius=6&dates=c9d1d9" alt="GitHub Streak"/>

<br/>

<img width="98%" src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=notfawadmir&theme=github_dark" alt="Contribution Activity"/>

</div>

---

## `$ curl -O fawad.mir/cv`

<div align="center">

<a href="./assets/CV.pdf" download="Fawad_Ahmed_Mir_CV.pdf">
  <img src="https://img.shields.io/badge/Download%20CV-Click%20Here-00ff41?style=for-the-badge&logo=adobeacrobatreader&logoColor=0d1117&labelColor=0d1117" alt="Download CV" height="50"/>
</a>

</div>

---

## `$ nc -lvp 4444` — Reach Me

<div align="center">

> Open to: penetration testing roles, bug bounty collaboration, security research, red team tooling projects, and CTF teamups.
> If you have a target (with permission), a project, or just want to talk shop — the port is open.

<br/>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/fawad-ahmed-mir)
[![Gmail](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:fawadmeer000@gmail.com)
[![Medium](https://img.shields.io/badge/Medium-12100E?style=for-the-badge&logo=medium&logoColor=white)](https://medium.com/@fawadmeer000)
[![WhatsApp](https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white)](https://wa.me/923065297526)
[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://instagram.com/notfawadmir)
[![Threads](https://img.shields.io/badge/Threads-000000?style=for-the-badge&logo=threads&logoColor=white)](https://www.threads.net/@notfawadmir)
[![Facebook](https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white)](https://www.facebook.com/fawad.mir.2025)

</div>

---

<div align="center">

```
┌──────────────────────────────────────────────────────────────────────┐
│                                                                      │
│  The best pentesters aren't the ones with the most certs.           │
│  They're the ones who built a lab at 2am just to see if it works.  │
│                                                                      │
│  ⭐ If a repo helped you, star it. It costs nothing.               │
│                                                                      │
└──────────────────────────────────────────────────────────────────────┘
```

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,100:001a0d&height=100&section=footer&fontColor=00ff41" width="100%"/>

</div>
