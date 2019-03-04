![alt text](https://github.com/LiYangHart/SDP_images/blob/master/Software-Defined-Perimeter-Market.png) 
## What is SDP?
Software defined perimeter [SDP](https://sdn.ieee.org/newsletter/march-2017/software-defined-perimeters-an-architectural-view-of-sdp) is a new approach for securing access to business applications. emerging along side other virtualization networking technichues such as SDN and NFV. It’s become particularly important as mobile users access cloud-based applications.

## Motivation  


### Precursors
![alt text](https://github.com/LiYangHart/SDP_images/blob/master/ZeroTrust%20arch.jpg) 

Conventional security models operate on the outdated assumption that everything on the inside of an organization’s network can be trusted, but given increased attack sophistication and insider threats, new security measures needed to be taken to stop them from spreading once inside. Introducing the concept of [Zero Trust](https://www.paloaltonetworks.com/cyberpedia/what-is-a-zero-trust-architecture) a new movment that introduced SDP as one of the solutions.

### Overcoming VPN shortcomings

Enterprises have long relied on virtual private networks (VPNs) to connect mobile or remote users to applications and other network resources. But, traditional VPNs are poorly suited for the shift to IaaS and SaaS. They rely on appliances, such as firewalls or VPN concentrators, binding mobile users to specific locations. Such an architecture adds latency and creates a chokepoint for cloud access. And, to even reach the VPN gateways, users must rely on the unpredictable Internet. Once connected through a VPN, users are trusted with access to all resources on the network, increasing the risk of malware propagation and data breach. Overall, legacy VPN architectures expose enterprise to attacks and adversely impact the user experience, especially when accessing cloud applications.





## Advantages of SDP
SDP reduces risk by restricting network access to authorized resources. Most SDP point-solutions fail to address mobile performance problems, especially for global access. They also fail to continuously inspect traffic to application resources for threats post authentication. And they introduce management and deployment complexity, requiring additional server software, network appliances, or cloud services.
SDP as a service (also known as cloud-based SDP) delivers secure mobile access as integral part of a company’s global network. Performance improves with direct, optimized access across a managed, cloud-based SD-WAN. Risk is minimized before and after users access the network through strong authentication and continuous traffic inspection. SDP as a service makes mobile access easy — easy to deploy, easy to use, and easy to secure.



### Types of attacks SDP protects against 
<img src="https://github.com/LiYangHart/SDP_images/blob/master/insta002.gif" width="500" height="400" />

1. _Server exploitation_
-	Server misconfigurations
-	Server vulnerabilities 
-	Injection
-	Denial of service
<img src="https://github.com/LiYangHart/SDP_images/blob/master/insta1.gif" width="500" height="400" />


2. _Credential theft_
-	Phishing 
-	Key loggers
-	Brute force

<img src="https://github.com/LiYangHart/SDP_images/blob/master/insta.gif" width="500" height="400" />

3. _Connection hijacking_
-	Man in the middle 
-	Certificate forgery 
-	DNS poisoning

### Security tools adopted by SDP core 
1. _Server exploitation_
-	Server isolatioon
-	SPA
-	Dynamic FW
2. _Credential theft_
-	Transparent MFA 
-	mTLS 
-	Fingerprint
3. _Connection hijacking_
-	Encryption
-	Pinned Certificates
-	NO DNS







 
## Security importance
Nowadays, more than ever, business and the society as a whole are linked to computer technology in multiple ways, and are therefore also strongly affected by its malfunctions and security breaches. Poor security practices may cost firms huge amounts of money. They can also have a severe impact on human activities or even human lives.

According to SafeNet 2014 Survey, although 74% of IT decision-makers trust their organization’s perimeter security, yet about half (44%) of them admitted that their perimeter has been breached or did not know if it had been breached. With cyber-attacks on the rise, the cost of IT security is becoming an increasingly heavy burden for every organization. According to the latest Gartner report, the worldwide spending on information security was $75.4 billion in 2015, which will jump to $101 billion in 2018 and soar to $170 billion by 2020.

Generally, networks are vulnerable to many regular networking threats. These attacks may extend from the local networks to other connected networks, for example financial networks may extend to personal home networks. The attackers manage to get access to devices interconnected with our daily physical activities: web cameras, security locks, university appliances - in other words, Internet of Things (IoT) devices. 17420The attackers collects important information from various ways such as the open ports, message types and applications running. Each device or service in the network is a potential entry point for cyber attackers.  All these reasons call for a strong protection system that can repel possible attacks that pose threats to networks.




































## Potential Applications and Users
Since the [SDP architecture][1] can be implemented in client-to- gateway, client-to-server, server-to-server, and client-to-server-to-client , so it can be used for numerous applications. It would become popular in enterprises to protect the Internal Enterprises Networks. 

[Virtual private networks (VPN)](https://en.wikipedia.org/wiki/Virtual_private_network) have provided secure access to virtual local area networks for remote users. However, it is out-of-date since it was designed for the 1990s networks and lack of agility. 

On the contrary, an SDP framework allows organizations and enterprises to keep cloud resources dark to unauthorized users. This helps protect against a variety of attacks including network flood attacks, brute-force attacks, and TLS vulnerabilities. Hence, by having a “dark net” around the servers, an SDP framework can facilitate the management and security of organizations’ cloud resources. Therefore, SDP can provide an ideal VPN solution for any size organization as it provides cloud-based controllers, gateways, and up-to-date software defined security perimeters to deliver secure, dynamic virtual connectivity. 
Therefore, SDP is an alternative to VPN for internal enterprise networks and more and more applications show that it shows better performance than VPN.

[1]: https://downloads.cloudsecurityalliance.org/initiatives/sdp/SDP_Specification_1.0.pdf

## SDP Architecture
The SDP architecture is composed of and relies on five separate security layers [[SDP]](https://downloads.cloudsecurityalliance.org/initiatives/sdp/Software_Defined_Perimeter.pdf) [[Understanding SDP]](https://digital-library.theiet.org/content/books/10.1049/pbse007e_ch7): 

1)	Single Packet Authentication (SPA): SPA is the basic of device authentication. The SDP uses the SPA to reject traffic to it from unauthorized devices. The first packet is cryptographically sent from the client’s device to the SDP controller where the device’s authorization is verified before giving it access. The SPA is then again sent by the device to the gateway to help it determine the authorized device’s traffic and reject all other traffic.

2)	Mutual Transport Layer Security (mTLS): Transport layer security (TLS) is used to provide secure communication over the Internet. It has typically only been used to authenticate servers to clients (client-to-server communications). However, the SDP utilizes mutual TLS standard to enable mutual two-way cryptographic authentication between each other.

3)	Device Validation (DV): Device validation ensure that the cryptographic key used is held by the proper device by performing Multi-Factor Authentication (MFA). This is because mTLS only proves that the key has not expired nor has it been revoked. However, it cannot prove that it has not been stolen. Therefore, DV ensures that the device is running the trusted software and belongs to the authorized users.

4)	Dynamic Firewalls (DF): Traditional static firewalls that can have hundreds or thousands of rules and implement generalized rules. On the other hand, dynamic firewalls have one constant rule to deny all connections. The major benefit of this is that in this age of rapidly expanding mobile and IoT devices, it allows to dynamically extend the perimeter to allow connections from these devices.

5)	Application Binding (AppB): Each connection is bound to a particular application in SDP. Application binding creates an encrypted TLS tunnel through an application-binding layer. Then it forces authorized applications to use the encrypted TLS tunnels. This is done after the device and the user are properly authenticated and authorized. This ensures that only authorized applications can communicate through the tunnels while unauthorized ones are blocked.

After combining these security layers and protocols, it becomes extremely difficult for malicious users and attackers to access protected applications and services.

## SDP Components
The SDP framework’s architecture consists of three main components [[SDP]](https://downloads.cloudsecurityalliance.org/initiatives/sdp/Software_Defined_Perimeter.pdf) [[Understanding SDP]](https://digital-library.theiet.org/content/books/10.1049/pbse007e_ch7):

a)	Controller: The SDP controller is the central element in the SDP framework. It is responsible for records of authorized hosts and services and passing on this information to the gateway. This includes issuing certificates and authenticating devices (both initiating and accepting hosts). It use a database to keep those information. The database consists of a variety of tables, mainly including “sdpid” to contain the informations of the components of SDP, “service” to provide the services that will be protected by SDP, “service gateway” to define the gateways for protecting a service and “sdpid service” to show the mapping of service IDs, and the port and protocol numbers of services. 

b)	Client/Initiating Host (IH): SDP Initiating Hosts are the SDP-enabled clients that send a request to connect to a service. This request will be sent the SDP controller and then will be authenticated by the information about hardware or software within the IH. Once authentication using the previously issued certificate, a mutual TLS tunnel is created that connects the IH to the server or application for which it has authorization. Since the IH only gets access to the server after being authenticated, it is beneficial for access control.

c)	Gateway/Accepting Hosts (AH): After the SDP controller provides the gateway with the verified and authenticated IH’s IP address and certificates, then the gateway acts as a filter to prevent all the unauthorized traffic to protect the service. The SDP Accepting Host (AH) is the device instructed to accept authorized services and may contain the gateway. It is originally set up to reject all incoming packets and requests from all hosts except the SDP controller.

 
## SDP Working Procedure
The whole process of SDP consists of the following steps: [[Build SDP]](http://ir.lib.uth.gr/bitstream/handle/11615/48775/17420.pdf?sequence=2&isAllowed=y)
1)	The gateway initiates a TLS connection to the controller, and the controller verifies the gateway by using a certificate.

2)	A connection between the controller and the gateway is establishes and the controller send all the information about IHs and AHs to the gateway as authorized users and services.

3)	The clients initiates a TLS connection to the controller. The controller may use a variety of authentication, authorization and access control services (Location service, MFA, IdP service, PKI service), to verify the clients that send requests to have access to services.

4)	Once the controller authenticates an IH, it selects which appropriate servers can provide the required service to the IH and which AHs they belong to.

5)	The client sends a SPA to the gateway and the decrypted packet is crosschecked. If passed, the gateway sets up the corresponding firewall rules

6)	The AHs are required to connect to the controller and send identification information for authentication. Accepting hosts communicate with the controller but do not respond to any other unauthenticated entity. 

7)	The SDP controllers inform AHs to accept connection from the authorized IH.

8)	The gateway allows the connection request to pass and the IH starts to communicate with AHs by establishing a mutual TLS connection with each AH to perform secure communication.

 
## SDP Simulation
If you want to simulate SDP on your own devices, [Waverly Labs’ OpenSDP project](https://www.waverleylabs.com/open-source-sdp/) is a good open-source resource to implement the proposed framework with components being programmed using C, Python, and NodeJS.

As mentioned earlier SDP consists of 3 main components: controller, gateway and client. Each component can be set up on a separate virtual machine by using [Oracle Virtualbox](https://www.virtualbox.org/). The code can be found in WaverleyLabs’ Github, [WaverleyLabs/SDPcontroller](https://github.com/WaverleyLabs/SDPcontroller) can be used to simulate the controller, while “WaverleyLabs/fwknop”(https://github.com/WaverleyLabs/fwknop) can be used to simulate gateway and client. 

In addition, another virtual machine can be set up as an unauthorized client or attacker. Several attacks can be simulated to test the utility of SDP. For example, [Hping3](http://www.hping.org/download.php) is a popular tool to simulate the DoS (Denial of Service) attacks, such as SYN flood attack. For port scanning attacks, [Nmap](https://nmap.org/download.html) is mainly used for network discovery and security auditing. Besides, the network traffic can be monitored by [Wireshark](https://www.wireshark.org/download.html) to check the network condition of using SDP or without SDP.
For testing SDP, here we mainly simulate two types of cyber-attacks: DoS and port scanning, and the network throughput is our main metric. 
#### (1)	SYN flood attack
[Denial-of-service attack (DoS attack)](https://en.wikipedia.org/wiki/Denial-of-service_attack) is a common cyber-attack that is typically accomplished by flooding the targeted machine or resource with superfluous requests in an attempt to overload systems and prevent some or all legitimate requests from being fulfilled.

SYN flood attack is a typical type of DoS attack. It occurs in TCP connections, the attackers send a variety of SYN (synchronize) requests to a target system or server without responding to the server without the expected ACK (acknowledge) code, which will result in the lack of resources. 

A simulation demo can be seen on [Waverleylabs’  OpenSDP Demo](http://www.waverleylabs.com/open-source-sdp/demo/). In normal traffic flows, when one authorized user makes a request, the complete requests would be 100%, and the transfer rate is about 14.2 kbytes/sec.

![alt text](https://github.com/LiYangHart/SDP_images/blob/master/dos_normal.jpg) 

Then we initiate a SYN flood attack without using SDP.

![alt text](https://github.com/LiYangHart/SDP_images/blob/master/syn.jpg) 

Most of the times, there would be no traffic can get through. Sometimes there would be a little bit good traffic to go through, but only half the normal transfer rate.

![alt text](https://github.com/LiYangHart/SDP_images/blob/master/without_1.jpg) 

![alt text](https://github.com/LiYangHart/SDP_images/blob/master/without_2.jpg) 

When using SDP, almost all the requests can be completed, and traffic speed is close to the normal speed. Therefore, the impact of SYN flood attack to SDP platform is very limited.

![alt text](https://github.com/LiYangHart/SDP_images/blob/master/with.jpg) 

The results can be also seen in the table.

|Type | Normal |SYN flood with SDP |SYN flood without SDP |
|-------------|-------------|-------------|-------------|
| Connection Setup Time (s)| 0.09 | 0.09 | 1.02 |
| Network Throughput| 14.2 Kbps | 12.8 Kbps | 7.6 Kbps |
| Complete requests percentage | 100% | 95% | 5% |

#### (2)	Port scanning attack
Another simulated attack is the port scanning attack. It is an attack that sends requests and list all the available ports to discover the hosts and services on a network and exploit vulnerabilities. Many other types of cyber-attacks may be conducted after port scanning.
In the experiments, Nmap is used to simulate port scanning and the scan ran on ports 1-1000, covering some of the more important services such as HTTP, FTP, SSH etc.
![alt text](https://github.com/LiYangHart/SDP_images/blob/master/port_without.jpg)    
Without SDP

![alt text](https://github.com/LiYangHart/SDP_images/blob/master/port_with.png)  
With SDP

From the results, it can be seen that without SDP, the scan report shows that an SSH connection is open and available. On the other hand, when with SDP, it doesn’t give any information about the open ports and the service hosted on them. This is because when using SDP, the resources and ports are hidden to any unauthorized users. Therefore, the ports information cannot be scanned by them. 

Overall, using a SDP framework can improve the network’s resiliency to various cyber-attacks such as DoS and port scanning attacks.
