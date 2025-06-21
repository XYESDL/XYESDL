# 音频技术

[广州国际专业灯光、音响展](https://www.soundlight.cn/)

[PLSG年度培训课程](https://wx.vzan.com/live/pc/index?liveId=1948707481)

## 网络音频协议

时钟同步

### [DANTE](https://www.audinate.com/ "官网")

[Dante BiLi官方](https://space.bilibili.com/677396871?spm_id_from=333.337.search-card.all.click)

系统管理软件

```vue
- Dante Controller 
- Dante Domain Manager
- Dante Director
```
[Dante Controller](https://www.getdante.com/products/software-essentials/dante-controller/)

#### 交换机配置要求

```vue
在Dante网络中不能使用交换机的EEE功能（绿色以太网或IEEE802.3az）。

转发延迟<10μs。

冗余网络需要交换机支持快速生成树协议(RSTP)。

支持QOS、IGMP（Enable IGMP Snooping on all VLANS）
```
![QoS](/QoS.png)

![IGMP](/IGMP.png)

![IP](/IP.png)

![video](/video.png)

![audio](/audio.png)

配置工具[Dante Controller](https://www.getdante.com/products/software-essentials/dante-controller/ "下载")

```vue
电脑开DHCP，设置主时钟，路由设置
```

连接方式：冗余、菊花链

### AVB

#### 依赖AVB交换机

```vue
AVB（IEEE 802.1AS/AVB）严格要求通过支持AVB的交换机实现：

时钟同步（PTP精密时间协议）：交换机作为主时钟源分发同步信号。

流量整形（802.1Qav）：直连时无法保障音频流的优先级和带宽预留，可能导致延迟或丢包。

设备角色：AVB设备默认是终端节点（Endpoints），不具备交换或转发能力。

```

#### AVB交换机要求

```vue
AVB交换机必须支持以下 IEEE 标准：

802.1AS（时间同步）

802.1Qat（流预留协议，SRP）

802.1Qav（流量整形，FQTSS）

802.1BA（AVB系统架构）
```

#### 交换机选型

```vue
Cisco、Netgear
```

### AES67

## 调音台

### [YAMAHA](https://www.yamaha.com.cn/)

### [Behringer](https://www.behringer.com/)

```vue
X-USB连接配置
    1.驱动下载
    2.input选择card通道
    3.card输出选择本地通道
```

## 音频处理器

### [Biamp](https://www.biamp.com/)

[Tesira编译、控制-Control、Canvas](https://www.biamp.com/support/downloads?products=Tesira&resources=Software/Firmware&languages=English)

[Tesira_Text_Protocol](https://support.biamp.com/Tesira/Control/Tesira_Text_Protocol)

[Tesira_command_string](https://support.biamp.com/Tesira/Control/Tesira_command_string_calculator)



```vue
1.参数调节
2.编译
3.上传
```

## 增益架构

合理的增益架构、频响曲线可最大程度还原声音。

### 输入输出增益调节

```vue
输入推杆+6的余量，观察pink调整增益
调整功放旋钮，满足正常场景使用
```

### 保护设置

```vue
输入通道压缩器
输出通道限幅器
```

## 音频系统校正

主要目的：解决因音箱缺陷、摆放、环境等问题对听感的影响。

### 系统测量软件

[国内软件VOS](https://www.chaopinspace.cn/#/)

[国外软件SMAART](https://www.rationalacoustics.com/pages/smaart-home)

![vos4](/qx.jpg)

```vue
连接测量麦克风、声卡
设置好测量、参考、输入、输出通道、DAW输出模式
导入测量话筒曲线校准文件
选择测量模式
```
### 设置分频点

```vue
播放Pink Noise,观察频响曲线
选择合适分频点及斜率
```
### 频响曲线校正

```vue
校正频响曲线，首先看相干性曲线，减少环境对测量结果影响
播放Pink Noise，调整到合适增益，插入延时，保存曲线
通过自动EQ调节，导入配置
```
### 相位对齐

```vue
用于调整各音箱频响重叠部分（避免因相位问题造成能量衰减）
话筒放置合适位置，多点位测量
通过反相或延时调整
```

### 声压级校准

```vue
使用校准器，多点位测量
```
