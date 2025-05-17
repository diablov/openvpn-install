克隆自https://github.com/angristan/openvpn-install

转载注明出处：
https://github.com/diablov/openvpn-install

之前脚本太老了，更新了一下：
1. 更新easyrsa为3.2.2版本（之前为3.1.2）
2. 增加重新安装功能
3. 考虑easyrsa不一定能下载成功，项目里面自带了一个EasyRSA-3.2.2.tgz
4. 增加自动安装功能
5. 考虑更改路由，增加了个提示

新版菜单如下：
```
What do you want to do?
   1) Add a new user
   2) Revoke existing user
   3) Remove OpenVPN
   4) Exit
   5) Reinstall OpenVPN
   6) Chang Subnet
Select an option [1-6]: 
```

放到任意目录，运行：
```
自动安装：
sudo ./autoinstall.sh

或者手动安装：
sudo ./openvpn-install.sh
```

常见修改：
server.conf:
```
tun-mtu 1400
```

ovpn文件修改：
```
tun-mtu 1400
route-nopull
route 10.100.0.0 255.255.255.0 vpn_gateway

#ignore-unknown-option block-outside-dns
#setenv opt block-outside-dns # Prevent Windows 10 DNS leak

```


