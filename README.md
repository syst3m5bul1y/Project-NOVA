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
