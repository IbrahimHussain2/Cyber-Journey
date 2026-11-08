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

built a password breach checker in python this week. the idea was to make something that actually solves a problem instead of just showing i can code.

it checks if a password has been in a known data breach using the have i been pwned api. the clever bit is k-anonymity - you hash the password with sha-1, then only send the first 5 characters of the hash to the api. it sends back every hash that starts with those 5 chars plus how many times each was breached, and you match yours locally. so the api never sees your actual password or even your full hash. tested it with "password" and it came back as seen over 52 million times.

things i learned:
- hashing for lookup vs hashing for storage. sha-1 is actually a broken hash - back in 2017 researchers pulled off the "shattered" attack and made two different files produce the exact same sha-1 hash, which is called a collision. so you should never use it for real security like signing or certificates. but it's fine here for two reasons: the hibp database is already built in sha-1 so i have to match it, and collisions aren't a threat for this - a collision means finding two inputs with the same hash, but im just looking up whether my one specific hash is on a known list. for actually storing passwords you'd use bcrypt or argon2 instead, because theyre deliberately slow and salted so they cant be brute forced or looked up in a table.
- for a security tool a false negative is the worst outcome. if the api call fails it should error out, not say "not found" and make you think a bad password is safe. so i added a timeout and proper error handling that exits with code 1.
- wrote 7 unit tests with unittest and mocked the api call so the tests dont need internet. one test literally checks only the 5 char prefix gets sent.
- refactored it into separate functions with a main guard at the end instead of one big blob.


