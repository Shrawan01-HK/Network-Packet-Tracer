# Network-Packet-Tracer
# Packet Sniffer using Scapy

This repository contains a Python script that implements a simple packet sniffer using the Scapy library. The script captures network packets and extracts key information, including source and destination IP addresses, protocol type, and payload data.

## Overview

The script listens for incoming packets on the network and processes them in real-time. For each captured packet, it checks for the presence of IP, TCP, and UDP layers, then prints relevant details.

### Key Features

- **IP Address Extraction**: Displays source and destination IP addresses for each packet.
- **Protocol Identification**: Identifies the protocol used (TCP/UDP).
- **Payload Decoding**: Attempts to decode and print the payload for TCP and UDP packets.
- **Error Handling**: Manages decoding errors gracefully, providing feedback if the payload cannot be decoded.

## How It Works

1. **Packet Callback Function**: The `packet_callback` function is called for each captured packet. It checks if the packet contains an IP layer, extracts details, and identifies if it contains TCP or UDP layers.
2. **Payload Handling**: For TCP and UDP packets, the script attempts to decode the payload as UTF-8 and prints it. If decoding fails, it outputs an error message.
3. **Sniffing Function**: The `start_sniffing` function initiates the packet sniffing process, utilizing Scapy’s `sniff` method to capture packets without storing them.

## Example Output

```
Source IP: 192.168.1.1 | Destination IP: 192.168.1.2 | Protocol: 6
TCP Payload
Source IP: 192.168.1.2 | Destination IP: 192.168.1.1 | Protocol: 17
UDP Payload
```

## Requirements

- Python 3.x
- Scapy library (`pip install scapy`)

## Usage

Run the script with appropriate permissions (e.g., as root) to capture network traffic. Modify the script as needed to filter specific traffic or enhance functionality.

## License

This project is open-source and available under the MIT License. Contributions are welcome!
