create:
# VPC
* name: freshguard-nerwork
* mode: Custom
* subnet: backend
    * IP Rage: 192.168.1.0/28
* subnet: machine learning
    * IP Rage: 192.168.1.16/28
* subnet: database
    * IP Rage: 192.168.1.32/28
* firewalls:
    * Allow SSH
        * TCP: 23
    * Allow HTTPS to Backend API
        * TCP: 80
* Cloud NAT
    External IP:
* Service Acounts:
    * Backend
        * Roles:
    * ML VM
        * Roles:
    * Cloud SQL
        * Roles:
