# Network Troubleshooting:
### using ping, dig, traceroute and nslookup!

---

## Tool 1: nslookup (google.com)

nslookup (short for name server lookup) is a effective command-line tool that lets you query DNS to find the IP address associated with a domain name—or vice versa.

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


## Use Cases for nslookup:
  . Verify if a domain is resolving properly: Quickly check if DNS is working for a given domain.
  . Identify the DNS server being used: Useful for diagnosing local DNS configuration issues.
  . Test external DNS servers: You can specify a custom DNS server by adding it after the domain:


## Tool 2: dig (Domain Information Groper)
dig is a more advanced tool for querying DNS, offering greater detail and flexibility than nslookup. It's widely used by network engineers for in-depth DNS analysis.

1. The dig command queried for the IPv4 address of google.com and received the address 142.250.200.46.

2. The query was handled by a DNS server at 127.0.0.53 (likely a local resolver), and the response took 17 milliseconds.

3. The A record (IPv4 address) for google.com was returned with a TTL of 58 seconds, meaning the result is valid for 58 seconds before it needs to be refreshed.

## key advantages of using dig for network troubleshooting:

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

## Summary:
Whether you're just starting out or diving deep into network troubleshooting, mastering nslookup and dig can save you hours of head-scratching. Use nslookup when you need a fast, readable answer. Use dig when you need the full picture.

## Pro Tip: 
Combine these tools with traceroute or ping to get an even clearer understanding of where your network issues might lie.



## Tool 3: ping – Connectivity & Latency Checker
ping is used to test if a target host is reachable and how long it takes for packets to travel to it and back (round-trip time).



🛠️ Use Cases
Verify if a host or server is online

Measure network latency

Identify packet loss or high latency, which may suggest issues in your connection

⚠️ Note: Some servers block ICMP ping requests (e.g., ping google.com may not always succeed).



## Tool 4: traceroute – Trace Network Path
traceroute (or tracert on Windows) helps you understand the route your data takes across the internet, hop by hop.


### Output Breakdown:
Each hop represents a router the packet travels through.

Shows IP addresses and latency times at each hop.

Helps locate where delays or failures occur.

### Use Cases:
Diagnose network routing issues

Identify where slowdowns are happening (e.g., at your ISP or further downstream)

Detect unreachable hops or firewalls

---

## Summary Table

Tool	Purpose	Best For:
nslookup -	Basic DNS lookup	Quick checks of IP/domain mapping
dig	- Advanced DNS query	Detailed DNS troubleshooting
ping - Connectivity check	Checking if a host is reachable
traceroute	- Trace path of data across network	Finding slow or failed hops

## Pro Tips
Use ping and traceroute together: ping tells you if a host is reachable, traceroute shows where the path is breaking.

Use dig instead of nslookup for scripting or detailed inspection.

Combine DNS and network tools to diagnose issues more effectively.

## Example Workflow:
A website is not loading. First, use ping to check reachability. \
If it fails, try traceroute to locate the failure point. If it loads slowly or incorrectly, use nslookup or dig to verify the DNS is resolving correctly.
