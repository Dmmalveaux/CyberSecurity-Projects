## Virtual Machines

Windows Server 2022
Purpose:
Domain Controller
DNS
Authentication

Windows 11
Purpose:
Employee Workstation

Windows 10
Purpose:
Second Employee Workstation

Ubuntu Server
Purpose:
Internal Web Server

Kali Linux
Purpose:
Attacker Machine

Splunk Enterprise
Purpose:
Centralized Log Collection
Threat Detection
Incident Investigation

| Machine           | IP Address      |
| ----------------- | --------------- |
| Domain Controller | 192.168.123.10  |
| Splunk            | 192.168.123.20  |
| Ubuntu            | 192.168.123.30  |
| Windows 11        | 192.168.123.100 |
| Windows 10        | 192.168.123.101 |
| Kali              | 192.168.123.200 |


                     Internet
                          │
                    Home Router
                          │
             VMware Virtual Switch
                          │
      ┌──────────────────────────────────┐
      │                                  │
Windows Server 2022             Splunk Enterprise
192.168.10.10                   192.168.10.20
Domain Controller               SIEM
      │
 ┌────┴───────────────┐
 │                    │
Windows 11         Windows 10
192.168.10.100     192.168.10.101
Employee           Employee
      │
      └──────────────┐
                     │
               Ubuntu Server
               192.168.10.30
               Web Server
                     │
                Kali Linux
              192.168.10.200
              Attacker

## Active Directory Domain

project.local
