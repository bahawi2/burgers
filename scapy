from scapy.all import ARP, Ether, srp

# Define the network range to scan
network = '192.168.1.0/24'

# Create an ARP request packet to broadcast to the network
arp = ARP(pdst=network)
ether = Ether(dst='ff:ff:ff:ff:ff:ff')
packet = ether/arp

# Send the packet and capture the response
result = srp(packet, timeout=3, verbose=0)[0]

# Iterate over the responses and print the ARP, vendor, and model information for each device
for sent, received in result:
    # Extract the MAC address, IP address, and vendor information from the response
    mac = received.hwsrc
    ip = received.psrc
    vendor = received.vendor

    # Print the MAC address, IP address, and vendor information for the device
    print('MAC Address: {}, IP Address: {}, Vendor: {}'.format(mac, ip, vendor))
