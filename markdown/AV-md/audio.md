# 音频技术

[广州国际专业灯光、音响展](https://www.soundlight.cn/)

[PLSG年度培训课程](https://wx.vzan.com/live/pc/index?liveId=1948707481)

## 网络音频协议

时钟同步

### [DANTE](https://www.audinate.com/ "官网")

Dante [BiLi官方](https://space.bilibili.com/677396871?spm_id_from=333.337.search-card.all.click)

```vue
在Dante网络中不要使用网络交换机的EEE功能。
使用可管理交换机时，关闭使用Dante的所有端口的EEE功能。
使用不可管理的交换机，请勿使用支持EEE功能的交换机。
EEE（Energy Efficient Ethernet，高能效以太网）功能是在网络流量稀少时降低以太网设备功耗的技术。还被称为“绿色以太网”或“IEEE802.3az”。
```

配置工具[Dante Controller](https://www.getdante.com/products/software-essentials/dante-controller/ "下载")

```vue
电脑开DHCP，设置主时钟，路由设置
```

连接方式：冗余、菊花链

### AVB

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

[Tesira](https://www.biamp.com/support/downloads?products=Tesira&resources=Software/Firmware&languages=English)客户端软件Biamp Canvas

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
