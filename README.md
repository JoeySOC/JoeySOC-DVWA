#     DVWA Exploitation Report: Command Injection

##    Lab Objective

To identify and exploit a command injection vulnerability in DVWA's "Command Injection" module. The goal is to bypass input restrictions and execute arbitrary OS commands to confirm remote code execution (RCE) capabilities.

---

##    Target Information

| Component     | Value             |
|---------------|------------------|
| **Victim Host** | DVWA Web Server |
| **IP Address**  | 192.168.56.109  |
| **Operating System** | Ubuntu (Apache 2.4.52) |
| **Web Service** | Apache HTTP Server |
| **Security Level (DVWA)** | Low |
| **Interface Used** | Web UI (Command Injection Panel) |

---

##    Attacker Machine

| Component     | Value             |
|---------------|------------------|
| **Host**         | Kali Linux       |
| **IP Address**   | 192.168.56.102   |
| **Tool Used**    | Browser-based manual injection |
| **Network Mode** | Host-Only (VirtualBox) |

---

##    Attack Overview

**Attack Type**: Remote Command Injection (RCE)  
**Vector**: Input field in DVWA's Command Injection module  
**Mechanism**: Chained injection using semicolon (`;`) to append OS commands  
**Result**: Successful execution of injected `ping` command

---

##    Injection Payload

###   Original Input
```text
127.0.0.1
