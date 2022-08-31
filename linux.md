## Windows 10 Linux Subsystem磁盘加载
sudo umount /mnt/d
sudo mount -t drvfs D: /mnt/d

## CentOS 防火墙设置
查看当前所有的iptables配置  
iptables -L -n  
在tcp协议中，禁止所有的ip访问本机的8080端口  
iptables -I INPUT -p tcp --dport 8080 -j DROP  
允许192.168.1.123访问本机的1521端口  
iptables -I INPUT -s 211.211.211.211 -p tcp --dport 8080 -j ACCEPT  
保存当前规则  
/etc/rc.d/init.d/iptables save service iptables restart  
参考(https://tsov.net/uupee/24435/)

## Ubuntu firewall-cmd命令

查看防火墙状态：firewall-cmd --state

查看防火墙：firewall-cmd --list-all

更新防火墙规则：firewall-cmd --reload

增加80端口，永久生效
firewall-cmd --add-port=80/tcp --permanent
firewall-cmd --reload