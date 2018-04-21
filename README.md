# shadowsocks-manager: A shadowsocks web interface

Demo：https://wall.gyteng.com

# Admin pannel
![](https://camo.githubusercontent.com/5eeea2edea09a6da05c945676a9b98e9956f817e/687474703a2f2f63646e2e6d6d6d7863632e636e2f626c6f672f32303137303531332f3133353334343436382e706e67)

![](https://camo.githubusercontent.com/e17b1432e87197926c6d79d88c6bf818c350d798/687474703a2f2f63646e2e6d6d6d7863632e636e2f626c6f672f32303137303531332f3133353335373439372e706e67)


# Requirements 
Centos7 X64, tested on Tencent cloud, digitialocean, interserver, ethernetservers.
Other versions have not been tested and are theoretically available.
# Installation script

## Installing ss-mgr Master-node and node
Running this script on your server automatically creates a master-node and a node.
```
wget -N --no-check-certificate https://raw.githubusercontent.com/gossterrible/ss-mgr/master/sm.sh && chmod +x sm.sh && bash sm.sh
```
After the installation is complete visit your IP address an you will ss-mgr should be  installed.


## Add a new node
On a new server use the script below to install a new node.
```
wget -N --no-check-certificate https://raw.githubusercontent.com/gossterrible/ss-mgr/master/sm_node.sh && chmod +x sm_node.sh && bash sm_node.sh
```

-Enter the password (This password will be used to connect the node with the Master-node)
![](http://cdn.mmmxcc.cn/blog/20170514/135830856.png)
- Enter the ip address or url of the new node, password, and select the encryption method used when installing the node.
![](http://cdn.mmmxcc.cn/blog/20170514/140131877.png)

# Note:
- The first registered user is the administrator.
- Register your second account and you can see your remaining time, which is generally 8 hours. You can click on the renewal fee and select any amount. After paying, you can see that the time will increase.
- By default,a hotmail mailbox is used.If your main server is located in mainland china you can have issues with connection timeout when sending emails. You can edit the default email account by modifying the ```/root/.ssmgr/webgui.yml``` file.
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
