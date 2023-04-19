# using-the-map - medium 

## Description
* You got access to Skynet and it looks like you aren't alone! Besides our good friend 22/tcp, what is the version of the other open service on this unknown host?
* ssh `<username>@<host>` | Password: `<password>`
* **IMPORTANT**: Make sure any active reconnaissance is done only to **PRIVATE** IP addresses, not public. All actions are required to be done within the virtual machine. It is illegal to perform active reconnaissance on real-life hosts without prior authorization. These virtual machines are configured and isolated in a Virtual Private Cloud (VPC).

## Hint
* Children's toy commercials be like: "Buy this map today for the low cost of $149.99 (5 payments) with free shipping and handling! Taxes and net-tools not included. Credit card, cash, and ip command all accepted."
* Flag format: jctf{version}

## Solution Steps
* SSH into the virtual machine and type `ip addr` to list the network interfaces, with 192.168.25.2/28 being the host's private IP address. This means that each host on the subnet will be 192.168.25.x/28, and to search the entire network it would be 192.168.25.0/28.
* Perform an Nmap host discovery scan using a few different commands:
  * `nmap -sn 192.168.25.0/28`
  * `nmap -sL 192.168.25.0/28`
  * `nmap -Pn 192.168.25.0/28`
* With the other active host being 192.168.25.3 with a few open ports, perform a version scan with `nmap -sV 192.168.25.3` 
* Flag: `jctf{2-4}` or `jctf{2-4 (RPC #100000)}` or `jctf{rpcbind 2-4 (RPC #100000)}` or `jctf{rpcbind 2-4}` 

## Knowledge and/or Tools Needed
* [MITRE ATT&CK® Technique T1046 - Network Service Discovery](https://attack.mitre.org/techniques/T1046/)
* [Nmap](https://nmap.org/)
