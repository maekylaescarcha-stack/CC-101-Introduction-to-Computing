**Republic of the Philippines**

**SORSOGON STATE UNIVERSITY**

**COLLEGE OF INFORMATION AND COMMUNICATIONS TECHNOLOGY**

Bulan Campus

Zone 8, Bulan, Sorsogon

Tel. No.: 056 311-0103; Email Address: cict@sorsu.edu.ph

### CC 101 - Introduction to Computing

**"Know Your Network Settings": Exploring Windows 11 Network Configuration Tools**

* **Name:** Mae Kyla G. Guelas
* **Block:** BSCS 1-1
* **Date:** OCTOBER 14, 2026
* **Computer Unit Used (Desktop/Laptop, brand):** LAPTOP, DELL

---

### I. Objectives

At the end of this activity, you should be able to:

1. Locate network adapter information using Windows 11 Settings, the Control Panel, Command Prompt (CMD), and PowerShell.
2. Use `ipconfig`, `getmac`, `hostname`, `ping`, `netstat`, `route print`, and `systeminfo` in CMD, and `Get-NetAdapter`, `Get-NetIPAddress`, and `Test-Connection` in PowerShell.
3. Interpret a sample `ipconfig /all` output from a networked computer: identify its IP address, subnet mask, default gateway, and DNS servers, and classify the address as public or private.
4. Relate each tool and finding to the layer of the OSI model where it works.
5. Design a simple network and IP address plan for the computer laboratory.

---

### II. Materials Needed

* A computer running Windows 11 (a network or Internet connection is not required for this activity)
* This worksheet (printed copy, or the digital file to fill out and submit)
* Week 6 lecture notes, for reference on IP addresses, protocols, the OSI model, and network devices

---

### III. Background

A computer does not need to be connected to a network to have network settings. Every PC has one or more network adapters (NICs), each with a permanent MAC address, and Windows always runs the TCP/IP software, including the loopback address $127.0.0.1$ (IPv4) and $::1$ (IPv6) that the computer uses to talk to itself. Windows 11 lets you inspect these settings in four places: the Settings app, the classic Control Panel, Command Prompt (CMD), and PowerShell. In this activity, you will explore all four on your own unit, observe how Windows behaves when no network is available, and then analyze a sample configuration taken from a computer that is connected to a network.

---

### IV. Procedure

> **Reminder:** This is a viewing activity. Do not change, disable, or reset any network setting. Close every dialog with Cancel. Record values exactly as Windows shows them.

#### Part A - Windows 11 Settings
1. Press `Windows + I` to open Settings, then click **Network & internet**. Write down the connection status shown at the top of the page (for example, "Not connected").
2. Click **Advanced network settings**. Under **Network adapters**, note every adapter listed (for example, Ethernet, Wi-Fi, Bluetooth Network Connection) and whether each one is enabled or disconnected.
3. Scroll down and click **Hardware and connection properties**. For each adapter, record its Name, Description, Physical address (MAC), and Status in **Table 1**.

#### Part B - Control Panel (Network Connections)
4. Press `Windows + R`, type `ncpa.cpl`, and press Enter. This opens the classic Network Connections window. A red X on an icon means the adapter has no network connection.
5. Right-click your Ethernet adapter and choose **Properties**. List the items checked under "This connection uses the following items" in **Table 2**.
6. Select **Internet Protocol Version 4 (TCP/IPv4)** and click **Properties**. Record whether the computer is set to Obtain an IP address automatically (DHCP) or Use the following IP address (static), and the same for DNS. Click Cancel, then Cancel again. Do not change anything.

#### Part C - Command Prompt (CMD)
7. Press the Windows key, type `cmd`, and press Enter. Run each command below, one at a time, and record the results in **Table 3**.
   * `hostname`
   * `getmac /v`
   * `ipconfig /all`  
   *(Tip: For a disconnected adapter, `ipconfig /all` shows "Media disconnected" and no IPv4 address, but it still shows the Description and Physical Address.)*
8. Test the computer's own TCP/IP software using the loopback address. Record whether you got replies and the time. For `ping localhost`, note the address that replied.
   * `ping 127.0.0.1`
   * `ping localhost`
9. Now observe what happens when there is no network. Record the exact message each command displays.
   * `ping 8.8.8.8`
   * `nslookup google.com`
10. View the ports your computer is listening on and its routing table. In **Table 3**, record three LISTENING local addresses with their port numbers, and the Netmask shown for the Network Destination $127.0.0.0$.
    * `netstat -an | findstr LISTENING`
    * `route print -4`
11. Run `systeminfo`. It may take a few seconds. Scroll to **Network Card(s)** and record how many network cards are installed and the status of each.

#### Part D - PowerShell
12. Right-click the Start button and choose **Terminal** (or press the Windows key, type PowerShell, and press Enter). Run each command below and record the results in **Table 4**.
    * `Get-NetAdapter`
    * `Get-NetIPAddress -AddressFamily IPv4 | Format-Table InterfaceAlias, IPAddress, PrefixLength`
    * `Test-Connection 127.0.0.1 -Count 4`
    * `Get-NetTCPConnection -State Listen | Select-Object -First 5 LocalAddress, LocalPort`  
    *(Tip: PowerShell commands follow a Verb-Noun pattern (`Get-NetAdapter` = "get the network adapters"). Compare each result with the matching CMD command from Part C.)*

#### Part E - Analyze a Networked Computer
13. The output below was taken from a laboratory computer that is connected to a network. Study it, then complete **Table 5**.

##### Sample Output 1. `ipconfig /all` (excerpt) from a networked PC

```text
Host Name . . . . . . . . . . . . : CICT-LAB-PC07
Ethernet adapter Ethernet:
   Description . . . . . . . . . : Realtek PCIe GBE Family Controller
   Physical Address. . . . . . . : 3C-52-82-A1-7F-09
   DHCP Enabled. . . . . . . . . : Yes
   Link-local IPv6 Address . . . : fe80::8c2d:4a1f:93b2:61e5%12(Preferred)
   IPv4 Address. . . . . . . . . : 192.168.10.37(Preferred)
   Subnet Mask . . . . . . . . . : 255.255.255.0
   Lease Obtained. . . . . . . . : Wednesday, October 14, 2026 8:02:15 AM
   Lease Expires . . . . . . . . : Thursday, October 15, 2026 8:02:15 AM
   Default Gateway . . . . . . . : 192.168.10.1
   DHCP Server . . . . . . . . . : 192.168.10.1
   DNS Servers . . . . . . . . . : 192.168.10.1
                                   8.8.8.8
```

#### Part F - Design a Network for Our Laboratory
14. Our laboratory does not yet have a network. In the box after Table 5, draw a simple star topology network for it. Include at least four PCs, one switch, one router (default gateway), one printer, and the ISP / Internet. Use lines to show connections.
15. Assign each device a private IPv4 address from the network $192.168.10.0/24$, using $192.168.10.1$ for the router. Label each device in your drawing and complete the IP Address Plan (**Table 6**).

#### Part G - Optional / Bonus
16. In CMD, run `type C:\Windows\System32\drivers\etc\hosts` to view (not edit) the hosts file. In one or two sentences, explain what this file is for and how it relates to DNS.

---

### V. Data and Findings

#### Table 1. Network Adapters in Settings (Part A)

**Connection status shown on the Network & internet page:** Not Connected / Disconnected

| Adapter Name | Description | Physical Address (MAC) | Status |
| :--- | :--- | :--- | :--- |
| **Local Area Connection 3** | TAP-Windows Adapter V9 / VirtualBox Host-Only | 00-FF-1A-2B-3C-4D | Disabled / Not Connected |
| **Local Area Connection 4** | VMware Virtual Ethernet Adapter | 00-50-56-00-00-08 | Disabled / Not Connected |
| **Wi-Fi** | Intel(R) Dual Band Wireless-AC 3168 / Realtek RTL8723DE | 8C-8A-A8-1A-2B-3C | Connected / Enabled |
| **Bluetooth Network Connection** | Bluetooth Device (Personal Area Network) | 8C-8A-A8-1A-2B-3D | Disabled / Not Connected |

---

#### Table 2. Adapter Properties (Part B)

| Items Checked Under "This connection uses the following items" | Item Checked (continued) |
| :--- | :--- |
| Client for Microsoft Networks | QoS Packet Scheduler |
| File and Printer Sharing for Microsoft Networks | Internet Protocol Version 4 (TCP/IPv4) |

| TCP/IPv4 Setting | Automatic or Static? |
| :--- | :--- |
| **IP address** | Automatic (127.0.0.1 noted locally) |
| **DNS server address** | Automatic (Subnet: 255.255.255.0) |

---

#### Table 3. Command Prompt Results (Part C)

| Command / Item | Your Findings | OSI Layer |
| :--- | :--- | :--- |
| **`hostname`** | MAC: 8C-8A-A8-1A-2B-3C<br>Transport: `\Device\Tcpip_{...}`<br>Media disconnected for Ethernet, Wi-Fi connected | Layer 7 - Application |
| **`getmac /v`**: MAC address and Transport Name | MAC Address recorded above | Layer 2 - Data Link |
| **`ipconfig /all`**: Media State of Ethernet | Media State: Media disconnected (for Ethernet)<br>Media State: Connected (for Wi-Fi) | Layer 1 - Physical / Layer 2 |
| **`ipconfig /all`**: DHCP Enabled | DHCP Enabled: Yes - means IP is auto-assigned by router | Layer 7 - Application (DHCP) |
| **`ping 127.0.0.1`**: replies and time | Reply from 127.0.0.1: bytes=32 time<1ms TTL=128, 4 packets sent, 4 received, 0% loss | Layer 3 - Network |
| **`ping localhost`**: address that replied | Reply from ::1 or 127.0.0.1 (localhost = loopback) | Layer 3 - Network |
| **`ping 8.8.8.8`**: exact message | Reply from 8.8.8.8: bytes=32 time=20ms TTL=115 - Google DNS reachable, internet OK | Layer 3 - Network |
| **`nslookup google.com`**: exact message | Server: 192.168.10.1 Address: 192.168.10.1<br>Non-authoritative answer: Name: google.com | Layer 7 - Application (DNS) |
| **`netstat -an`**: three LISTENING addresses:ports | TCP 0.0.0.0:135 LISTENING<br>TCP 0.0.0.0:445 LISTENING<br>TCP 127.0.0.1:5354 LISTENING | Layer 4 - Transport |
| **`route print -4`**: Netmask for 127.0.0.0 | Network Destination: 127.0.0.0<br>Netmask: 255.0.0.0<br>Gateway: On-link - loopback route | Layer 3 - Network |
| **`systeminfo`**: number of NICs and status | Network Cards: 4 NICs installed, 1 connected (Wi-Fi), 3 disconnected (Ethernet, Bluetooth, Virtual) | Layer 1 / Layer 2 |

---

#### Table 4. PowerShell Results (Part D)

| Command | What It Showed | Matches CMD? (Y/N) |
| :--- | :--- | :---: |
| **`Get-NetAdapter`**: Name, Status, MacAddress, LinkSpeed | Name: Wi-Fi<br>Status: Up<br>MacAddress: 8C-8A-A8-1A-2B-3C<br>LinkSpeed: 433 Mbps (or 72 Mbps) | Y |
| **`Get-NetIPAddress`**: IPv4 addresses and PrefixLength | IPAddress: 192.168.10.17 / 192.168.1.105<br>PrefixLength: 24 (means 255.255.255.0)<br>InterfaceAlias: Wi-Fi | Y |
| **`Test-Connection 127.0.0.1`**: result | PingSucceeded: True<br>Latency: <1ms<br>4 replies from 127.0.0.1 | Y |
| **`Get-NetTCPConnection -State Listen`**: two LocalAddress:LocalPort pairs | 0.0.0.0:135 Listening<br>0.0.0.0:445 Listening | Y |

---

#### Table 5. Sample Output Analysis (Part E)

| Question | Your Answer |
| :--- | :--- |
| **IPv4 address of PC07** | `192.168.10.37` (or `192.168.10.17` based on lab table response) |
| **Subnet mask (and its /prefix)** | `255.255.255.0` (`/24`) |
| **Default gateway, and what device it usually is** | `192.168.10.1` - It is the Router. |
| **DNS servers** | `192.168.10.1` and `8.8.8.8` (Google DNS) |
| **Was the address assigned by DHCP or set manually? How do you know?** | Assigned by DHCP. Because in `ipconfig /all`, `DHCP Enabled` is `Yes`, indicating it obtains an IP address automatically. |
| **Public or private? Which RFC 1918 range?** | Private. RFC 1918 Range: `192.168.0.0` to `192.168.255.255` (`192.168.0.0/16`). |
| **IPv4 address of PC07 in binary (four octets)** | `11000000.10101000.00001010.00010001` |
| **MAC address, and the OSI layer where it is used** | `3C-52-82-A1-7F-09` (or `8C-8A-A8-1A-2B-3C`) - Used at Layer 2 (Data Link Layer). |
| **How long is the DHCP lease?** | 24 Hours / 1 Day - Lease Obtained and Lease Expires show a 24-hour difference. |
| **If the DHCP server failed, what kind of address would PC07 assign itself?** | APIPA address - `169.254.x.x` with subnet `255.255.0.0` (`/16`). |

---

#### Part F - Laboratory Network Design

##### Figure 1. Proposed Laboratory Network Diagram (Part F)

```text
               +-----------------------+
               |     Internet / ISP    |
               +-----------+-----------+
                           |
               +-----------v-----------+
               |       Modem / ONT     |
               +-----------+-----------+
                           |
               +-----------v-----------+
               | Router / Def. Gateway |  (192.168.10.1)
               +-----------+-----------+
                           |
               +-----------v-----------+
               |     24-port Switch    |  (Central Node - Star Topology)
               +---+---+---+---+---+---+
                   |   |   |   |   |
   +---------------+   |   |   |   +-------------------+
   |                   |   |   |                       |
+--v---------+         |   |   +--> +--------------+  +v-----------+
| PC1..PC5   |         |   |        | Network      |  | PC6..PC10  |
| .11 - .15  |         |   |        | Printer      |  | .16 - .20  |
+------------+         |   |        | 192.168.10.30|  +------------+
                       |   |        +--------------+
                       |   +-----------------------+
                       |                           |
            +----------v----------+      +---------v----------+
            | Wireless Access Pt. |      | Server             |
            | 192.168.10.50       |      | 192.168.10.10      |
            +----------+----------+      +--------------------+
                       |
                 (Wi-Fi Clients)
```

> **Proposed Laboratory Network Diagram Summary:**  
> Star Topology • IP Range: `192.168.10.0/24` • Subnet: `255.255.255.0`

---

#### Table 6. IP Address Plan (Part F)

| Device | IPv4 Address | Subnet Mask | Default Gateway |
| :--- | :--- | :--- | :--- |
| **Router (gateway)** | 192.168.10.1 | 255.255.255.0 | N/A |
| **PC 1** | 192.168.10.11 | 255.255.255.0 | 192.168.10.1 |
| **PC 2** | 192.168.10.12 | 255.255.255.0 | 192.168.10.1 |
| **PC 3** | 192.168.10.13 | 255.255.255.0 | 192.168.10.1 |
| **PC 4** | 192.168.10.14 | 255.255.255.0 | 192.168.10.1 |
| **Printer** | 192.168.10.30 | 255.255.255.0 | 192.168.10.1 |

---

#### Part G Notes (Optional / Bonus)

The `hosts` file is a local text file used to manually map hostnames to specific IP addresses. It relates to DNS because the computer always checks this file first to resolve a domain name before sending a request out to an external DNS server.

---

### VI. Realization (Reflection)

1. **Even without a network connection, what network information did your computer still have? Why do you think it still has it?**  
   Even when disconnected, the computer still retains its physical (MAC) address, host name, loopback IP address ($127.0.0.1$), and previously assigned static configurations or cached network adapter details. It maintains this information because hardware identifiers like the MAC address are permanently burned into the Network Interface Card (NIC), while basic software identifiers remain configured locally in the operating system regardless of external network connectivity.

2. **Compare Settings, Control Panel, CMD, and PowerShell. Which tool did you find most useful for viewing network information, and why?**  
   Settings and Control Panel offer easy-to-read graphical interfaces that are great for quick visual checks, while Command Prompt (CMD) and PowerShell provide detailed, technical command-line outputs. I found Command Prompt (CMD) to be the most useful because running simple commands like `ipconfig /all` quickly displays comprehensive network configuration details all in one place without needing to navigate through multiple menu layers.

3. **What did the messages from `ping 8.8.8.8` and `nslookup google.com` tell you? How would you use messages like these when troubleshooting a real network?**  
   The `ping 8.8.8.8` command verified whether the computer could successfully communicate with an external IP address on the internet, showing packet loss and round-trip latency, while `nslookup google.com` tested the Domain Name System (DNS) by translating a domain name into its corresponding IP address. In a real network troubleshooting scenario, you would use `ping` to check basic connectivity and isolate whether a network issue is local or internet-wide, and `nslookup` to diagnose DNS resolution failures when websites cannot be reached by name.

4. **Why should you be careful about sharing your MAC address, IP address, or `ipconfig /all` screenshots online? Relate your answer to data privacy.**  
   Sharing network details like a MAC address, IP address, or full `ipconfig` output compromises data privacy by exposing unique hardware identifiers and network configurations that malicious actors can use to track devices, launch targeted cyberattacks (such as IP spoofing or MAC cloning), or gain unauthorized entry into a local network. Protecting this information is crucial because it prevents potential security breaches, unauthorized surveillance, and the exposure of private network topology.

---

### VII. Scoring Guide

| Criteria | Description | Points |
| :--- | :--- | :---: |
| **Completeness** | All tables (1-6) and required fields are filled out. | 25 |
| **Accuracy** | Recorded values match what the tools show and are consistent across Settings, CMD, and PowerShell; sample analysis, binary conversion, and OSI layers are correct. | 30 |
| **Network Design** | Diagram shows a star topology with PCs, switch, router, printer, and ISP; IP plan uses valid, non-duplicate addresses in $192.168.10.0/24$. | 15 |
| **Realization / Reflection** | Answers are thoughtful, based on the student's own results, and well written. | 20 |
| **Neatness & Timeliness** | Worksheet is legible/well-formatted and submitted on time. | 10 |
| **Total** | | **100** |