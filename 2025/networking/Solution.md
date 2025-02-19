# **Week 1: Networking Challenge Solution**  

## **Task 1: Real-World Applications of Each Layer in Networking**  
Check out my article on [Hashnode](https://day1-of-90-days-devops-challenge.hashnode.dev/networking-understanding-the-foundations-of-modern-connectivity).  

---  
## **Task 2: Explanation of Networking Protocols in DevOps**  
I have covered these topics in my article 

---  
## **Task 3: Guide on Creating and Configuring Security Groups**  
This will be covered in the upcoming weeks.  

---  
## **Task 4: Networking Commands Cheat Sheet**  

### **1️⃣ `ping` - Check Network Connectivity**  
The `ping` command sends **ICMP Echo Requests** to a target to check if it’s reachable.  

#### **Example Usage:**  
```sh
ping google.com
```  
#### **Scenario: Checking Internet Connectivity**  
If you’re experiencing issues loading websites, test your network connection:  
```sh
ping 8.8.8.8
```  
- If you receive replies → The internet is working fine.  
- If you get timeouts → There's a network issue.  

---  
### **2️⃣ `traceroute` / `tracert` - Trace Network Route**  
- **Linux/macOS:** `traceroute`  
- **Windows:** `tracert`  

This command **traces the path** packets take from your system to a destination, showing routers (hops) along the way.  

#### **Example Usage:**  
```sh
traceroute google.com    # Linux/macOS
tracert google.com       # Windows
```  
#### **Scenario: Debugging Slow Internet Issues**  
If a website is **loading slowly**, but `ping` works fine, use `traceroute` to check where the delay occurs:  
```sh
traceroute example.com
```  
- If timeouts or high latency appear at a hop, that router may be causing delays.  

---  
### **3️⃣ `netstat` - View Network Connections**  
The `netstat` command displays **active network connections, ports, and listening services**.  

#### **Example Usage:**  
```sh
netstat -tulnp    # Linux (shows listening ports)
netstat -ano      # Windows (shows active connections)
```  
#### **Scenario: Checking Which Ports Are in Use**  
To check if a web server is running on port 80:  
```sh
netstat -tulnp | grep :80   # Linux
netstat -ano | findstr :80  # Windows
```  
- If the port **isn't listed**, the server is not running.  
- If the port **is occupied by another process**, you may need to stop that process.  

---  
### **4️⃣ `curl` - Fetch Data from URLs**  
`curl` is essential for interacting with APIs, testing services, debugging network issues, and automating deployments.  

#### **Example Usage:**  
```sh
curl example.com  # Performs GET request
curl -i https://example.com  # Includes response headers
curl -I https://example.com  # HEAD request (headers only)
curl -o page.html https://example.com  # Save response to file
curl -L http://apple.com  # Follow redirects
curl -u username:password https://api.example.com/secure-data  # Basic auth
```

#### **Scenario: Testing API Responses**  
Fetch JSON data and pretty-print it using `jq`:  
```sh
curl https://jsonplaceholder.typicode.com/users | jq
```

---  
### **5️⃣ `dig` / `nslookup` - Query DNS Information**  
- **Linux/macOS:** Use `dig`  
- **Windows:** Use `nslookup`  

These commands query **DNS records** to find IP addresses, domain details, and troubleshoot name resolution.  

#### **Example Usage:**  
```sh
dig google.com       # Linux/macOS
nslookup google.com  # Windows
```  
#### **Scenario: Checking Domain Name Resolution**  
If your app fails to connect to `api.example.com`, check DNS resolution:  
```sh
dig api.example.com
nslookup api.example.com
```  
- If no IP is returned → The **DNS server might be down**.  
- If the IP is incorrect → The **DNS configuration might be wrong**.  

---  
### **References**  
- [curl man page](https://linux.die.net/man/1/curl)  
- [curl tutorial on FreeCodeCamp](https://youtu.be/I6id1Y0YuNk?si=c-HXQzcHF-NU4Jfb)
