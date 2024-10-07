# Network Security Checklist Version 2

## Firewalls

- Update the router to the latest firmware version.
- Enable stateful packet inspection (SPI).
- Disable ping (ICMP) response on WAN port.
- Disable UPnP (universal plug-and-play).
- Disable IDENT (port 113).
- Disable remote management of the router.
- Change the default administrator password.
- The settings for a firewall policy should be as specific as possible. Do not use 0.0.0.0 as an address.
- Check for incoming/outgoing traffic security policy.
- Check for firewall firmware / OS updates.
- Allow only HTTPS access to the GUI and SSH access to the CLI.
- Re-direct HTTP GUI logins to HTTPS.
- Change the HTTPS and SSH admin access ports to non-standard ports.
- Restrict logins from trusted hosts.
- Set up two-factor authentication for administrators.
- Create multiple administrator accounts.
- Modify administrator account lockout duration and threshold values.
- Check if all management access from the Internet is turned off, if it does not have a clear business need. At most, HTTPS and PING should be enabled.
- Ensure that your SNMP settings are using SNMPv3 with encryption and configure your UTM profiles.
- All firewall policies should be reviewed every 3 months to verify the business purpose.

## Routers

- Do not use Default password for your router.
- Check if the router block access to a modem by IP address.
- Ensure that router admin gets an alert when a new device joins the network.
- Most routers let you disable UPnP on the LAN side.
- Enable port forwarding and IP filtering for your router.

`LOCAL ADMINISTRATION`

- Check if the router supports HTTPs, in some routers it is disabled by default.
- If HTTPS is supported, can admin access be limited exclusively to HTTPS?.
- Check if the TCP/IP port used for the web interface can be changed.
- To really prevent local admin access, limit the LAN IP address to a single IP address that is both outside the DHCP range and not normally assigned.
- Check if the admin access can be limited to Ethernet only.
- Check if the router access can be restricted by SSID and/or by VLAN.
- The router should not allow multiple computers to logon at the same time using the same userid.
- Check if there is some type of lockout after too many failed attempts to login to the web interface.

`REMOTE ADMINISTRATION`

- Make sure the remote administration settings are turned off by default.
- Check if the port number can be changed remotely.
- If you forget to logout from the router, eventually your session should time out, and, you should be able to set the time limit, the shorter, the more secure.

`ROUTER FIREWALL`

- Inbound WAN: What ports are open on the WAN/Internet side? The most secure answer is none and you should expect any router not provided by an ISP to have no open ports on the Internet side. One exception is old school Remote Administration, which requires an open port. Every open port on the WAN side needs to be accounted for, especially if the router was provided by an ISP; they often leave themselves a back door. The Test your Router page links to many websites that offer firewall tests. That said, none of them will scan all 65,535 TCP ports or all 65,535 UDP ports. The best time to test this is before placing a new router into service.

- Inbound LAN: What ports are open on the LAN side? Expect port 53 to be open for DNS (probably UDP, maybe TCP). If the router has a web interface, then that requires an open port. The classic/standard utility for testing the LAN side firewall is nmap. As with the WAN side, every port that is open needs to be accounted for.

- Outbound: Can the router create outgoing firewall rules? There are all sorts of attacks that can be blocked with outgoing firewall rules.
  Generally, consumer routers do not offer outbound firewall rules while business class routers do. In addition to blocking, it would be nice if the blocks were logged for auditing purposes. Note however, that devices connected to Tor or a VPN will not obey the outbound firewall rules.

## Switches

- Check if the latest firmware is used.
- Check the switch's user guide's for security features and see if the required ones have been implemented properly.
- Create an Enable Secret Password Encrypt Passwords on the device.
- Use an external AAA server for User Authentication.
- Create separate local accounts for User Authentication Configure Maximum Failed Authentication Attempts.
- Restrict Management Access to the devices to specific IPs only.
- Enable Logging for monitoring, incident response and auditing. You can enable logging to an internal buffer of the device or to an external Log server.
- Enable Network Time Protocol (NTP) - You must have accurate and uniform clock settings on all network devices in order for log data to be stamped with the correct time and timezone. This will help tremendously in incident handling and proper log monitoring and correlation.
- Use Secure Management Protocols if possible.
- Restrict and Secure SNMP Access.

## Linux Servers

- Update your package list and upgrade your OS.
- Remove unnecessary packages.
- Detect weak passwords with John the Ripper.
- Verify no accounts have empty passwords.
- Set password rules.
- Set password expiration in login.defs.
- Disable USB devices. (for headless servers)
- Check which services are started at boot time.
- Detect all world-writable files.
- Configure iptables to block common attacks.
- Set GRUB boot loader password.
- Disable interactive hotkey startup at boot.
- Enable audited to check for read/write events.
- Secure any Apache servers.
- Install and configure UFW.
- Configure SSH securely.
- Disable telnet.
- Configure sysctl securely.
- Lock user accounts after failed attempts with Fail2Ban.
- Configure root user timeout.
- Check for hidden open ports with netstat.
- Set root permissions for core system files.
- Scan for rootkits.
- Check that shut down mode is enabled for sensitive event log alerts.
- Check that all event log data is being securely backed up.
- Evaluate event log monitoring process.
- Keep watch for any users logging on under suspicious circumstances.
- Check remote access logs regularly.
- In case of remote access activity: Make sure that the suspicious activity is flagged and documented.
- Make sure that the Suspected account privileges temporarily frozen.
- Evaluate server configuration control process.
- Update service packs and patches for software.
- Check event log monitoring is properly configured:.
- Check that all user account logins are being recorded.
- Check that all system configuration changes are being recorded.
- Make sure that there is a process in place for changing system configurations.
- Ensure start-up processes are configured correctly.
- Remove unnecessary startup processes.
- Ensure regular users cannot change system startup configuration.
- Remove unused software and services.
- Run a full system anti-virus scan.
- Review your server firewall security settings and make sure everything is properly configured.
- Disable or remove all user accounts that haven't been active in the last 3 months.
- Make sure that membership to both the admin and superadmin group is restricted to as few users as possible without causing any problems.

## Windows Servers

- Install the latest service packs and hotfixes from Microsoft.
- Enable automatic notification of patch availability.
- Set minimum password length.
- Enable password complexity requirements.
- Do not store passwords using reversible encryption. (Default)
- Configure account lockout policy.
- Restrict the ability to access this computer from the network to Administrators and Authenticated Users.
- Do not grant any users the 'act as part of the operating system' right. (Default)
- Restrict local logon access to Administrators.
- Deny guest accounts the ability to logon as a service, batch job, locally or via RDP
- Place the warning banner in the Message Text for users attempting to log on.
- Disallow users from creating and logging in with Microsoft accounts.
- Disable the guest account. (Default)
- Require Ctrl+Alt+Del for interactive logins. (Default)
- Configure machine inactivity limit to protect idle interactive sessions.
- Configure Microsoft Network Client to always digitally sign communications.
- Configure Microsoft Network Client to digitally sign communications if server agrees. (Default)
- Disable the sending of unencrypted passwords to third party SMB servers.
- Configure Microsoft Network Server to always digitally sign communications.
- Configure Microsoft Network Server to digitally sign communications if client agrees.
- Disable anonymous SID/Name translation. (Default)
- Do not allow anonymous enumeration of SAM accounts. (Default)
- Do not allow anonymous enumeration of SAM accounts and shares.
- Do not allow everyone permissions to apply to anonymous users. (Default)
- Do not allow any named pipes to be accessed anonymously.
- Restrict anonymous access to named pipes and shares. (Default)
- Do not allow any shares to be accessed anonymously.
- Require the "Classic" sharing and security model for local accounts. (Default)
- Allow Local System to use computer identity for NTLM.
- Disable Local System NULL session fallback.
- Configure allowable encryption types for Kerberos.
- Do not store LAN Manager hash values.
- Set LAN Manager authentication level to only allow NTLMv2 and refuse LM and NTLM.
- Enable the Windows Firewall in all profiles (domain, private, public). (Default)
- Configure the Windows Firewall in all profiles to block inbound traffic by default. (Default)
- Configure Windows Firewall to restrict remote access services (VNC, RDP, etc.) to authorized organisation-only networks .
- Configure Windows Firewall to restrict remote access services (VNC, RDP, etc.) to the organization VPN.
- Digitally encrypt or sign secure channel data (always). (Default)
- Configure machine inactivity limit to protect idle interactive sessions.
- Require strong (Windows 2000 or later) session keys.
- Configure the number of previous logons to cache.
- Configure Account Logon audit policy.
- Configure Account Management audit policy.
- Configure Logon/Logoff audit policy.
- Configure Policy Change audit policy & Privilege Use audit policy.
- Configure Event Log retention method and size.
- Configure log shipping (e.g. to Splunk).
- Disable or uninstall unused services.
- Configure user rights to be as secure as possible: Follow the Principle of Least Privilege
- Ensure all volumes are using the NTFS file system.
- Configure file system as well as registry permissions.
- Disallow remote registry access if not required.
- Set the system date/time and configure it to synchronize against Organization time servers.
- Install and enable anti-spyware and antivirus software.
- Configure anti-virus software to update daily.
- Configure anti-spyware software to update daily.
- Provide secure storage for Confidential (category-I) Data as required.
- Security can be provided by means such as, but not limited to, encryption, access controls, file system audits, physically securing the storage media, or any combination thereof as deemed appropriate.
- Install software to check the integrity of critical operating system files.
- If RDP is utilized, set RDP connection encryption level to high.