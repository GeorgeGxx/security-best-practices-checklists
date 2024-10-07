## Firewall Configuration

    sudo nano /etc/sysconfig/iptables

    -A INPUT -p tcp -m tcp --dport 10000 -j ACCEPT

    https://localhost.localdomain:10000

    https://localhost:10000

    https://10.0.0.101:10000

    yum install firewalld -y

    systemctl start firewalld.service

    firewall-cmd --state

    firewall-cmd --get-default-zone

    firewall-cmd --list-all

    firewall-cmd --get-zones

    firewall-cmd --zone=home --list-all


    yum install epel-release

    yum install iptables-services

    systemctl enable firewalld

    systemctl start firewalld

    systemctl stop firewalld

    systemctl disable firewalld

    systemctl status firewalld

    systemctl enable iptables

    systemctl start iptables

    systemctl stop iptables

    systemctl status iptables.service

    journalctl -xe