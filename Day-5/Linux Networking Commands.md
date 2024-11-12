# Linux Networking Commands

This README file provides detailed information about essential Linux networking commands for easy reference.

## Basic Commands

1. `ifconfig`
The `ifconfig` command is used to configure and display network interface parameters. It is commonly used to display the IP address, MAC address, and the status of network interfaces.

```bash
ifconfig
```
### Common Usage:
- Display all active network interfaces and their details.
- Configure network interfaces (e.g., ifconfig eth0 up to bring up an interface).
- Note: ifconfig is deprecated in many Linux distributions in favor of the ip command.

2. ip
The ip command is a versatile tool for network management. It is used for displaying and manipulating routing, devices, policy routing, and tunnels.
```
ip addr show          # Show all IP addresses assigned to interfaces
ip link show          # Show the link layer information (MAC address, status)
ip route show         # Display the routing table
ip link set eth0 up   # Bring an interface up (replace eth0 with your interface name)
ip link set eth0 down # Bring an interface down

```
- Common Usage:
- ip addr show lists all network interfaces and their assigned IP addresses.
- ip link show displays the status (up or down) of all network interfaces.
- ip route show shows the routing table.

3. ping
The ping command is used to test connectivity between the host machine and a remote network host. It sends ICMP echo request packets and waits for an ICMP echo reply.
```
ping <hostname or IP>

```
- Common Usage:
- Check if a host is reachable over the network.
- Measure round-trip time of packets (latency).
- Use ping -c 4 to limit the number of pings to 4.

4. netstat
The netstat command is used to display active network connections, routing tables, and interface statistics. It is useful for monitoring network activity.
```
netstat -tuln           # Show TCP/UDP ports in listening state
netstat -a              # Show all network connections (both listening and established)
netstat -s              # Show network statistics (like bytes sent/received)

```
- Common Usage:
- netstat -tuln shows TCP/UDP ports that are currently open and listening for connections.
- netstat -a lists all active connections (both listening and established).

5. ss
The ss (Socket Statictics) command is a faster and more efficient replacement for netstat. It is used to investigate sockets and network connections.
```
ss -tuln               # Show TCP/UDP listening ports
ss -a                  # Show all socket connections (both established and listening)
ss -s                  # Show socket statistics

```
- Common Usage:
- ss -tuln shows listening TCP and UDP ports.
- ss -a shows all open sockets (both listening and established).

6. traceroute
The traceroute command is used to trace the path that packets take from the source machine to a destination over the network, showing each hop along the way.
```
traceroute <hostname or IP>
```
- Common Usage:
- Identify the path and delay of packets traveling through the network.
- Helpful for diagnosing network routing issues.

7. nslookup
The nslookup command is used to query Domain Name System (DNS) servers to obtain domain name or IP address information.
```
nslookup <domain>

```
- Common Usage:
- Find the IP address of a domain name.
- Verify DNS resolution.
- Note: nslookup is typically used for DNS troubleshooting.

9. hostname
The hostname command shows or sets the system's hostname. The hostname is used to identify the machine on a network.
```
hostname               # Show the system’s current hostname
hostnamectl set-hostname <new-hostname>  # Set a new hostname

```
- Common Usage:
- Use hostname to view the current system name.
- Use hostnamectl to change the system’s hostname on modern Linux distributions.

10. curl / wget
Both curl and wget are tools used to retrieve data from the web, but curl is more flexible and supports a wide range of protocols.
```
curl <URL>             # Retrieve web content
wget <URL>             # Download files from a URL
```
- Common Usage:
- curl is commonly used for API requests and web scraping.
- wget is used for downloading large files or mirroring websites.





## Advanced Commands
11. tcpdump
The tcpdump command is used to capture network packets for analysis. It is helpful for diagnosing network issues or monitoring traffic.
```
tcpdump -i <interface>   # Capture packets on the specified interface
tcpdump -w <file>        # Save the captured packets to a file

```
- Common Usage:
- tcpdump -i eth0 captures packets on the eth0 interface.
- tcpdump -w capture.pcap saves the captured packets to a .pcap file for later analysis.

12. iptables
The iptables command is used to configure the Linux kernel firewall and define rules for packet filtering and NAT.
```
iptables -L             # List all active rules
iptables -A INPUT -p tcp --dport <port> -j ACCEPT  # Allow incoming on a specific port
iptables -A OUTPUT -p udp --dport <port> -j DROP  # Block outgoing UDP on a port
```
- Common Usage:
- iptables -L lists the current firewall rules.
- iptables -A INPUT -p tcp --dport 80 -j ACCEPT allows HTTP traffic through port 80.

13. nmap
The nmap (Network Mapper) command is used for network discovery and security auditing. It can identify hosts and services on a network.
```
nmap <IP or hostname>    # Scan a host for open ports
nmap -sV <IP>           # Scan a host and attempt to detect service versions
nmap -O <IP>            # Perform OS detection

```
- Common Usage:
- nmap helps identify open ports on a networked system.
- nmap -sV attempts to determine the versions of the services running on the open ports.

14. ipconfig (Windows) / nmcli (Linux)
ipconfig is used to display network configuration on Windows, while nmcli is used for NetworkManager control in Linux.
```
nmcli dev status         # Show network device status
nmcli con show           # Show network connections
```
- Common Usage:
- nmcli is used for managing network connections on Linux systems with NetworkManager.

15. route
The route command is used to show or modify the IP routing table. It can also be used to add or delete routes.
```
route -n                 # Show the IP routing table
route add default gw <gateway-IP>  # Add a default gateway

```
- Common Usage:
- route -n displays the current IP routing table.
- route add adds a new route to the table.

16. arp
The arp (Address Resolution Protocol) command is used to display or manipulate the ARP table. ARP maps IP addresses to MAC addresses.
```
arp -a                   # Show ARP table
arp -d <IP>              # Delete an entry from the ARP table
```
- Common Usage:
- arp -a shows the mapping of IP addresses to MAC addresses.
- arp -d can be used to remove a specific ARP entry.

17. ethtool
The ethtool command is used to display or change the settings of network interfaces, primarily for Ethernet devices.
```
ethtool <interface>      # Display settings for the specified interface
ethtool -s eth0 speed 1000 duplex full  # Set the speed and duplex mode

```
- Common Usage:
- ethtool eth0 shows the current settings of the Ethernet interface eth0.


18. iwconfig
The iwconfig command is used to configure wireless network interfaces, such as Wi-Fi.
```
iwconfig                 # Show wireless interface info
iwconfig <interface> essid <network> key <password>  # Connect to WiFi

```
- Common Usage:
-  iwconfig is used to set up wireless network interfaces, including SSID and encryption keys.

19. vnstat
The vnstat command is a network traffic monitor that tracks bandwidth usage on network interfaces.
```
vnstat                   # Show bandwidth usage summary
vnstat -d                # Show daily traffic statistics
vnstat -w                # Show weekly traffic statistics

```
- Common Usage:
- vnstat shows the overall bandwidth usage for each interface.
- Note: vnstat needs to be installed and configured before use.

20. speedtest-cli
The speedtest-cli command is used to test the speed of your internet connection.
```
speedtest-cli            # Run an internet speed test
```
- Common Usage:
- speedtest-cli tests download and upload speeds, along with ping latency.

## Troubleshooting Commands
21. nc (netcat)
The nc (netcat) command is used for reading and writing data across network connections using the TCP or UDP protocol. It is commonly used for testing and debugging network services
```
nc -zv <hostname> <port>  # Test connectivity to a specific port

```
- Common Usage:
- nc is used to test whether a specific port on a server is open and reachable.

22. mtr
The mtr command is a network diagnostic tool that combines the functionality of ping and traceroute. It provides detailed, real-time information about the route packets take to their destination.
```
mtr <hostname>           # Start the mtr trace to a specific host
```
- Common Usage:
- mtr continuously reports the path and response times of packets, helping to diagnose network issues.

23. whois
The whois command queries the WHOIS database to retrieve information about a domain name or IP address, including the owner and contact details.
```
whois <domain>

```
- Common Usage:
- whois example.com retrieves registration information for the domain example.com.







