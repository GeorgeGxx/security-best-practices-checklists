# Network Security Checklist

## Firewalls

- Regularly review and update firewall rule sets to reflect changes in network infrastructure and security policies.
- Enable logging on firewalls to record traffic and rule violations for analysis.
- Conduct periodic firewall rule reviews to identify and remove unnecessary or outdated rules.
- Configure firewall rules to block inbound and outbound traffic by default and only allow specific exceptions.
- Implement geographic filtering to block traffic from regions with a high volume of malicious activity.

## Intrusion Detection and Prevention Systems (IDPS)

- Configure IDPS to monitor both inbound and outbound network traffic for known attack signatures and anomalies.
- Regularly update IDPS signatures and rules to detect new and emerging threats.
- Set up alerts and notifications for suspicious or malicious activity detected by the IDPS.
- Conduct regular testing and tuning of IDPS to minimize false positives and improve detection accuracy.
- Integrate IDPS with other security tools and systems for automated incident response and remediation.

## Encryption

- Use strong encryption algorithms (e.g., AES, RSA) with appropriate key lengths for data encryption.
- Implement SSL/TLS encryption for securing web traffic, email communications, and other sensitive data transmissions.
- Encrypt sensitive data stored in databases, file systems, and other storage repositories using encryption technologies such as BitLocker or FileVault.
- Implement certificate management practices, including regular certificate expiration checks and renewal procedures.
- Securely manage encryption keys, including key generation, storage, rotation, and destruction, to prevent unauthorized access.

## Virtual Private Network (VPN)

- Implement VPN technology to securely extend network access to remote users and branch offices.
- Configure VPN encryption and authentication settings to ensure data confidentiality and integrity.
- Enforce VPN client security policies, including endpoint security checks and software updates.
- Monitor VPN connections for anomalous behavior and potential security threats.
- Regularly review VPN logs and audit trails for compliance and security pur poses.

## Network Access Control (NAC)

- Deploy NAC solutions to enforce security policies and control access to network resources.
- Authenticate users and devices before granting network access, using methods such as 802.1X authentication, MAC address authentication, or captive portal authentication.
- Assess the security posture of devices connecting to the network and enforce compliance with security policies (e.g., antivirus software, operating system patches).
- Automate the remediation of non-compliant devices or quarantine them to a restricted network segment.
- Integrate NAC with other security systems (e.g., SIEM, endpoint security) for centralized policy management and threat response.

## Network Segmentation

- Segment the network into multiple logical or physical segments to reduce the impact of security breaches and limit lateral movement by attackers.
- Implement VLANs, subnets, or micro-segmentation to separate network traffic based on user roles, departments, or sensitivity of data.
- Configure access control lists (ACLs) and firewall rules to control traffic between network segments and enforce least privilege access.
- Monitor inter-segment traffic for anomalous behavior or policy violations using network monitoring tools and intrusion detection systems.
- Regularly review and update network segmentation policies to adapt to changes in business requirements and security threats.

## Wi-Fi Security

- Use strong encryption protocols (e.g., WPA2/WPA3 to secure Wi-Fi networks
- Implement Wi-Fi Protected Access WPA enterprise mode with 802.1X authentication for user authentication and access control.
- Enable MAC address filtering to restrict access to authorized devices only.
- Regularly change Wi-Fi passwords and pre-shared keys PSKs) to prevent unauthorized access.
- Monitor Wi-Fi networks for rogue access points and unauthorized connections.

## Data Loss Prevention (DLP)

- Deploy DLP solutions to monitor and control sensitive data leaving the networks
- Classify sensitive data and establish policies to prevent unauthorized access, transmission, or storage.
- Monitor network traffic, email communications, and endpoint activities for data leakage incidents.
- Implement encryption and access controls to protect sensitive data at rest and in transit.
- Regularly audit and review DLP policy configurations and incident logs for effectiveness and compliance.

### [v2 checklist](README-V2.md)