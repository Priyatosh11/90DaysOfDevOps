Week 1: Networking Challenge Solution
Task 1: Write examples of how each layer applies to real-world scenarios
Checkout this article written by me on hashnode .

Task 2: Create a blog, article, GitHub page, or README listing these protocols and explaining their relevance to DevOps workflows.
Checkout this article written by me on hashnode .

Task 3: Write a step-by-step guide or blog on how to create and configure Security Groups.
Would be covered in the upcoming weeks.

Task 4: Create a cheat sheet or short guide explaining the purpose and usage of Networking Commands
1️⃣ ping - Check Network Connectivity

The ping command sends ICMP Echo Requests to a target to check if it’s reachable.

Example Usage:
ping google.com
Scenario: Checking Internet Connectivity
We’re having trouble loading websites. To check if our internet connection is working, run:

ping 8.8.8.8
If replies come back → The internet is fine.
If no replies (timeout) → We have a network issue.
2️⃣ traceroute / tracert - Trace Network Route

Linux/macOS: traceroute
Windows: tracert
This command traces the path packets take from our system to a destination, showing the routers (hops) along the way.

Example Usage:
traceroute google.com    # Linux/macOS
tracert google.com       # Windows
Scenario: Debugging Slow Internet Issues
Our website is loading slowly, but ping works fine. Run traceroute to check where the delay occurs:

traceroute example.com
If we see timeouts or high latency at a particular hop, that router may be causing delays.

3️⃣ netstat - View Network Connections

The netstat command shows active network connections, ports, and listening services.

Example Usage:
netstat -tulnp    # Linux (shows listening ports)
netstat -ano      # Windows (shows active connections)
Scenario: Checking Which Ports Are in Use
You suspect that your web server isn't running on port 80. Run:

netstat -tulnp | grep :80   # Linux
netstat -ano | findstr :80  # Windows
If the port isn't listed, the server is not running.
If the port is occupied by another process, you may need to stop that process.
Flags Explained:
-t: shows only active TCP connections (excluding UDP).

-u: shows only active UDP connections

-l: shows listening ports (i.e. services actively listening for connections).

-n: Displays IP addresses and port numbers instead of resolving them into hostnames and service names. E.g. localhost:http is displayed as 127.0.0.1:80

-p: Displays the process (PID) and program name using each port.
