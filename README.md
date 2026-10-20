CodeAlpha Basic Network Sniffer
A basic educational IPv4 packet sniffer written with Python's standard library.
Features
Captures raw packets using platform-specific sockets.
Parses Ethernet (Linux), IPv4, TCP, UDP, and ICMP headers.
Displays source/destination IP addresses, ports, TCP flags, and a short payload preview.
Supports protocol filtering, packet count limits, text logging, and summary statistics.
Checks packet lengths and skips malformed packets rather than stopping immediately.
Requirements
Python 3.9+ recommended.
Linux: raw packet capture normally requires root privileges.
Windows: run as Administrator. Windows raw-socket behavior differs from Linux; test on your machine and network adapter.
No third-party Python packages are required.
Usage
Linux:
sudo python3 sniffer.py -c 20
sudo python3 sniffer.py -p tcp
sudo python3 sniffer.py -c 50 -o capture_log.txt
Windows (Command Prompt as Administrator):
python sniffer.py -c 20
python sniffer.py -p udp
python sniffer.py -c 50 -o capture_log.txt
-c 0 (the default) runs until Ctrl+C. -p supports tcp, udp, and icmp. -o writes displayed packet details to a text file.
Limitations
This is an educational sniffer, not a replacement for Wireshark.
It parses IPv4 only; IPv6, ARP, VLAN tags, and packet capture export to PCAP are not implemented.
Non-initial IPv4 fragments are identified but not reassembled.
Raw socket availability and capture behavior vary by operating system, permissions, and network adapter.
Payload previews can expose sensitive data. Use only on networks/devices you own or have explicit permission to monitor, and do not publish logs containing private information.
Testing
The source file has been syntax-compiled. You should still run functional tests on your own system with permission to capture traffic. Do not describe it as tested on live traffic until you have actually run and verified that test.
