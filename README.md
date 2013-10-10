Build Instructions - On an EL6 machine
  
    sudo su

    wget http://repo.zabbix.com/zabbix/2.0/rhel/6/SRPMS/zabbix-2.0.5-1.el6.src.rpm
    rpm -ivh zabbix-2.0.5-1.el5.src.rpm

    yum install rpm-build java-devel libssh2-devel OpenIPMI-devel curl-devel unixODBC-devel sqlite-devel iksemel-devel gnutls-devel openldap-devel net-snmp-devel postgresql-devel mysql-devel

    git clone https://github.com/RiotGamesMinions/zabbix.git
    cd zabbix

    cp zabbix.spec /root/rpmbuild/SPECS/
    cp *.patch /root/rpmbuild/SOURCES/
    rpmbuild -ba /root/rpmbuild/SPECS/zabbix.spec 

The rpms will be under /root/rpmbuild/RPMS
