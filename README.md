Project - Securing networks with pfsense : A comprehensive firewall implementation

The project is based on the network security platform where we have configured and implemented a firewall which will used to secure the infrastructure. in this project we have used multiple tools or services like dhcp service, captive portal service,squid proxy, squid guard,Snort and VPN.

Uses of services-

DHCP Service -  The dhcp service is used for assigning the ip addresses to hosts dynamically where it will ensure that all the traffic should go through the Firewalll only by Setting up the default gateway if each host to the ip of pfsense Lan Adaptor.

Captive Portal - the capitive portal is used for The Authentication purpose where users have to authenticate them first before connecting to the internet  it supports multiple ways for the authentication such as 
No authentication, Authentication via username and password and and authentication using vouchers which will provide the internet access to users for limited period of time.we can also limit the bandwidth for each user using this feature and we can also record the log for each ip address connected to the internet which is authenticated by captive portal and  It also have the functionality for testing the credentials that we are  going to provided to the user.it will be beneficial for the admins and it will also reduce the conflicts between users and adminstrators.

Squid Proxy - Squid is designed to improve the speed and efficiency of web browsing by caching frequently accessed web pages and serving them from memory instead of fetching them from the internet every time a user requests them.

Configurations- in local cache there are configurations for cache replacement policy. Like we have to mention percentages for how fast the cache will get replaced. For this there are two two settings in the configuration first is low watermark in % and high watermark in %.

Low watermark in % and high watermark in % indicates how fast cache will get replaced , here we have to mention the lowest limit and highest limit.

Low watermark in % - suppose we have set this value to 90 and threshold reaches that value then squid will consider cache is running low on space and it will aggressively start to evict the cache until value becomes less than 90 .

 high watermark in %- suppose we have set this value to 95 and threshold reaches that value then squid will stop creating new cache object until and unless the value becomes less than threshold.

We can also clear the stored cache from the local cache configurations tab,

Squidguard - squid guard is basically used for the web content filtering. It will act as a forward proxy where all the traffic from lan which is going to wan will be filtered via squid proxy. Squid guard has the functionality to block the websites that are prohibited by the admin.
In this squid guard we have used a url based blacklisting feature where we have to enter the url which consists of various websites categorized by domains which are not supposed to be accessed from the organization's network. After applying this changes web traffic will be filtered according to this rules.
Following is the url -
https://dsi.ut-capitole.fr/blacklists/download/blacklists_for_pfsense.tar.gz

Snort (IDS/IPS) - in this project snort is used as an ids and ips where it is supposed to give an alert when there is any abnormal traffic comes and it should block that specific host. It is configured on the wan interface to detect all the traffic coming from outside. In this project we are used the predefined set of rules which are present in the Snort VRT (Vulnerability research team ). All the traffic will be checked through this rules

Snort vrt rules contains rules for following -

In the Snort VRT (Vulnerability Research Team), there are various types of rules designed to detect specific types of network traffic indicative of security threats. These rules are categorized based on the nature of the threat they detect. Here are some common categories of rules found in Snort VRT:

Policy Rules: These rules detect policy violations or unwanted network activities. Examples include rules for detecting P2P file sharing, excessive network traffic, or protocol anomalies.

Protocol-specific Rules: These rules are tailored to specific network protocols such as HTTP, FTP, SMTP, etc. They identify abnormal or malicious usage of these protocols.

Web Application Rules: These rules focus on detecting attacks targeting web applications, such as SQL injection, cross-site scripting (XSS), or remote file inclusion (RFI) attacks.

Exploit Rules: These rules are designed to detect attempts to exploit known vulnerabilities in various software or systems. Examples include rules for detecting buffer overflow attempts, shellcode execution, or specific exploit payloads.

Malware Rules: These rules detect network traffic associated with known malware or malicious activities. They may target specific malware families or behaviors indicative of malware infections.

Backdoor Rules: These rules identify network traffic associated with backdoor activities, such as remote command execution or unauthorized access attempts.

Brute Force Rules: These rules detect brute force attacks, where an attacker attempts to gain unauthorized access by repeatedly trying different credentials or passwords.

Policy-violation Rules: These rules identify traffic that violates organizational or network policies, such as rules against accessing certain websites or services.

Informational Rules: These rules provide information about network activities without necessarily indicating a security threat. They can be useful for monitoring and analyzing network traffic.

Tuning Rules: These rules are used for fine-tuning the detection capabilities of Snort, such as adjusting thresholds or ignoring certain types of traffic.

These categories encompass a wide range of rules designed to detect and prevent various types of network threats and security incidents. Snort VRT regularly updates its rule sets to address emerging threats and vulnerabilities in the cybersecurity landscape.


Virtual private network -

In this project we have also configured a vpn for remote access, it is using the L2tp/ipsec with pre shared key protocol because it is providing an encryption in  communication. Users will be authenticated by psk key. We have used l2tp over ipsec because l2tp alone cant provide any kind of encryption.


Applications of the Project - 

Network security : pfSense's snort feature can detect and block potential security threats, ensuring that the organization's network is secure.

User access control: pfSense's captive portal feature allows organizations to control user access to the internet, ensuring that only authorized users can access the network.

Web content filtering: pfSense's Squid and Squid Guard features allow organizations to filter web content, preventing access to harmful or inappropriate websites.

Improved network performance : pfSense's DHCP service feature can improve network performance by ensuring that IP addresses are allocated efficiently.
