Place Red Team/Pentesting Scripts and Resources Here.

#### Password Cracking
The first step in evaluating a target network is to identify open ports and active services.

```
hydra -t 4 -l [userName] -P /usr/share/wordlists/rockyou.txt -vV [ip] [protocol]
```

Resources
[Try Hack Me Hydra](https://tryhackme.com/r/room/hydra)
[Try Hack Me Brute Force Heroes](https://tryhackme.com/r/room/bruteforceheroes)
[Try Hack Me HackPark](https://tryhackme.com/r/room/hackpark)
