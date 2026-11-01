# Cyber Journey

## About me
I'm Ibrahim, a second-year Cybersecurity (BSc Hons) student at Aston University. I'm building my practical skills alongside my degree, with the aim of securing a placement in cybersecurity.

## Why this repo
This is where I log what I'm learning each week: notes, lab work and small projects. The goal is to understand how things work, not just how to use tools.

## Log

### Week 1
- Set up WSL2 with Ubuntu to get a Linux environment on Windows
- Created a GitHub account and enabled two-factor authentication (authenticator app)
- Configured Git with a private noreply email to keep my real address off public commits
- Generated an ed25519 SSH key pair and used it to authenticate with GitHub
- Learned basic Linux commands: whoami, pwd, ls, cd, mkdir

### Week 2
- Built an SSH brute-force detector in Python (parses auth logs, flags compromised accounts)
- Built a phishing awareness simulator (local training tool: generates emails, tracks clicks, reports results)
- Learned about false positives, detection thresholds, tracking tokens, and keeping personal data out of version control with .gitignore
- Completed the Mastercard Cybersecurity Virtual Experience Programme (scored 90%): identified phishing threats, interpreted a simulated campaign's results, and designed awareness training for the at-risk teams

### Week 3
- Built a full home network security lab in VirtualBox (pfSense firewall + Ubuntu host)
- Configured and hardened pfSense, wrote a custom firewall rule, and verified it (blocked ICMP, HTTPS still worked)
- Analysed live traffic in Wireshark (blocked ICMP vs working DNS)
- Deployed Snort IDS with my own detection signature that alerted on test traffic
- Ran an nmap scan and found an exposed HTTP service on the firewall
- Documented the whole project with evidence: github.com/IbrahimHussain2/network-security-lab
- Learned: default-deny, rule ordering, IDS vs IPS, defence in depth, attack surface
