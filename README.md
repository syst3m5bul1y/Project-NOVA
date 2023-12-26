# Project NOVA Overview

### NAME: PROJECT NO VISITORS ALLOWED

### BRIEF DESCRIPTION: 

Project NOVA is designed as a hands-on initiative to establish a comprehensive cybersecurity home lab. This project aims to simulate a small-scale enterprise network environment, allowing for practical learning, experimentation, and skill development in various aspects of cybersecurity.

### SYSTEM TYPE: 

NETWORK ARCHITECTURE /HOME-LAB

### PRIMARY FUNCTION

Mimic realistic small-scale enterprise network.

### PURPOSE & GOALS  

*created on 19/11/2023*

#### Primary Goals:

1. **Skill Enhancement in Cybersecurity**: To deepen understanding and proficiency in network security, system administration, and ethical hacking practices.

2. **Certification Preparation**: To create a robust environment for preparing for certifications like CompTIA CySA+ and Red Hat Certified System Administrator.

3. **Practical Application**: To apply theoretical knowledge in a controlled, realistic setting, enabling the practice of configuring, securing, and managing network services.

4. **Security Tool Exploration**: To experiment with and understand the functionalities of various cybersecurity tools, including NIDS/NIPS systems, SIEM solutions, and other security software.

5. **Response Strategy Testing**: To simulate cyber-attack scenarios and test response strategies, enhancing skills in incident response and threat mitigation.

6. **Understanding Network Services**: To set up and manage key network services like LDAP, email servers, and web services, and to learn about hardening these services against potential threats.

#### Secondary Goals:

1. **Research and Development**: To explore and test new cybersecurity tools and technologies, staying up-to-date with current trends and advancements in the field.

2. **Documentation and Reporting Skills**: To enhance skills in documenting technical processes and creating comprehensive reports, an essential skill in cybersecurity and network engineering professions.




### HIGH LEVEL ARCHITECTURE

*created on 19/11/2023*

#### Overview:

Project NOVA's architecture is designed to mimic a small-scale enterprise network environment within a virtualized setup. The core of the architecture lies in its ability to simulate real-world network scenarios, security setups, and attack responses within a controlled lab setting.

#### Key Components:

1. **Virtualization Platform**: VMware Workstation 17 Pro 17.5.0 serves as the foundation, hosting all virtual machines (VMs) and managing network configurations.

2. **Network Layout**:
    - The lab network operates on the `192.168.2.0/24` subnet, separate from the host network.
    - A dedicated Gateway VM acts as the central router, firewall, and access point between the internal lab network and the external internet connection.

3. **Virtual Machines and Roles**:
    - **Gateway VM**: Manages network traffic, provides DHCP and DNS services, and ensures secure internet access for other VMs in the lab.
    - **WebServer VM** (PROPOSED): Hosts web applications for testing web security.
    - **MailHost VM**: Simulates email services for studying email security and spam filtering.
    - **LDAPhost VM**: Provides directory services, enabling experimentation with LDAP security.
    - **SIEM System VM** (PROPOSED): Collects and analyzes logs, aiding in security event management and incident response.
    - **Associate Desktop VMs**: VMs such as Kali Linux, Ubuntu Desktop, BackBox, Windows 10, etc, to orchestrate personal devices. These VMs will range from function and security standing such as hardened to vulnerable.

4. Networking and Security:
	- The *Gateway VM* features dual network interfaces: one for external (bridged/NAT) connections and one for the internal lab network.
	- The internal network is configured for complete isolation from the host network, ensuring a secure and controlled environment.
	- All VMs are configured to communicate within the `192.168.2.0/24` subnet, with the Gateway VM serving as their primary gateway and firewall.
	- Comprehensive security configurations, including firewalls and security policies, are implemented to mirror real-world enterprise security standards.


Functionality and Flexibility:

- The lab is designed for flexibility, allowing for the addition or reconfiguration of VMs and network settings to suit various learning objectives and scenarios.
- It enables practical application of cybersecurity concepts, from basic network setup to advanced security strategies and incident response


### KEY COMPONENTS

*created on 19/11/2023*

#### Virtualization Platform:

- **VMware Workstation 17 Pro**: The primary platform for creating and managing all virtual machines (VMs) in the lab. It allows for configuring various network settings and managing the interactions between different VMs.

#### Core Virtual Machines:

1. **Gateway VM**:
    
    - Role: Acts as the network router, firewall, and point of entry/exit for internet access in the lab network. It also provides essential network services like DHCP and DNS.
    - Operating System: Slackware Linux (or a preferred alternative).
    - Key Services: iptables for firewall setup, ISC DHCP Server for DHCP services, BIND for DNS services.

2. **WebServer VM** (PROPOSED):
    
    - Role: Hosts web applications and services for testing and learning about web security.
    - Operating System: Ubuntu Server or CentOS (chosen for stability and community support).
    - Key Services: Apache or Nginx for web hosting, MySQL/PostgreSQL for database management.

3. **MailHost VM**:
    
    - Role: Simulates an email server environment for studying email security, including spam filters and mail routing.
    - Operating System: Ubuntu Server or another Linux distribution suitable for mail services.
    - Key Services: Postfix for SMTP, Dovecot for IMAP/POP3.

4. **LDAPhost VM**:
    
    - Role: Provides directory services, useful for practicing LDAP integration and security.
    - Operating System: Debian or CentOS.
    - Key Service: OpenLDAP.

5. **SIEM System VM** (PROPOSED):
    
    - Role: Central system for log collection, monitoring, and analysis, aiding in incident detection and response.
    - Operating System: A lightweight Linux distribution.
    - Key Service: Elasticsearch, Logstash, and Kibana (ELK Stack) or similar.

6. **Kali Linux VM**:
    
    - Role: Serves as the primary platform for penetration testing and security assessments.
    - Operating System: Kali Linux.
    - Tools: Includes various cybersecurity tools pre-installed in Kali Linux.

7. **Ubuntu Desktop VM**:
    
    - Role: A general-purpose VM for various tasks and testing.
    - Operating System: Ubuntu Desktop.

#### Network and Security Infrastructure:

- **Custom VMnet (VMware Network)**: A virtual network setup within VMware to connect and isolate the lab VMs.

#### Hardware Requirements:

- **Host System**: Lenovo Legion Slim 5 16IRH8 with an i7 13700H processor, 16GB RAM, 512GB M.2 SSD, and Nvidia RTX 4050 6GB, running the VMware Workstation 17 Pro.

#### Additional Tools and Software:

- Network monitoring tools, security scanning tools, and other relevant cybersecurity software as required for specific experiments and learning objectives.

Full set of services - [[Project NOVA - LoS]]

### PROJECT PLAN

*created on 19/11/2023*

#### Phase 1: Planning and Design

- **Objective**: Establish a clear project outline and design the network architecture.
- **Milestones**:
    1. Finalize project goals and scope.
    2. Develop a detailed network plan, including IP scheme and VM roles.
    3. Select operating systems and key software for each VM.
    4. Document initial project plan and network design.

#### Phase 2: Environment Setup

- **Objective**: Set up the virtualization environment and initial VMs.
- **Milestones**:
    1. Install and configure VMware Workstation Pro on the host system.
    2. Create and configure the Gateway VM with necessary network services.
    3. Establish custom VMnet for lab network.
    4. Document setup processes and configurations.

#### Phase 3: Core VM Deployment

- **Objective**: Deploy and configure key VMs within the lab network.
- **Milestones**:
    1. Set up and configure the WebServer, MailHost, and LDAPhost VMs.
    2. Install and set up the SIEM System VM.
    3. Configure Kali Linux and Ubuntu Desktop VMs.
    4. Ensure all VMs are connected to the lab network and functioning as expected.
    5. Document each VM's setup and configuration.

#### Phase 4: Security Implementation and Testing

- **Objective**: Implement security measures and conduct initial tests.
- **Milestones**:
    1. Configure firewall and security policies on the Gateway VM.
    2. Set up NIDS/NIPS using the SENSI system.
    3. Perform initial security assessments and penetration tests with Kali Linux.
    4. Document security setups and test results.

#### Phase 5: Experimentation and Learning

- **Objective**: Utilize the lab for learning, experiments, and certification preparation.
- **Milestones**:
    1. Conduct specific network security experiments and document findings.
    2. Prepare for and study relevant cybersecurity certifications (e.g., CompTIA CySA+, RHCSA).
    3. Explore and test new tools and technologies.

#### Phase 6: Documentation and Community Sharing

- **Objective**: Finalize documentation and share learnings with the community.
- **Milestones**:
    1. Complete comprehensive documentation of the project in Obsidian.
    2. Share configurations, findings, and insights on GitHub under 'syst3m5bul1y'.

#### Phase 7: Ongoing Maintenance and Expansion

- **Objective**: Maintain and expand the lab environment as needed.
- **Milestones**:
    1. Regularly update and maintain the VMs and tools.
    2. Explore possibilities for expanding or upgrading the lab.
    3. Stay updated with the latest cybersecurity trends and incorporate relevant changes into the lab.

# NETWORK PLAN

### ARCHITECTURE

![image](https://github.com/syst3m5bul1y/Project-NOVA/assets/100330775/b56abc2e-b0cd-42bd-bd88-5047a81a1f29)

### SUBNETTING & IP ALLOCATION

#### Subnetting Strategy:

- **Chosen Subnet**: `192.168.2.0/24`
- **Purpose**: This subnet is selected to avoid conflict with the home network range and to provide sufficient address space for lab components.
- **Subnet Size**: Offers up to 254 usable IP addresses, ample for the scale of this lab.

#### IP Allocation:

1. **Gateway VM**:
    
    - IP Address: `192.168.2.1`
    - Role: Network router and firewall, DHCP, and DNS services.

2. **WebServer VM**:
    
    - IP Address: `192.168.2.10`
    - Role: Hosting web applications and services.
    - IP reserved.

3. **MailHost VM**:
    
    - IP Address: `192.168.2.20`
    - Role: Simulating email server for email security practices.

4. **LDAPhost VM**:
    
    - IP Address: `192.168.2.30`
    - Role: Providing directory services for LDAP integration and security testing.

5. **SIEM System VM**:
    
    - IP Address: `192.168.2.40`
    - Role: Log collection, monitoring, and analysis.
    - IP reserved.

6. **Kali Linux VM**:
    
    - IP Address: `192.168.2.50`
    - Role: Penetration testing and security assessments.

7. **Ubuntu Desktop VM**:
    
    - IP Address: `192.168.2.60`
    - Role: General-purpose Linux environment.

#### DHCP and Static IP Strategy:

- **Dynamic IP Assignment**: For certain VMs where fixed IPs are not critical, a DHCP service (from the Gateway VM) can be used for dynamic IP allocation.

- **Static IP Reservation**: Key VMs like the Gateway, WebServer, MailHost, LDAPhost, and SIEM System will have static IPs for consistent network configuration and easier management.

#### Network Segmentation (Future Consideration):

- Potential to segment the network further for specialized purposes, such as creating isolated subnets for testing specific security scenarios.


### NETWORK SERVICES CONFIGURATIONS & SPECIFICATION

#### Overview:

Configuring network services effectively is crucial for the functionality and security of Project NOVA's lab environment. These services are mainly managed by the Gateway VM, providing centralized control and simplified administration.

#### DHCP (Dynamic Host Configuration Protocol) Configuration:

- **Service Host**: Gateway VM.
- **Role**: Automatically assigns IP addresses and other network parameters to VMs.
- **Configuration Details**:
    - DHCP Range: `192.168.2.100` to `192.168.2.200` for dynamic allocation.
    - Lease Time: Set per lab testing requirements (default 24 hours).
    - DHCP Options: Default gateway (`192.168.2.1`), DNS server settings, etc.

#### DNS (Domain Name System) Configuration:

- **Service Host**: Gateway VM.
- **Role**: Resolves domain names into IP addresses.
- **Configuration Details**:
    - Primary DNS: Configured for both internal lab hostnames and external domains.
    - Forwarders: Optional external DNS servers (e.g., 1.1.1.1 or 8.8.8.8) for external queries.

#### Firewall Configuration:

- **Service Host**: Gateway VM.
- **Role**: Regulates network traffic based on predefined security rules.
- **Configuration Details**:
    - Default Policy: Deny all incoming traffic not matching a rule.
    - Specific Rules: Allow necessary inbound/outbound traffic for each VM.

#### NTP (Network Time Protocol) Configuration:

- **Service Host**: Gateway VM.
- **Role**: Synchronizes time across all VMs and network devices.
- **Configuration Details**:
    - Install NTP service (e.g., `sudo apt install ntp` for Ubuntu/Debian).
    - Edit `/etc/ntp.conf` to specify NTP servers.
    - Adjust firewall to allow NTP traffic (port 123 UDP).
    - Set Gateway VM as the primary NTP server for other VMs.

#### SNMPv3 Configuration:

- **Service Host**: Gateway VM.
- **Role**: Provides secure network management and monitoring capabilities.
- **Configuration Details**:
    - Install SNMPv3 tools (e.g., `sudo apt-get install snmpd` for Ubuntu/Debian).
    - Configure `/etc/snmp/snmpd.conf` with secure users, authentication, and encryption settings.
    - Adjust firewall to allow SNMP traffic (default port 161/UDP).
    - Use SNMPv3 for secure communication between agents and the manager.
    - Set up agents on individual VMs and a central SNMP manager for comprehensive monitoring.

#### Additional Services:

- **VPN Server (Future Consideration)**: For secure remote lab access.

#### Monitoring and Management Tools:

- Tools like Nagios or Zabbix for network monitoring and alerting.
- Command-line tools (e.g., `iftop`, `nmap`) for real-time network monitoring.


### GATEWAY VM CONFIGURATIONS

#### Overview:

The Gateway VM serves as the central node of the Project NOVA network. It handles various critical functions, including traffic routing, security enforcement, and network service management.

#### Roles and Responsibilities:

- **Primary Network Router**: Manages and directs traffic between the lab network and external networks.
- **Security Enforcement Point**: Implements firewall rules to regulate inbound and outbound traffic, ensuring network security.
- **Service Provider**: Hosts essential network services such as DHCP, DNS, NTP, and SNMPv3.

#### Specific Configuration Details:

1. **Operating System**:
    
    - Recommended OS: Slackware Linux or Ubuntu Server for stability and control.
    - Update and secure the OS with the latest patches and security configurations.

2. **Network Interfaces**:
    
    - At least two network interfaces: one connecting to the external network (e.g., your home network) and the other to the internal lab network.
    - Assign appropriate IP addresses aligning with the network plan (e.g., External: DHCP-assigned, Internal: `192.168.2.1`).

3. **DHCP Server**:
    
    - Assigns IP addresses within the `192.168.2.0/24` range to lab VMs.
    - Configure options for default gateway, subnet mask, and DNS.

4. **DNS Server**:
    
    - Resolves both internal and external domain name queries.
    - Optionally configure forwarders for external domain resolution.

5. **Firewall Configuration**:
    
    - Implement iptables or nftables rules for packet filtering and NAT (Network Address Translation).
    - Define rules to allow necessary traffic and block unwanted access.

6. **NTP Service**:
    
    - Synchronizes time across all lab devices.
    - Configured to connect to reliable external NTP servers and act as the NTP server for internal lab VMs.

7. **SNMPv3 Agent**:
    
    - Secure configuration for network monitoring and management.
    - Set up with robust authentication and encryption settings.

8. **Routing and Network Management**:
    
    - Ensure proper routing between the internal and external networks.
    - Manage network settings to optimize performance and reliability.

9. **Logging and Monitoring**:
    
    - Configure system logging to track and record network and system events.
    - Use monitoring tools for real-time network visibility.

#### Security Considerations:

- Regularly update and patch the OS and services.
- Employ strong firewall rules and monitor logs for any unusual activities.
- Use secure protocols and authentication methods for all services.

# VM CONFIGURATIONS

### Gateway VM Configuration

1. **OS Choice**: Slackware Linux.
    
    - **Reasoning**: Offers advanced control and is suited for learning in-depth Linux administration.

2. **Resource Allocation**:
    
    - **CPU**: 2 Cores.
    - **RAM**: 2 GB.
    - **Disk Space**: 20 GB.

3. **Primary Role**:
    
    - Network routing and management.
    - Firewall, DHCP, DNS, NTP, and SNMP agent functionalities.

4. **Software and Tools**:
    
    - **Firewall**: iptables/nftables for network packet filtering and NAT.
    - **DHCP Server**: ISC DHCP server for dynamic IP address allocation.
    - **DNS Service**: BIND for domain name resolution within the lab network.
    - **NTP Service**: Chrony or ntpd for network time synchronization.
    - **SNMP Agent**: NET-SNMP for network management information sharing.

5. **Network Adapter Settings**:
    
    - **Adapter 1**: Bridged mode, connecting to the external network for Internet access.
    - **Adapter 2**: Custom VMnet, for internal lab network communication.
  
### Mail Server VM Configuration

1. **OS Choice**: Debian - minimal.
    
    - **Reasoning**: Known for its stability and efficiency, Debian is well-suited for running a reliable mail server.

2. **Resource Allocation**:
    
    - **CPU**: 2 Cores.
    - **RAM**: 2 GB.
    - **Disk Space**: 30 GB (additional space may be allocated for email storage).

3. **Primary Role**:
    
    - Hosting and managing email communication within the lab network.

4. **Software and Tools**:
    
    - **Mail Transfer Agent (MTA)**: Postfix, for handling outgoing and incoming emails.
    - **Mail Delivery Agent (MDA)**: Dovecot, for accessing and storing mails.
    - **Spam Filtering**: SpamAssassin, for identifying and filtering spam emails.
    - **Virus Scanning**: ClamAV, for detecting viruses in email attachments.
    - **Webmail Interface** (Optional): Roundcube or SquirrelMail for accessing emails via a web browser.

5. **Network Adapter Settings**:
    
    - **Adapter**: Custom VMnet, ensuring the mail server is part of the internal lab network and accessible by other VMs.

   ### LDAP Server VM Configuration

1. **OS Choice**: CentOS.
    
    - **Reasoning**: CentOS is known for its stability and enterprise-level features, making it a suitable choice for directory services and identity management.

2. **Resource Allocation**:
    
    - **CPU**: 2 Cores.
    - **RAM**: 2 GB.
    - **Disk Space**: 20 GB.

3. **Primary Role**:
    
    - Managing user identities, authentication, and directory services within the lab network.

4. **Software and Tools**:
    
    - **LDAP Service**: OpenLDAP, for providing directory services.
    - **LDAP Management Tools**: phpLDAPadmin for a web-based LDAP management interface (optional).
    - **Security Tools**: Appropriate firewall settings (firewalld or iptables) and SELinux for enhanced security.

5. **Network Adapter Settings**:
    
    - **Adapter**: Custom VMnet99, ensuring the LDAP server is integrated into your internal lab network and accessible by other VMs on the same network.

   ### Web Server VM Configuration

1. **OS Choice**: Ubuntu Server.
    
    - **Reasoning**: Ubuntu Server is user-friendly and widely used, making it a suitable choice for hosting web applications, especially for those who are familiar with Ubuntu's ecosystem.

2. **Resource Allocation**:
    
    - **CPU**: 2 Cores.
    - **RAM**: 2 GB.
    - **Disk Space**: 30 GB (consider more if expecting high web content volume).

3. **Primary Role**:
    
    - Hosting and serving web pages or applications within the lab network.

4. **Software and Tools**:
    
    - **Web Server Software**: Apache or Nginx, popular choices for serving web content.
    - **Database Management System**: MySQL or PostgreSQL, for backend database support if needed.
    - **Scripting Languages**: PHP, Python, or others, depending on the web application requirements.
    - **Additional Tools**: SSL/TLS certificates (self-signed for lab purposes), Content Management System (CMS) like WordPress (optional), and security tools like ModSecurity (for Apache) or Fail2Ban.

5. **Network Adapter Settings**:
    
    - **Adapter**: Custom VMnet99, aligning with your internal lab network configuration, and ensuring that the web server is accessible by other VMs within the same network.

   ### SNMP Manager Server VM Configuration

1. **OS Choice**: Ubuntu Server.
    
    - **Reasoning**: Known for its user-friendliness and robustness, ideal for running network management and monitoring tools.

2. **Resource Allocation**:
    
    - **CPU**: 2 Cores.
    - **RAM**: 2 GB.
    - **Disk Space**: 30 GB.

3. **Primary Role**:
    
    - Central management and monitoring of network devices and VMs using SNMP.

4. **Software and Tools**:
    
    - **SNMP Management Tool**: Zabbix, Nagios, or Cacti (choose based on preference).
    - **SNMPv3 Configuration**: For secure communication with SNMP agents.

5. **Network Adapter Settings**:
    
    - **Adapter**: Custom VMnet99, ensuring connectivity with all lab VMs for effective SNMP management.

   # VM SPECIFIC SECURITY CONFIGURATIONS

   VM SPECIFIC SECURITY CONFIGURATIONS


#### Gateway VM

1. **Operating System Hardening**:
    
    - Ensure only necessary services are running.
    - Regularly update the Slackware Linux system to patch vulnerabilities.
    - Disable root login over SSH and use key-based authentication.

2. **Firewall Configuration**:
    
    - Implement a strict iptables or nftables rule set.
    - Allow traffic on essential ports only (e.g., 22 for SSH, 53 for DNS, 80/443 for HTTP/HTTPS if needed).
    - Drop all inbound traffic that does not match defined rules.
    - Configure NAT for internal VMs to access external networks.

3. **Intrusion Detection and Prevention**:
    
    - Deploy Suricata with rulesets tailored to detect and possibly block known attack patterns.
    - Regularly update Suricata rules.

4. **Network Services Security**:
    
    - Secure the DHCP and DNS services by restricting updates to authorized users and machines.
    - Implement rate limiting on DHCP and DNS to mitigate DDoS attacks.
    - Configure NTP securely to avoid misuse of your server in NTP amplification attacks.

5. **Logging and Monitoring**:
    
    - Enable and configure logging for all critical services (firewall, DHCP, DNS, NTP, etc.).
    - Forward logs to a centralized logging server for analysis and retention.

6. **SNMP Configuration**:
    
    - Use SNMPv3 for its enhanced security features.
    - Restrict SNMP access to specific management IPs.



#### Mail Server VM

1. **Operating System Hardening**:
    
    - Regularly update Debian to ensure all security patches are applied.
    - Disable unused services and ports.
    - Implement strong user password policies and use SSH key-based authentication.

2. **Firewall Configuration**:
    
    - Configure UFW (Uncomplicated Firewall) to allow only mail-related ports: SMTP (25, 587), IMAP (143, 993), and POP3 (110, 995).
    - Block all other inbound ports not used by mail services.
    - Implement rate limiting for SMTP to prevent spamming activities.

3. **Mail Server Security**:
    
    - Use Postfix and Dovecot with secure configurations to prevent unauthorized access.
    - Implement spam filtering with SpamAssassin and virus scanning with ClamAV to protect against malicious emails.
    - Enable SSL/TLS for all mail services to ensure encrypted communication.

4. **Authentication and Access Control**:
    
    - Enforce strong authentication mechanisms in Dovecot.
    - Use SASL (Simple Authentication and Security Layer) in Postfix for secure authentication.

5. **Logging and Monitoring**:
    
    - Enable comprehensive logging for Postfix, Dovecot, SpamAssassin, and ClamAV.
    - Regularly review logs for signs of unusual activities or attempted breaches.
    - Forward logs to a centralized server for better analysis and archiving.

6. **Backup and Recovery**:
    
    - Implement regular backups of email data and server configurations.
    - Test restore procedures to ensure data can be recovered in the event of a failure or breach.

#### LDAP Server VM

1. **Operating System Hardening**:
    
    - Regularly update CentOS to apply security patches.
    - Disable unnecessary services and ports not required for LDAP operations.
    - Use SSH key-based authentication and disable root login over SSH.

2. **Firewall Configuration**:
    
    - Configure firewalld to allow only LDAP-related ports: 389 for LDAP and 636 for LDAPS (LDAP over SSL).
    - Deny all other inbound traffic not explicitly required for LDAP services.

3. **LDAP Service Security**:
    
    - Configure OpenLDAP to use strong encryption with LDAPS or StartTLS to protect the communication.
    - Implement access controls within OpenLDAP to restrict data access based on roles and need-to-know basis.

4. **Authentication and Access Control**:
    
    - Use strong password policies for LDAP accounts.
    - Regularly review and update access permissions to ensure they adhere to the principle of least privilege.

5. **Logging and Monitoring**:
    
    - Enable detailed logging for OpenLDAP activities.
    - Regularly monitor logs for unauthorized access attempts or unusual activities.
    - Forward logs to a centralized logging server for analysis and long-term storage.

6. **Backup and Recovery**:
    
    - Regularly backup LDAP directory data and configuration files.
    - Verify backup integrity and test restoration processes periodically.

7. **Security Enhancements**:
    
    - Consider implementing Multi-Factor Authentication (MFA) for sensitive accounts.
    - Regularly audit and review LDAP entries and configurations for security risks.

#### SNMP Server VM

1. **Operating System Hardening**:
    
    - Regularly update Ubuntu Server to incorporate the latest security patches.
    - Disable unnecessary services and close unused ports.
    - Implement SSH key-based authentication and disable root login over SSH.

2. **Firewall Configuration**:
    
    - Use UFW (Uncomplicated Firewall) to allow only SNMP-related ports, typically UDP 161 for SNMP queries.
    - Block all other inbound traffic that is not essential for SNMP operations.

3. **SNMP Service Security**:
    
    - Configure SNMPv3, which provides enhanced security features including authentication and encryption.
    - Use complex passwords and encryption keys for SNMPv3 users.
    - Limit SNMP access to only specific management IPs within your lab network.

4. **Monitoring and Access Control**:
    
    - Regularly monitor SNMP traffic for any unusual patterns or spikes in activity that may indicate a security issue.
    - Implement strict access controls on the SNMP management tools like Zabbix or Nagios, ensuring only authorized users have access.

5. **Logging and Alerting**:
    
    - Enable detailed logging of SNMP activities.
    - Set up alerts for critical events or anomalies detected through SNMP monitoring.
    - Forward logs to a centralized logging server for comprehensive analysis and record-keeping.

6. **Backup and Recovery**:
    
    - Regularly backup the SNMP configuration and the monitoring database.
    - Test restoration procedures to ensure you can recover in case of failure.

7. **Update and Patch Management**:
    
    - Keep the SNMP management software up to date with the latest releases and patches.

#### Web Server VM

1. **Operating System Hardening**:
    
    - Keep Ubuntu Server updated with the latest security patches.
    - Disable unnecessary services and ports not required for web hosting.
    - Use SSH key-based authentication and disable root login over SSH.

2. **Firewall Configuration**:
    
    - Configure UFW to allow only web traffic on ports 80 (HTTP) and 443 (HTTPS).
    - Implement rate limiting on these ports to mitigate the risk of DDoS attacks.
    - Block all other unnecessary inbound traffic.

3. **Web Service Security**:
    
    - Use Apache or Nginx with secure configurations, including disabling unnecessary modules.
    - Implement SSL/TLS certificates for HTTPS, using Let's Encrypt for free certificates.
    - Set up proper directory permissions and ownership.

4. **Application-Level Security**:
    
    - If running CMS (e.g., WordPress, Joomla), keep it and its plugins/themes updated.
    - Implement security plugins or modules within the CMS for added protection.
    - Use strong passwords for CMS admin accounts and consider two-factor authentication.

5. **Database Security** (if applicable):
    
    - Secure database access by binding to localhost and using strong passwords.
    - Regularly update and patch the database management system.
    - Perform regular backups of the database.

6. **Logging and Monitoring**:
    
    - Enable extensive logging for the web server and review logs regularly.
    - Use tools like Fail2Ban to ban IPs that show malicious behavior.
    - Forward logs to a centralized server for analysis and archiving.

7. **Backup and Recovery**:
    
    - Implement a regular backup schedule for website data and configurations.
    - Verify backups and test restoration processes to ensure data integrity.
  
   

