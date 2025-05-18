# Network Troubleshooting:
### using ping, dig, traceroute and nslookup!

---

## Tool 1: nslookup (google.com)

nslookup (short for name server lookup) is a effective command-line tool that lets you query DNS to find the IP address associated with a domain name—or vice versa.



https://github.com/user-attachments/assets/7a9f9665-d7cb-46c3-bce0-7f4c0fdf4509

---

1. Server: 127.0.0.53
  - This indicates that your local system is querying the DNS server at the IP address 127.0.0.53. This is typically a local DNS resolver, often used in systems that have DNS        caching or are using systemd-resolved in Linux distributions.

2. Address: 127.0.0.53#53
  - This shows the IP address of the DNS server (127.0.0.53) and the port (#53, which is the standard DNS port) that the query was sent to.

3. Non-authoritative answer:
  - This means that the response is not coming directly from the DNS server that holds the authoritative information for google.com. Instead, it's coming from a cache or             another server.

4. Name: google.com
  - This shows the domain name you queried: google.com.

5. Address: 142.250.200.14
  - This is the IPv4 address for google.com. It's the address used to reach Google's servers.

6. Address: 2a00:1450:4009:81f::200e
  - This is the IPv6 address for google.com, a newer version of IP addresses that allows for a larger number of unique addresses compared to IPv4.


## Advantages: 
  - Verify if a domain is resolving properly: Quickly check if DNS is working for a given domain.
  - Identify the DNS server being used: Useful for diagnosing local DNS configuration issues.
  - Test external DNS servers: You can specify a custom DNS server by adding it after the domain:

---

## Tool 2: dig (Domain Information Groper)
dig is a more advanced tool for querying DNS, offering greater detail and flexibility than nslookup. It's widely used by network engineers for in-depth DNS analysis.



https://github.com/user-attachments/assets/b6255f35-b61d-401d-b3a4-bc735338abec

---

1. The dig command queried for the IPv4 address of google.com and received the address 142.250.200.14.
  - The query made: For the A record (IPv4 address) of google.com.

3. The query was handled by a DNS server at 127.0.0.53 Ip address of the local resolver (your router), and the response took 1 milliseconds.

4. The A record (IPv4 address) for google.com was returned with a TTL of 6 seconds.
  - google.com. — The domain name queried.
  - 299 — Time to live (TTL) in seconds. How long this result is valid for before it should be queried again.
  - IN — Internet class.
  - A — Type of record (IPv4 address).
  - 142.250.200.14 — The actual IPv4 address of google.com.

## Advantages:

1. Detailed Output:
  - Unlike nslookup, dig provides more detailed information, including query time, server used, and response sections (like the Answer, Authority, and Additional sections). This     helps in diagnosing DNS issues more thoroughly.

2. Flexibility:
  - dig allows for advanced queries (like specifying record types—A, MX, TXT, etc.), enabling you to target specific information and perform detailed troubleshooting.

3. No Caching:
  - By default, dig bypasses local caches and directly queries DNS servers, ensuring that you get real-time data. This is useful when you want fresh or unmodified DNS results.

4. Verbose and Customizable:
  - You can customize the level of detail shown in dig's output using options like +short, +trace, and +stats, making it versatile for different levels of troubleshooting.

5. Traceability:
  - The +trace option lets you trace the DNS query path from root to authoritative servers, which helps in identifying where the problem lies in the DNS resolution chain.

6. Cross-platform:
  - dig is available on most Unix-like systems and can be installed on others, making it a widely accessible tool for network professionals.

7. Scriptable:
  - Since dig outputs data in a machine-readable format, it can be easily used in scripts for automated DNS checks or monitoring.

---

## Tool 3: ping – Connectivity & Latency Checker
ping is used to test if a target host is reachable and how long it takes for packets to travel to it and back (round-trip time).


https://github.com/user-attachments/assets/f4ca2f90-f30f-41fc-a9cb-d90b25cabe2d

---

1. Initiation – Send ICMP Echo Requests:
  - When you run the ping command, your computer sends a series of ICMP (Internet Control Message Protocol) Echo Request packets to the target host **(from our example google.com with its IP address 216.58.204.78)**

2. Response – Await ICMP Echo Replies
  - If the target host is reachable and configured to respond to ICMP, it replies with ICMP Echo Reply packets.
      - If replies are received: the host is online.
      - If no replies are received: the host may be down, unreachable, or blocking ICMP.

3. Latency Measurement – Track Round-Trip Time
  - Each successful reply includes a time value, showing how long (in milliseconds) it took for the packet to travel to the host and back.
      - Low time = fast connection
      - High time = possible congestion or delay

4. Packet Loss Analysis
  - ping shows how many packets were sent and received. From this, it calculates packet loss.
      - 0% loss = ideal
      - Any loss = potential network instability


## Advantages of Using ping:
  - Quickly verifies connectivity to a server or device.
  - Measures network latency (how fast packets travel).
  - Detects packet loss, helping identify unstable connections.
  - Simple to use, available by default on most OS platforms.
  - Lightweight and fast, with minimal overhead.
  - Helps isolate issues (e.g., unreachable host vs. DNS issue).


`⚠️ Note: Some servers block ICMP ping requests (e.g., ping google.com may not always succeed).`

---

## Tool 4: traceroute – Trace Network Path
traceroute (or tracert on Windows) helps you understand the route your data takes across the internet, hop by hop.



https://github.com/user-attachments/assets/1a7ec9a7-fca9-4df2-ae29-92d793705887

---

1. Send Probing Packets with Increasing TTL
  - traceroute sends packets with a gradually increasing Time-To-Live (TTL) value, starting from 1. Each hop along the path reduces TTL by 1.

2. Receive ICMP "Time Exceeded" Responses
  - When a packet's TTL expires at a router, that router sends back a "Time Exceeded" ICMP message, revealing its IP and latency.

3. Repeat Until Destination Is Reached
  - The process continues until the packet reaches the final destination, which replies with a different ICMP message (or completes the route).

4. Record Each Hop’s IP Address and Response Time. **(from our example google.com with its first hope IP address 142.250.200.14)**
  - traceroute displays the path the packet takes, hop-by-hop, including the IP addresses and response times for each router.

## Advantages of Using traceroute:
  - Maps the exact path data takes from your device to the destination.
  - Identifies slow or failing hops (routers with high latency or no response).
  - Pinpoints where network issues occur, such as timeouts or routing failures.
  - Helps differentiate local vs. remote issues (e.g., home router vs. ISP vs. destination server).
  -  Visualizes network performance, useful for diagnostics and reporting.
    
---

## Summary Table

  - **nslookup** -	Basic DNS lookup	Quick checks of IP/domain mapping
  - **dig**	- Advanced DNS query	Detailed DNS troubleshooting
  - **ping** - Connectivity check	Checking if a host is reachable
  - **traceroute**	- Trace path of data across network	Finding slow or failed hops

---

## Crucial Tips:

1. Use ping and traceroute together: ping tells you if a host is reachable, traceroute shows where the path is breaking.
2. Use dig instead of nslookup for scripting or detailed inspection.
3. Combine DNS and network tools to diagnose issues more effectively.

---

## Example Workflow:

A website is not loading. \
First, use ping to check reachability. \
If it fails, try traceroute to locate the failure point. \
If it loads slowly or incorrectly, use nslookup or dig to verify the DNS is resolving correctly.
