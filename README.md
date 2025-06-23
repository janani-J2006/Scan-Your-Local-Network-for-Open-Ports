# Scan-Your-Local-Network-for-Open-Ports

Local Network Port Scan (Using Kali Linux)
**Task Objective**
To scan the local network using Kali Linux and Nmap to discover devices and their open ports, and understand potential security risks.
Objective: Learn to discover open ports on devices in your local network to
 understand network exposure.

Tools Used
- Kali Linux (running in VirtualBox)
- Nmap (built-in tool)

**What Is Port Scanning?** 
Imagine a house (your computer) has many doors (called ports). Some are open, and others are locked. Port scanning is like checking all the doors of all the houses in your street (your network) to see which ones are open. Open doors can let in guests (apps or services), but they can also let in thieves (hackers). So we check them to stay safe.

**Step 1**: Use Kali Linux (No need to install Nmap)
        Start your Kali Linux VM (in VirtualBox or VMware).
        Open the Terminal in Kali.
        Confirm Nmap is already there:


![Screenshot_2025-06-23_09_20_05](https://github.com/user-attachments/assets/74c16ea8-1873-41be-b185-25fe5f257d97)

**Step 2**: Find Your Network Range
        We need to find the range of IPs in your network (like saying “scan all the houses in this street”).
![Screenshot 2025-06-23 200516](https://github.com/user-attachments/assets/8ce5d38e-c414-44fc-966e-a1b1a1cc5db7)

**Step 3**: Do the Port Scan
        Now we use Nmap to scan all devices on the network.

  In Kali terminal, run:

![Screenshot_2025-06-23_09_20_31](https://github.com/user-attachments/assets/3ce9b03b-0113-4a0e-8d87-15987c9bbb42)

This will:
        Go to every device in your network.
        Knock on every door (port).
        Show which ones answer back (open).
        It will take 1–2 minutes. Be patient.

**Step 4**:
       Read the Results 
       After the scan, you’ll see results 
       Save the Scan Results
![Screenshot_2025-06-23_09_20_44](https://github.com/user-attachments/assets/df35e033-348a-4269-96b3-a002b995f7da)

You can see it with:  cat scan_results.txt

## Results Summary
- Scanned 256 IPs
- Found 3 devices online
- Detected open ports like:
  - 53 (DNS)
  - 22 (SSH)
  - 80 (HTTP)

**What Your Nmap Scan Found**

Nmap found 3 devices online:

 Device 1: 192.168.162.32 (Your Kali VM)
 Port 53 open → DNS (Domain Name System)
 DNS is used to translate names (like google.com) to IPs.

 Device 2: 192.168.162.52
 No response on any ports
 Port 22 (SSH) being open could mean remote login is possible. If left unprotected, an attacker could brute-force into this system. This shows why open ports should be secured with firewalls or key-based      
 authentication

 Device 3: 192.168.162.30
 Port 22 open → SSH (remote login)

 Port 80 open → HTTP (web server)
 This could be a router, server, or someone hosting a website!

 To secure this network, I would suggest:

                       Disabling unused ports (like SSH if not needed)

                       Enabling firewall rules

                       Changing default passwords on router

## What I Learned
- How to find my IP range using `ip a`
- How to do a SYN scan using Nmap
- Risks of open ports like SSH or HTTP
- Importance of firewalls and secure network settings


## Files Included
- `scan_results.txt` – full output of my Nmap scan

       
