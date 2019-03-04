Potential Applications and Users
Since the SDP architecture can be implemented in client-to- gateway, client-to-server, server-to-server, and client-to-server-to- client, so it can be used for numerous applications. It would become popular in enterprises to protect the Internal Enterprises Networks. 
	Virtual private networks (VPN) have provided secure access to virtual local area networks for remote users. However, it is out-of-date since it was designed for the 1990s networks and lack of agility. 
On the contrary, an SDP framework allows organizations and enterprises to keep cloud resources dark to unauthorized users. This helps protect against a variety of attacks including network flood attacks, brute-force attacks, and TLS vulnerabilities. Hence, by having a “dark net” around the servers, an SDP framework can facilitate the management and security of organizations’ cloud resources. Therefore, SDP can provide an ideal VPN solution for any size organization as it provides cloud-based controllers, gateways, and up-to-date software defined security perimeters to deliver secure, dynamic virtual connectivity. 
Therefore, SDP is an alternative to VPN for internal enterprise networks and more and more applications show that it shows better performance than VPN.
 
SDP Architecture
The SDP architecture is composed of and relies on five separate security layers: [U]
1)	Single Packet Authentication (SPA): SPA is the basic of device authentication. The SDP uses the SPA to reject traffic to it from unauthorized devices. The first packet is cryptographically sent from the client’s device to the SDP controller where the device’s authorization is verified before giving it access. The SPA is then again sent by the device to the gateway to help it determine the authorized device’s traffic and reject all other traffic.
2)	Mutual Transport Layer Security (mTLS): Transport layer security (TLS) is used to provide secure communication over the Internet. It has typically only been used to authenticate servers to clients (client-to-server communications). However, the SDP utilizes mutual TLS standard to enable mutual two-way cryptographic authentication between each other.
3)	Device Validation (DV): Device validation ensure that the cryptographic key used is held by the proper device by performing Multi-Factor Authentication (MFA). This is because mTLS only proves that the key has not expired nor has it been revoked. However, it cannot prove that it has not been stolen. Therefore, DV ensures that the device is running the trusted software and belongs to the authorized users.
4)	Dynamic Firewalls (DF): Traditional static firewalls that can have hundreds or thousands of rules and implement generalized rules. On the other hand, dynamic firewalls have one constant rule to deny all connections. The major benefit of this is that in this age of rapidly expanding mobile and IoT devices, it allows to dynamically extend the perimeter to allow connections from these devices.
5)	Application Binding (AppB): Each connection is bound to a particular application in SDP. Application binding creates an encrypted TLS tunnel through an application-binding layer. Then it forces authorized applications to use the encrypted TLS tunnels. This is done after the device and the user are properly authenticated and authorized. This ensures that only authorized applications can communicate through the tunnels while unauthorized ones are blocked.
After combining these security layers and protocols, it becomes extremely difficult for malicious users and attackers to access protected applications and services.
SDP Components
The SDP framework’s architecture consists of three main components [U]:
a)	Controller: The SDP controller is the central element in the SDP framework. It is responsible for records of authorized hosts and services and passing on this information to the gateway. This includes issuing certificates and authenticating devices (both initiating and accepting hosts). It use a database to keep those information. The database consists of a variety of tables, mainly including “sdpid” to contain the informations of the components of SDP, “service” to provide the services that will be protected by SDP, “service gateway” to define the gateways for protecting a service and “sdpid service” to show the mapping of service IDs, and the port and protocol numbers of services. 
b)	Client/Initiating Host (IH): SDP Initiating Hosts are the SDP-enabled clients that send a request to connect to a service. This request will be sent the SDP controller and then will be authenticated by the information about hardware or software within the IH. Once authentication using the previously issued certificate, a mutual TLS tunnel is created that connects the IH to the server or application for which it has authorization. Since the IH only gets access to the server after being authenticated, it is beneficial for access control.
c)	Gateway/Accepting Hosts (AH): After the SDP controller provides the gateway with the verified and authenticated IH’s IP address and certificates, then the gateway acts as a filter to prevent all the unauthorized traffic to protect the service. The SDP Accepting Host (AH) is the device instructed to accept authorized services and may contain the gateway. It is originally set up to reject all incoming packets and requests from all hosts except the SDP controller.
 
SDP Working Procedure
The whole process of SDP consists of the following steps: [17420] 
1)	The gateway initiates a TLS connection to the controller, and the controller verifies the gateway by using a certificate.
2)	A connection between the controller and the gateway is establishes and the controller send all the information about IHs and AHs to the gateway as authorized users and services.
3)	The clients initiates a TLS connection to the controller. The controller may use a variety of authentication, authorization and access control services (Location service, MFA, IdP service, PKI service), to verify the clients that send requests to have access to services.
4)	Once the controller authenticates an IH, it selects which appropriate servers can provide the required service to the IH and which AHs they belong to.
5)	The client sends a SPA to the gateway and the decrypted packet is crosschecked. If passed, the gateway sets up the corresponding firewall rules
6)	The AHs are required to connect to the controller and send identification information for authentication. Accepting hosts communicate with the controller but do not respond to any other unauthenticated entity. 
7)	The SDP controllers inform AHs to accept connection from the authorized IH.
8)	The gateway allows the connection request to pass and the IH starts to communicate with AHs by establishing a mutual TLS connection with each AH to perform secure communication.

 
SDP Simulation
	If you want to simulate SDP on your own devices, Waverly Labs’ OpenSDP project (https://www.waverleylabs.com/open-source-sdp/) is a good open-source resource to implement the proposed framework with components being programmed using C, Python, and NodeJS.
As mentioned earlier SDP consists of 3 main components: controller, gateway and client. Each component can be set up on a separate virtual machine. The code can be found in WaverleyLabs’ Github, [WaverleyLabs/SDPcontroller] (https://github.com/WaverleyLabs/SDPcontroller) can be used to simulate the controller, while “WaverleyLabs/fwknop” (https://github.com/WaverleyLabs/fwknop) can be used to simulate gateway and client. 
In addition, another virtual machine can be set up as an unauthorized client or attacker. Several attacks can be simulated to test the utility of SDP. For example, [Hping3] (http://www.hping.org/download.php) is a popular tool to simulate the DoS (Denial of Service) attacks, such as SYN flood attack. For port scanning attacks, [Nmap] (https://nmap.org/download.html) is mainly used for network discovery and security auditing. Besides, the network traffic can be monitored by [Wireshark] (https://www.wireshark.org/download.html) to check the network condition of using SDP or without SDP.
For testing SDP, here we mainly simulate two types of cyber-attacks: DoS and port scanning, and the network throughput is our main metric. 
(1)	SYN flood attack
[Denial-of-service attack (DoS attack)](https://en.wikipedia.org/wiki/Denial-of-service_attack) is a common cyber-attack that is typically accomplished by flooding the targeted machine or resource with superfluous requests in an attempt to overload systems and prevent some or all legitimate requests from being fulfilled.
SYN flood attack is a typical type of DoS attack. It occurs in TCP connections, the attackers send a variety of SYN (synchronize) requests to a target system or server without responding to the server without the expected ACK (acknowledge) code, which will result in the lack of resources. 
A simulation demo can be seen on [Waverleylabs’  OpenSDP Demo](http://www.waverleylabs.com/open-source-sdp/demo/). In normal traffic flows, when one authorized user makes a request, the complete requests would be 100%, and the transfer rate is about 14.2 kbytes/sec.
  
When we initiate a SYN flood attack, the traffic is no longer getting through.
 
   
Most of the times, there would be no traffic can get through. Sometimes there would be a little bit good traffic to go through, but only half the normal transfer rate.
 
| Normal |SYN flood with SDP |SYN flood without SDP |
| ------------- |:-------------:| -----:|
| Connection Setup Time (s)| 0.09 | 0.09 | 1.02 |
| Network Throughput| 14.2 Kbps | 12.8 Kbps | 7.6 Kbps |
| Complete requests percentage |100% | 95%  | 5% |
Almost all the requests can be completed, and traffic speed is close to the normal speed. Therefore, the impact of SYN flood attack to SDP platform is very limited.

(2)	Port scanning attack
Another simulated attack is the port scanning attack. It is an attack that sends requests and list all the available ports to discover the hosts and services on a network and exploit vulnerabilities. Many other types of cyber-attacks may be conducted after port scanning.
In the experiments, Nmap is used to simulate port scanning and the scan ran on ports 1-1000, covering some of the more important services such as HTTP, FTP, SSH etc.
  
Without SDP
  
With SDP
	From the results, it can be seen that without SDP, the scan report shows that an SSH connection is open and available. On the other hand, when with SDP, it doesn’t give any information about the open ports and the service hosted on them. This is because when using SDP, the resources and ports are hidden to any unauthorized users. Therefore, the ports information cannot be scanned by them. 
Overall, using a SDP framework can improve the network’s resiliency to various cyber-attacks such as DoS and port scanning attacks.
