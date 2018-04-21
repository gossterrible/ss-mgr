[shadowsocks-manager]

Demo：https://wall.gyteng.com

# Requirements 
Centos7 X64, tested on Tencent cloud, digitialocean, interserver, ethernetservers.
Other versions have not been tested and are theoretically available.
# Installation script

## Installing ss-mgr Master node and node
This script includes the master and the node. During installation,the server is automatically added as a node.
```
wget -N --no-check-certificate https://raw.githubusercontent.com/gossterrible/ss-mgr/master/sm.sh && chmod +x sm.sh && bash sm.sh
```
After the installation is complete visit your IP address an you will ss-mgr should be installed.


## Add a new node
On a new server use the script below to install a new node.
```
wget -N --no-check-certificate https://raw.githubusercontent.com/gossterrible/ss-mgr/master/sm_node.sh && chmod +x sm_node.sh && bash sm_node.sh
```

-Enter the password (This password will be used to connect the node with the host server)
![](http://cdn.mmmxcc.cn/blog/20170514/135830856.png)
- Enter the ip or address for the new node, password, and select the encryption method used wheninstalling node
![](http://cdn.mmmxcc.cn/blog/20170514/140131877.png)

#Note
- The first registered user is the administrator.
- Register your second account and you can see your remaining time, which is generally 8 hours. You can click on the renewal fee and select any amount. After paying, you can see that the time will increase.
- By default,a hotmail mailbox is used.If your main server is located in mainland china you can have issues with connection timeout when sending emails.
- If your using an old kernel version you might have some promt like the one below Pressing Enter will be ok.
![](http://cdn.mmmxcc.cn/blog/20170513/135239354.png)

If your not familiar with using docker to start the processes you can use the Screen command below to start the processes in the background.
```
screen -dmS ss-manager ss-manager -m aes-256-cfb -u --manager-address 127.0.0.1:4000
cd /root/shadowsocks-manager/
screen -dmS ss node server.js -c /root/.ssmgr/ss.yml
screen -dmS webgui node server.js -c /root/.ssmgr/webgui.yml
```
---
If you have any problem you can get help from this telegram group: https://t.me/feiyangss

---
Credits：
Original Chinese version:https://github.com/mmmwhy/ss-mgr 
Reference: https://code.momok.xyz/server/deploy-ss-manager.html
Shadowsocks Manager : https://github.com/shadowsocks/shadowsocks-manager
