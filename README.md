# Ansbile-webservers-playbook
This playbook will help us to installing web server related some packages on linux systems(Centos 7). To see the playbook clear, use raw tab.

vim web-server.yml

---
 - hosts: [hosts name from /etc/ansible/hosts file]
 
   user: [Remote user name]

   tasks:
    - name: install httpd
      yum:
        name: httpd

    - name: install php and maria db
      yum: name={{item}} state=installed
      with_items:  
      - php
      - php-mysql
      - php-pdo
      - php-gd
      - php-mbstring
      - mariadb-server
      - mariadb
      - ntpd
