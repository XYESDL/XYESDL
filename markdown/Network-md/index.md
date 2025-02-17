# 网络

## 交换机

交换机模拟软件ENSP

```vue
查看设备型号和版本信息
display version

查看设备运行时间
display device

查看设备名称和系统时间
display clock

查看所有接口的简要状态
display interface brief

查看指定接口的详细信息（如GigabitEthernet 0/0/1）
display interface GigabitEthernet 0/0/1

查看接口的统计信息（如收发包数量、错误包等）
display interface counters

查看所有VLAN、VLAN 10、接口所属的VLAN信息
display vlan、vlan 10、port vlan

查看MAC地址表、动态学习的MAC地址、指定VLAN的MAC地址
display mac-address、mac-address dynamic、mac-address vlan 10

查看静态路由、OSPF路由、IP路由表、ARP表、指定IP的ARP信息
display ip routing-table protocol static、ospf routing、ip routing-table、arp、arp 192.168.1.1

查看系统日志、告警信息、CPU使用率、内存使用率、历史CPU使用率
display logbuffer、trapbuffer、diagnostic-information、cpu-usage、memory-usage、cpu-usage history

查看生成树协议（STP）状态、ACL规则、指定ACL的详细信息
display stp、acl all、acl 2001

查看指定端口的STP信息（如GigabitEthernet 0/0/1）
display stp interface GigabitEthernet 0/0/1

查看DHCP服务器状态、DHCP地址池信息
display dhcp server statistics、dhcp pool

查看已保存的配置、当前运行的配置
display saved-configuration、current-configuration

保存当前配置、重启交换机
save、reboot

查看设备温度、电源状态、风扇状态
display temperature、power、fan
```

```vue
登录交换机并进入系统视图
[Huawei] system-view

进入需要配置的接口视图。配置接口GigabitEthernet 0/0/1：
[Huawei] interface GigabitEthernet 0/0/1
[Huawei-GigabitEthernet0/0/1]

为接口配置IP地址（通常用于管理接口或三层接口）：
[Huawei-GigabitEthernet0/0/1] ip address 192.168.1.1 255.255.255.0

启用或禁用接口
[Huawei-GigabitEthernet0/0/1] undo shutdown\shutdown

设置速率为100Mbps，双工模式为全双工：
[Huawei-GigabitEthernet0/0/1] speed 100
[Huawei-GigabitEthernet0/0/1] duplex full
恢复为自动协商：
[Huawei-GigabitEthernet0/0/1] undo speed
[Huawei-GigabitEthernet0/0/1] undo duplex

为接口添加描述信息，便于管理：
[Huawei-GigabitEthernet0/0/1] description "Link to Server"

将接口加入VLAN 10（Access模式）：
[Huawei-GigabitEthernet0/0/1] port link-type access
[Huawei-GigabitEthernet0/0/1] port default vlan 10

将接口设置为Trunk模式，并允许VLAN 10通过：
[Huawei-GigabitEthernet0/0/1] port link-type trunk
[Huawei-GigabitEthernet0/0/1] port trunk allow-pass vlan 10

修改接口的MTU值（默认为1500字节）：
[Huawei-GigabitEthernet0/0/1] mtu 1600

启用接口的流量控制功能：
[Huawei-GigabitEthernet0/0/1] flow-control

查看当前接口的配置信息：
[Huawei-GigabitEthernet0/0/1] display this

配置完成后，保存配置：
[Huawei] save

退出接口视图，返回系统视图：
[Huawei-GigabitEthernet0/0/1] quit

查看接口状态：
[Huawei] display interface GigabitEthernet 0/0/1

查看接口简要信息：
[Huawei] display interface brief

接口模式：根据需求选择Access、Trunk或Hybrid模式。

IP地址配置：只有三层接口（如VLAN接口或路由接口）才需要配置IP地址。

保存配置：配置完成后务必使用save命令保存，否则重启后配置会丢失
```

```vue
创建VLAN、批量创建VLAN、删除VLAN
[Huawei] vlan 10、vlan batch 10 20 30、undo vlan 10
[Huawei-vlan10] quit

三层交换与VLAN间路由
创建VLAN接口并配置IP地址：
[Huawei] interface Vlanif 10
[Huawei-Vlanif10] ip address 192.168.10.1 255.255.255.0
[Huawei-Vlanif10] quit

启用三层交换功能：
[Huawei] ip routing

添加静态路由：
[Huawei] ip route-static 192.168.2.0 255.255.255.0 192.168.1.1
删除静态路由：
[Huawei] undo ip route-static 192.168.2.0 255.255.255.0 192.168.1.1

动态路由协议
启用OSPF：
[Huawei] ospf 1
[Huawei-ospf-1] area 0
[Huawei-ospf-1-area-0.0.0.0] network 192.168.1.0 0.0.0.255
启用RIP：
[Huawei] rip 1
[Huawei-rip-1] network 192.168.1.0

链路聚合（Eth-Trunk）
创建Eth-Trunk：
[Huawei] interface Eth-Trunk 1
[Huawei-Eth-Trunk1] quit
将接口加入Eth-Trunk：
[Huawei] interface GigabitEthernet 0/0/1
[Huawei-GigabitEthernet0/0/1] eth-trunk 1
[Huawei-GigabitEthernet0/0/1] quit

启用STP：
[Huawei] stp enable

配置STP模式（如MSTP）
[Huawei] stp mode mstp

查看STP状态：
[Huawei] display stp

创建基本ACL：
[Huawei] acl 2001
[Huawei-acl-basic-2001] rule permit source 192.168.1.0 0.0.0.255
[Huawei-acl-basic-2001] quit

应用ACL到接口：
[Huawei] interface GigabitEthernet 0/0/1
[Huawei-GigabitEthernet0/0/1] traffic-filter inbound acl 2001

创建流量分类：
[Huawei] traffic classifier c1
[Huawei-classifier-c1] if-match acl 2001
[Huawei-classifier-c1] quit

创建流量行为：
[Huawei] traffic behavior b1
[Huawei-behavior-b1] remark dscp af11
[Huawei-behavior-b1] quit

创建QoS策略并应用：
[Huawei] traffic policy p1
[Huawei-trafficpolicy-p1] classifier c1 behavior b1
[Huawei-trafficpolicy-p1] quit
[Huawei] interface GigabitEthernet 0/0/1
[Huawei-GigabitEthernet0/0/1] traffic-policy p1 inbound

启用DHCP服务器：
[Huawei] dhcp enable

创建DHCP地址池：
[Huawei] ip pool pool1
[Huawei-ip-pool-pool1] network 192.168.1.0 mask 255.255.255.0
[Huawei-ip-pool-pool1] gateway-list 192.168.1.1
[Huawei-ip-pool-pool1] quit

在接口上启用DHCP：
[Huawei] interface Vlanif 10
[Huawei-Vlanif10] dhcp select global

启用端口安全：
[Huawei] interface GigabitEthernet 0/0/1
[Huawei-GigabitEthernet0/0/1] port-security enable

限制MAC地址数量：
[Huawei-GigabitEthernet0/0/1] port-security max-mac-num 5

启用SNMP：
[Huawei] snmp-agent

配置SNMP团体名：
[Huawei] snmp-agent community read public
[Huawei] snmp-agent community write private

配置日志主机：
[Huawei] info-center loghost 192.168.1.100

设置日志级别：
[Huawei] info-center source default channel loghost log level informational

配置Telnet登录：
[Huawei] user-interface vty 0 4
[Huawei-ui-vty0-4] authentication-mode password
[Huawei-ui-vty0-4] set authentication password cipher Huawei@123
[Huawei-ui-vty0-4] user privilege level 15

配置SSH登录：
[Huawei] stelnet server enable
[Huawei] rsa local-key-pair create
[Huawei] user-interface vty 0 4
[Huawei-ui-vty0-4] authentication-mode aaa
[Huawei-ui-vty0-4] protocol inbound ssh

```
## 路由器
DDNS、DNS、DHCP、DMZ、UPNP、端口映射

## 光猫

超级管理员账号密码获取、桥接[参考图文](https://www.bilibili.com/opus/907251136224821285?spm_id_from=333.999.0.0)

## 