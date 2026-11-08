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

### Week 4
- Completed the HPE Software Engineering Virtual Experience
- Designed and built a RESTful web service in Java Spring Boot to manage employee data (GET and POST)
- Wrote JUnit unit tests and proposed a private cloud architecture using HPE GreenLake
- Learned: REST API design, separation of concerns, and unit testing

### Week 5
* Built a password breach checker in Python that checks if a password has appeared in a known data breach
* Used the Have I Been Pwned API with k-anonymity: only the first 5 characters of the password's SHA-1 hash are ever sent, so the password and full hash never leave the machine
* Added a request timeout and error handling that exits with code 1, so a failed API call errors out instead of falsely reporting "not found"
* Wrote 7 unit tests with unittest, mocking the API so tests run offline; one test confirms only the 5-char prefix is sent
* Refactored into separate functions with a main guard
* Documented it with a README and a sequence diagram: github.com/IbrahimHussain2/password-breach-checker
* Learned: k-anonymity, hashing for lookup vs storage (SHA-1 is fine here but bcrypt/Argon2 for storing passwords), why a false negative is the worst failure for a security tool, and mocking in tests


