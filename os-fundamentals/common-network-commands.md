# Common Network Commands

Network commands are essential tools for managing and troubleshooting network connections on a Linux system. Below is a brief explanation of some of the most commonly used network commands in Kali Linux along with examples.

***

#### 1. **`ifconfig` (Interface Configuration)**

* **Purpose**: Displays or configures network interfaces, including their IP addresses, MAC addresses, and other related details.
*   **Example**:

    ```bash
    ifconfig
    ```

    **Output**:

    ```
    eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
            inet 192.168.1.101  netmask 255.255.255.0  broadcast 192.168.1.255
            inet6 fe80::a00:27ff:fe8f:ad71  prefixlen 64  scopeid 0x20<link>
            ether 08:00:27:8f:ad:71  txqueuelen 1000  (Ethernet)
            RX packets 21282  bytes 2169575 (2.0 MB)
            RX errors 0  dropped 0  overruns 0  frame 0
            TX packets 15835  bytes 1205462 (1.1 MB)
            TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
    ```

    This command shows detailed information about each network interface, including IP address, MAC address, and network statistics.

***

#### 2. **`ip a` (Show IP Addresses)**

* **Purpose**: Displays IP addresses and network interfaces on the system. This is an alternative to `ifconfig` and is often preferred in modern Linux distributions.
*   **Example**:

    ```bash
    ip a
    ```

    **Output**:

    ```
    1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN
        inet 127.0.0.1/8 scope host lo
           valid_lft forever preferred_lft forever
    2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP qlen 1000
        inet 192.168.1.101/24 brd 192.168.1.255 scope global dynamic eth0
           valid_lft 86145sec preferred_lft 86145sec
    ```

    It shows all network interfaces (`eth0`, `lo`, etc.) and their associated IP addresses, which can be useful for network configuration and diagnostics.

***

#### 3. **`ip n` (Show Neighboring Information)**

* **Purpose**: Displays the ARP (Address Resolution Protocol) cache, which includes a list of IP-to-MAC address mappings.
*   **Example**:

    ```bash
    ip n
    ```

    **Output**:

    ```
    192.168.1.1 dev eth0 lladdr 00:11:22:33:44:55 REACHABLE
    192.168.1.101 dev eth0 lladdr 08:00:27:8f:ad:71 STALE
    ```

    The command provides a view of which IP addresses are associated with which MAC addresses on the local network.

***

#### 4. **`arp -a` (Show ARP Table)**

* **Purpose**: Displays the ARP table, which maps IP addresses to MAC addresses for devices in the local network.
*   **Example**:

    ```bash
    arp -a
    ```

    **Output**:

    ```
    ? (192.168.1.1) at 00:11:22:33:44:55 [ether] on eth0
    ? (192.168.1.101) at 08:00:27:8f:ad:71 [ether] on eth0
    ```

    This command is useful for verifying the devices on the local network and their corresponding hardware addresses.

***

#### 5. **`ip r` (Show Routing Table)**

* **Purpose**: Displays the routing table, showing how packets are routed through different network interfaces.
*   **Example**:

    ```bash
    ip r
    ```

    **Output**:

    ```
    default via 192.168.1.1 dev eth0
    192.168.1.0/24 dev eth0 proto kernel scope link src 192.168.1.101
    ```

    It shows the default route and local routes for IP addresses, helping with troubleshooting network routing issues.

***

#### 6. **`route` (Show/Modify Routing Table)**

* **Purpose**: Displays or modifies the routing table. This command is used to manage how packets are forwarded between networks.
*   **Example**:

    ```bash
    route -n
    ```

    **Output**:

    ```
    Kernel IP routing table
    Destination     Gateway         Genmask         Flags Metric Ref    Use Iface
    0.0.0.0         192.168.1.1     0.0.0.0         UG    100    0        0 eth0
    192.168.1.0     0.0.0.0         255.255.255.0   U     0      0        0 eth0
    ```

    The `route` command shows the routing table, where `UG` indicates a route to the gateway (`192.168.1.1` in this case).

***

#### 7. **`ping` (Send ICMP Echo Request)**

* **Purpose**: Sends ICMP echo requests to a network host to test connectivity and measure response times.
*   **Example**:

    ```bash
    ping 192.168.1.1
    ```

    **Output**:

    ```
    PING 192.168.1.1 (192.168.1.1) 56(84) bytes of data.
    64 bytes from 192.168.1.1: icmp_seq=1 ttl=64 time=0.146 ms
    64 bytes from 192.168.1.1: icmp_seq=2 ttl=64 time=0.189 ms
    ```

    `ping` is useful for checking if a specific IP address or hostname is reachable over the network.

***

#### Additional Common Network Commands:

***

#### 8. **`netstat` (Network Statistics)**

* **Purpose**: Displays network connections, routing tables, interface statistics, and more.
*   **Example**:

    ```bash
    netstat -tuln
    ```

    **Output**:

    ```
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address           Foreign Address         State
    tcp        0      0 0.0.0.0:22              0.0.0.0:*               LISTEN
    tcp6       0      0 :::80                   :::*                    LISTEN
    ```

    This command shows open ports and services listening on the network.

***

#### 9. **`nslookup` (Query DNS)**

* **Purpose**: Resolves domain names to IP addresses using DNS.
*   **Example**:

    ```bash
    nslookup example.com
    ```

    **Output**:

    ```
    Server:  192.168.1.1
    Address: 192.168.1.1#53

    Non-authoritative answer:
    Name: example.com
    Address: 93.184.216.34
    ```

    `nslookup` helps to troubleshoot DNS-related issues by resolving domain names to their corresponding IP addresses.

***

#### 10. **`traceroute` (Trace Route to a Host)**

* **Purpose**: Traces the route packets take to reach a network host.
*   **Example**:

    ```bash
    traceroute example.com
    ```

    **Output**:

    ```
    1  192.168.1.1 (192.168.1.1)  1.113 ms  1.039 ms  1.084 ms
    2  203.0.113.1 (203.0.113.1)  10.823 ms  10.887 ms  10.963 ms
    ```

    `traceroute` helps identify where packets are delayed or dropped along the route to a destination.

***

#### 11. **`hostname` (Show or Set the Hostname)**

* **Purpose**: Displays or sets the system's hostname.
*   **Example**:

    ```bash
    hostname
    ```

    **Output**:

    ```
    kali
    ```

    This command displays the current hostname of the system. You can use `hostname new_name` to set a new hostname.

***

### Summary:

Here’s a quick summary of the commands we discussed:

| Command      | Purpose                                            | Example                  |
| ------------ | -------------------------------------------------- | ------------------------ |
| `ifconfig`   | Display network interface details                  | `ifconfig`               |
| `ip a`       | Show IP addresses of network interfaces            | `ip a`                   |
| `ip n`       | Show ARP cache (IP-MAC address mapping)            | `ip n`                   |
| `arp -a`     | Display ARP table                                  | `arp -a`                 |
| `ip r`       | Show routing table                                 | `ip r`                   |
| `route`      | Show or modify routing table                       | `route -n`               |
| `ping`       | Test connectivity to a host                        | `ping 192.168.1.1`       |
| `netstat`    | Display network connections and statistics         | `netstat -tuln`          |
| `nslookup`   | Query DNS and resolve domain names to IP addresses | `nslookup example.com`   |
| `traceroute` | Trace the route packets take to a network host     | `traceroute example.com` |
| `hostname`   | Show or set the system's hostname                  | `hostname`               |

These network commands will help you manage and troubleshoot your network connections and configurations efficiently on Kali Linux.

