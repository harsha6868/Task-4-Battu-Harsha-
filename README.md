# Task-4-Battu-Harsha-
This  repository contains setting up and using a fire wall on windows/Linux of Battu harsha vardhan reddy batch 15
# UFW Firewall Configuration Project Report:
This report provides a comprehensive analysis of the UFW (Uncomplicated Firewall) setup and configuration performed on a Kali Linux system, demonstrating practical network security implementation and testing.

# Project Overview:
**Objective:** Configure and test basic firewall rules using UFW to control network traffic flow    
**Testing Environment:** Multi-host network setup with remote testing capabilities   
**Duration:** Complete implementation and testing cycle

# Implementation Analysis:

# **Initial System State**
The project began with UFW not installed on the target Kali Linux system. This required package installation before any firewall configuration could proceed.

# Step-by-step Process

## Installing UFW in linux using the command:
`sudo apt update && sudo apt install ufw`

<img width="512" height="346" alt="image" src="https://github.com/user-attachments/assets/a9460436-2f92-4382-8912-2deb0e9a90ff" />

##  Enabling UFW using the command:
<img width="500" height="347" alt="image" src="https://github.com/user-attachments/assets/56f44eb5-b41c-4e9c-affd-e58329d342a3" />

## Make UFW start on boot using following command:
`sudo systemctl enable ufw`

<img width="503" height="346" alt="image" src="https://github.com/user-attachments/assets/417fe626-c1a7-43cc-8ff8-b41295d236e0" />

## Enable logging to monitor firewall activity with the command:
`sudo ufw logging on`
## Set Default policy in UFW by command:
`sudo ufw default deny incoming` `sudo ufw default allow outgoing`
## Block Inbound Traffic on Port 23 (Telnet) using command:
`sudo ufw deny 23/tcp` `sudo ufw deny 23/udp`
##  Allow SSH Access (Port 22) by command:
`sudo ufw allow ssh`
## Test firewall rules by following command: 
<img width="511" height="345" alt="image" src="https://github.com/user-attachments/assets/802fa1d0-9429-4ea4-9a03-9a15667026f1" />


## Success end Result
<img width="509" height="346" alt="image" src="https://github.com/user-attachments/assets/8f3dffe9-5acc-4256-89cb-515350626a8e" />

# Security Impact Assessment:

### **Threat Mitigation Achieved**

**Telnet Security Enhancement:**
- **Risk Eliminated:** Unencrypted credential transmission
- **Attack Vector Blocked:** Remote unauthorized access via Telnet
- **Compliance Improvement:** Aligned with security best practices

**Network Segmentation:**
- **Default Deny Policy:** Reduces attack surface significantly
- **Service Isolation:** Only essential services exposed
- **Dual-Stack Protection:** IPv4 and IPv6 coverage

### **Operational Considerations**

**Positive Impacts:**
- Enhanced security posture without service disruption
- Maintained administrative access via SSH
- Web services remain functional
- Comprehensive logging for security monitoring

**Potential Limitations:**
- Stateless filtering may not detect sophisticated attacks
- No application-layer inspection
- Limited intrusion detection capabilities

### **Security Principles Applied**
- **Principle of Least Privilege:** Only necessary ports opened
- **Defense in Depth:** Multiple rule types for comprehensive protection
- **Fail-Safe Defaults:** Default deny policy implementation
- **Auditability:** Logging enabled for security monitoring

##  Technical Deep Dive:

### **UFW Architecture Understanding**

UFW operates as a **frontend to iptables**, providing simplified rule management while maintaining the robust filtering capabilities of the underlying netfilter framework. The implementation demonstrates:

- **Rule Translation:** UFW commands automatically generate appropriate iptables rules
- **Chain Management:** Proper integration with INPUT, OUTPUT, and FORWARD chains

### **Network Traffic Flow Analysis**

The firewall implementation creates the following traffic flow control:

1. **Incoming Traffic Evaluation:**
   - Default DENY policy applied first
   - Explicit ALLOW rules checked sequentially
   - Blocked traffic logged (when logging enabled)

2. **Outgoing Traffic Management:**
   - Default ALLOW policy permits most outbound connections
   - No restrictions on client-initiated communications
   - Maintains system functionality for updates and external services


## Conclusion

This UFW firewall implementation project successfully demonstrated comprehensive network security configuration on Kali Linux. The systematic approach to rule implementation, thorough testing methodology, and proper documentation practices showcase effective cybersecurity implementation.

##  Recommendations for Enhancement

### **Immediate Improvements**
1. **Rate Limiting:** Implement connection rate limiting for SSH
2. **Geo-blocking:** Consider IP-based geographic restrictions
3. **Port Knocking:** Advanced SSH access control mechanisms

### **Advanced Security Measures**
1. **Application Layer Filtering:** Consider proxy-based solutions
2. **Monitoring Integration:** SIEM system connectivity for centralized logging
3. **Automated Response:** Dynamic rule updates based on threat intelligence


