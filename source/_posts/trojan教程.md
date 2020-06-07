---
categories: 
- 网络
tags:
- 上网
---



- [一枝红杏](https://yizhihongxing.network/index.html#home)
- [服务优势](https://yizhihongxing.network/index.html#services)
- [产品特性](https://yizhihongxing.network/index.html#features)
- [价格](https://yizhihongxing.network/index.html#pricing)
- [客户中心](https://order.yizhihongxing.network/knowledgebase.php?action=displayarticle&id=14)

https://order.yizhihongxing.network/knowledgebase.php?action=displayarticle&id=14#)

## 一、【Windows】【推荐】 Trojan-QT5 设置方法

**本文导入配置文件适用于 V0.04a 以上客户端（帮助 > 关于 查看客户端版本号）****目前客户端流量统计功能无法正常工作，显示用量 0 是正常的****教程对应的服务版本为： Trojan 服务**

<!--more-->

## 1. 下载客户端

前往 技术支持 > 资源下载 > Trojan 进行下载： [Trojan-QT5 Windows 客户端(点击下载)](https://order.yizhihongxing.network/dl.php?type=d&id=19)

- 如出现 VCRUNTIME140.dll 和 MSVCP140.dll 缺失,需点击以下链接安装 Visual C++ redistributable packages for Visual Studio 2015, 2017 and 2019
  x86: [vc_redist.x86.exe](https://aka.ms/vs/16/release/vc_redist.x86.exe)
  x64: [vc_redist.x64.exe](https://aka.ms/vs/16/release/vc_redist.x64.exe)
- **如果点击连接时时闪退/报错/没有反应，请确认没有其他程序占用客户端的监听端口，建议将其他代理客户端退出后试试**

## 2. 查看节点信息

登入到客户中心，依次访问 Services > [My Products & Services](https://order.yizhihongxing.network/clientarea.php?action=products)[( ](https://order.yizhihongxing.network/clientarea.php?action=products)[我的产品与服务 ](https://order.yizhihongxing.network/clientarea.php?action=products)[- 点击前往)](https://order.yizhihongxing.network/clientarea.php?action=products) ，查看 Trojan 协议对应的 `Rose` 服务器信息。

## 3. 添加节点

添加方式支持
手动(3.1)
导入配置文件(3.2)  **(<-推荐)** 
扫码(3.3)

### 3.1 手动添加

推荐通过 **导入配置文件(3.2部分)(可以一次性全部导入)** / **扫码(3.3部分)**  的方式进行添加，本部分主要用于说明节点设置页面各选项的作用。

打开客户端，点击 `连接` > `添加` > `手动(M)`，在弹出的窗口中按照如下的内容填写。

红框部分为必须填写的内容，绿框部分可以根据情况进行修改，选项说明见图片底部。

![添加节点](https://i.loli.net/2020/03/09/DmPrIMWphQ9ixXR.png)

- `配置名称` : 节点的备注名称，可以自由填写
- `服务器地址`： 填写选用的服务器地址域名或是 IP
- `服务器端口`： 我们 Trojan 服务的端口均为 443
- `密钥`： 填写服务连接密码
- `本地端口` / `本地HTTP端口`： SOCKS5 与 HTTP 的监听端口，一般保持默认即可，**由于 Trojan / Shadowsocks 客户端默认端口一致，因此不要同时运行两个客户端，如有同时运行需求，请修改其中一个客户端的 Socks5 监听端口**
- `本地服务类型`: 选择 `SOCKS5 + HTTP` 会在连接后提供 HTTP 协议的监听，否则仅监听 SOCKS 端口
- `自动化`： 勾选后会在程序启动时自动连接该节点

点击 OK 后完成添加。

端口设置，请点击顶部菜单 **设置 > 高级设置** 进行设置，下图为客户端的默认设置

![img](https://i.loli.net/2020/02/29/7z3NXCJ94F1aPbc.png)

### 3.2 导入配置文件

打开服务详情页面，点击密码底部的 GUI-Config  Download 下载配置文件 `gui-config.json`。

![img](https://i.loli.net/2020/03/09/aAorsN6xnhe5VtR.png)

然后点击客户端顶部的 `文件` > `从 gui-config 导入连接(I)` ：

![导入配置文件](https://i.loli.net/2020/02/29/HFcdqJBKQye35iu.png)

导入后选择一个节点再点击顶部的链接按钮进行使用，**配置中提供的本地 SOCKS5 端口为 1080 与 Shaodowsocks 客户端默认端口一致，因此点击后如果没有反应请****确认没有其他已连接的节点或是其他程序占用了客户端的本地端口**。

选中的节点双击可以打开编辑配置，选项说明请查看 3.1 部分。

 ![img](https://i.loli.net/2020/03/09/4ymiBfIb9cErkuH.png)

 

### 3.3 扫描二维码添加

打开服务详情页面，点击服务器信息最后一列的二维码图标显示二维码。

![显示二维码](https://i.loli.net/2020/03/09/aAorsN6xnhe5VtR.png)

然后点击客户端顶部菜单的 `连接` > `添加` > `扫描屏幕上的二维码(S)`

![二维码添加](https://i.loli.net/2020/02/20/KTLePmyRSJOuExX.png)

参考手动设置部分的选项说明决定是否修改设置，点击 OK 后完成添加。

![添加节点](https://i.loli.net/2020/03/09/DmPrIMWphQ9ixXR.png)

3.3.1 粘贴 URI 添加

点击客户端顶部菜单的 `连接` > `添加` >  URI 

**粘贴 产品详情 -点击 节点地址旁边 齿轮图标 - Trojan Url 下的内容**

### 4. 设置开机启动

点击顶部菜单 `设置` > `常规设置` , 勾选 `登陆时启动` 即可。

![开机启动](https://i.loli.net/2020/02/29/P7YoDJ46rRqy9pN.png)

### 5. 注意事项

**Trojan - qt5 与 Shadowsocks-WIN 的客户端默认监听端口均为 1080 ，因此一般情况下请不要同时运行两个客户端。**
**如果有同时运行需求请修改任意一个客户端的本地端口设置。**

**此答案有用么？**  					是 					否 				 

### Also Read

- #### ![Article Icon](https://order.yizhihongxing.network/images/article.gif) [【Android】 Trojan Igniter 设置方法 ](https://order.yizhihongxing.network/knowledgebase.php?action=displayarticle&id=18)(查看: 5619)

- #### ![Article Icon](https://order.yizhihongxing.network/images/article.gif) [Trojan 服务客户端设置教程索引 ](https://order.yizhihongxing.network/knowledgebase.php?action=displayarticle&id=13)(查看: 22560)

- #### ![Article Icon](https://order.yizhihongxing.network/images/article.gif) [【MacOS】【推荐】TrojanX 设置方法](https://order.yizhihongxing.network/knowledgebase.php?action=displayarticle&id=16) (查看: 4732)

[服务配置](https://order.yizhihongxing.network/knowledgebase.php?action=displayarticle&id=2)



## 二、【MacOS】【推荐】TrojanX 设置方法

TrojanX 的使用方法与 ShadowsocksX-NG 基本一致。

- 本文对应系统版本为 macOS 15.1
- 本文对应的客户端版本 1.0(1) / TrojanX-0.2.zip

## 1. 下载/安装客户端

### 1.1 下载

前往 技术支持 > 资源下载 > Trojan 进行下载： [TrojanX macOS 客户端(点击下载)](https://order.yizhihongxing.network/dl.php?type=d&id=20) 下载得到 **TrojanX-0.2.zip**

### 1.2 安装

找到刚才下载的 TrojanX-0.2.zip 并解压得到 TrojanX (一般在托盘的下载文件夹中点击 TrojanX-0.2.zip 后会自动解压并弹出文件窗口)。
将 TrojanX 文件拖动至应用程序中。
![trojanx-install.gif](https://i.loli.net/2020/03/10/4uFDNpxHUyJCe1K.gif)

然后找到应用程序中的 TrojanX ，初次打开时会提示无法验证开发者，点击取消然后按照下面图片所示在 Finder(访达) 中的应用程序文件夹中找到 TrojanX 右键选择打开。 
![trojanx-verify.png](https://i.loli.net/2020/03/10/U7d3fnK6SqZFGur.png)

右键选择打开。
![trojanx-force-open-01.png](https://i.loli.net/2020/03/10/lQodvR2qLJTse1C.png)

系统会再次确认，请选择打开。
![trojanx-force-open-02.png](https://i.loli.net/2020/03/10/7F1yLlB4mSROUMs.png)

第一次打开时需要输入用户密码进行授权，输入密码后点击好。

![trojanx-force-open-03.png](https://i.loli.net/2020/03/10/polJCuyeIAafHvm.png)

打开后可以在右上角找到 ![trojanx-indicator.png](https://i.loli.net/2020/03/10/wdZUAQzM5gF7DP3.png) 样式的客户端图标。

## 2. 查看节点信息

登入到客户中心，依次访问 Services > [My Products & Services](https://order.yizhihongxing.network/clientarea.php?action=products)[( ](https://order.yizhihongxing.network/clientarea.php?action=products)[我的产品与服务 ](https://order.yizhihongxing.network/clientarea.php?action=products)[- 点击前往)](https://order.yizhihongxing.network/clientarea.php?action=products) ，查看 Trojan 协议对应的 `Rose` 服务器信息。

![trojan-service-details.png](https://i.loli.net/2020/03/10/eIraRjy3mVQUxAH.png)

## 3. 添加节点

**目前 TrojanX 客户端不支持批量导入客户端，当前推荐使用 剪贴板导入(3.3部分) 的方式添加客户端。****。**

### 3.1 手动添加

右上角点击客户端图标，在菜单中点击 `服务器` > `服务器设置`，打开服务器窗口。
按照自己的服务器信息填写后点击确定。
![trojanx-add-server.png](https://i.loli.net/2020/03/10/EC9gDWvwNTZH2lr.png)

### 3.2 扫码添加

**在我们的测试中，存在一直提示无法找到二维码的情况，当前推荐选择 3.3 剪贴板导入的方法进行添加。**

在服务详情页面，点击 ![icon-qrcode.png](https://order.yizhihongxing.network/modules/servers/trojan/assets/images/qrcode.png) 打开需要添加的节点的二维码后，点击客户端菜单中的 `扫码屏幕上的二维码` 。
![trojanx-addby-qr.png](https://i.loli.net/2020/03/10/W6Y1mwvABgyGeV2.png)

macOS 15 中扫码需要授权给客户端屏幕录制权限，否则会提示找不到二维码。   

![img](https://i.loli.net/2020/03/10/WPxhdKwljRBJnsM.png)

我们需要在系统设置中进行权限设置，打开 `系统偏好设置` > `安全与隐私` ，在隐私标签中，左侧找到屏幕录制，勾选 TrojanX。

![trojan-qr-privacy.png](https://i.loli.net/2020/03/10/2XbW6Ge5TUtuIpo.png)

**当客户端菜单顶部显示 Trojan: On 时，表示 TrojanX 已经启用。**

### 3.3 剪贴板导入

在服务详情页面，点击 ![icon-config.png](https://i.loli.net/2020/03/10/DJgz8NcujAtKeUM.png) 打开需要添加的节点的服务器配置页面复制 Trojan 链接。

![trojanx-copy-url.png](https://i.loli.net/2020/03/10/oIwq1afQUsdgyk4.png)

之后点击客户端菜单中的 `从剪贴板导入服务器配置链接` 即可。
![trojanx-addby-url.png](https://i.loli.net/2020/03/10/6FLHeuZJGKD9Ahk.png)

## 4. 配置系统代理模式

点击屏幕右上方菜单栏的 ![trojanx-indicator.png](https://i.loli.net/2020/03/10/wdZUAQzM5gF7DP3.png) > `PAC 自动模式`。

![trojanx-set-pac.png](https://i.loli.net/2020/03/10/sKbi2rc3JZH8vVY.png)

### 注意事项

- **PAC模式：** 表示可以实现自动代理，及本来可以访问的网站不会经过代理，推荐日常使用。
- **全局模式：** 表示计算机内大多数流量都会经过代理，不推荐日常使用。
- **手动模式：** 不设置系统代理，浏览器需要配合扩展才可以使用
- Safari 需要使用系统代理， Firefox / Chrome 在没有安装代理扩展的情况下默认使用的也是系统代理

## 5. 设置浏览器扩展

**TrojanX 默认提供的本地 Socks5 监听端口为 1080 ，一般情况下不需要做改动，如果有同时运行其他 Shadowsocks / V2ray 的客户端可能存在冲突，所以不要同时运行多个代理客户端。**

### 配置 Chrome 的代理

**如需使用 Chrome 浏览器通过代理浏览网页，请参考下面链接：**
[Chrome安装SwitchyOmega浏览器插件（中文版）](https://order.yizhihongxing.network/knowledgebase.php?action=displayarticle&id=9)



## 三、【Android】 Trojan Igniter 设置方法

- 本文对应的客户端版本为 igniter 0.1.0-pre-alpha19
- 系统为 Android 10

## 1. 下载客户端

**更新至 alpha19 时请卸载原来的版本，然后重启手机后再安装使用**

- 从客户中心下载： [点击下载](https://order.yizhihongxing.network/dl.php?type=d&id=15)
- 从 Github 下载： [点击前往](https://github.com/trojan-gfw/igniter/releases) 下载 `app-release.apk```

## 2. 查看节点信息

登入到客户中心，访问 [我的服务(点击前往)](https://order.yizhihongxing.network/clientarea.php?action=products) ，查看 Trojan 协议对应的 `Trojan` 服务器信息。

![img](https://i.loli.net/2020/03/27/hf4RWv25Tl3xEAQ.png)

## 3. 添加节点

- 2.1 手动添加
- 2.2 扫码添加
- 2.3 导入配置文件(批量添加)

### 3.1 手动添加

首页选项说明

```markup
Remote Address: 服务器地址 
Remote Port: 服务器端口（默认为443） 
Password： 服务器密码 
Trojan URL: Trojan 链接 

Enable IPv6: 是否开启 IPv6 
Verify Certificate: 是否验证证书 
Bypass China with Clash: 是否代理中国大陆的网站
```

手动添加可以 `直接填写服务器信息(3.1.1)` 或是 `复制 Trojan URL(3.1.2)` ，两种方法选择一种即可

3.1.1 直接填写信息

![igniter-add-manually-01.jpg](https://i.loli.net/2020/03/26/BixDaIQEu4qVtos.jpg)

3.1.2 复制 Trojan Url

![igniter-add-manually-02.jpg](https://i.loli.net/2020/03/26/zm6wG4fO1npMPgi.jpg)

添加完成点击 START 即可，初次连接时系统会确认 VPN 权限，请选择允许。

![igniter-permission-request.jpg](https://i.loli.net/2020/03/26/9TyrtN2DiLqpYlG.jpg)

### 3.2 扫码添加

使用其他设备打开需要添加的节点的二维码。

点击右上角设置 ![icon-more.png](https://i.loli.net/2020/03/26/LGS1kXb75BE4oqI.png) 按钮，选择 `Server List` 打开节点列表页面，然后点击二维码按钮进行扫码。

![igniter-add-by-qr.png](https://i.loli.net/2020/03/26/kJKQZeqhcTsVldr.png)

### 3.3 导入配置文件

首先将 Trojan 服务的 `gui-config.json` 配置文件下载到手机上。

点击右上角设置 ![icon-more.png](https://i.loli.net/2020/03/26/LGS1kXb75BE4oqI.png) 按钮，选择 `Server List` 打开节点列表页面，然后点击 `更多选项` 的按钮，选择 `Import from file`，选择刚才下载配置文件即可。

![igniter-add-by-file.png](https://i.loli.net/2020/03/26/mXTvt6Ypb8kAfnO.png)

### 4. 更换节点

点击右上角设置 ![icon-more.png](https://i.loli.net/2020/03/26/LGS1kXb75BE4oqI.png) 按钮，选择 `Server List` 打开节点列表页面，点击需要切换的节点即可。



## 四、【IOS】Shadowrocket 设置方法

**如果类型没有 Trojan 或是扫码时出错，请更新您的 Shadowrocket (客户端图标样式** ![img](https://i.loli.net/2020/02/27/IFLfBpqGuS9Ohzk.png) **)****版本至 2.1.42 或以上版本。**

一、直接添加

打开 Shadowrocket 客户端，按照下面步骤添加服务器信息。

Shadowrocket 可以直接通过扫码的方式进行添加，或是按照下面的步骤手动添加。

1. 点击右上角 `+` 添加新的服务器。
2. 类型选择 **Trojan**
3. 填写对应的 **服务器、端口、与密码** 后保存即可，其他选项不需要设置。

二、扫码添加

打开服务详情页面，点击每个服务器右侧的二维码图标![img](https://i.loli.net/2020/02/28/UcnN8TxykG3rlhD.png)，然后点击“二维码”即可展示二维码。

打开 Shadowrocket 应用，点击左上角的扫描二维码图标，扫描屏幕上的二维码即可添加。

选择对应的服务器点击连接，同意 VPN 权限后即连接到互联网。





## 节点

<img src="https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/1.png" style="zoom:50%;" />

<center>JP1</center>
<img src="https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/2.png" style="zoom:50%;" />

<center>JP2</center>
<img src="https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/3.png" style="zoom:50%;" />

<center>JP3</center>
<img src="https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/4.png" style="zoom:50%;" />

<center>JP4</center>
<img src="https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/5.png" style="zoom:50%;" />

<center>JP5</center>
<img src="https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/6.png" style="zoom:50%;" />

<center>JP6</center>
<img src="https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/7.png" style="zoom:50%;" />

<center>US1</center>
<img src="https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/8.png" style="zoom:50%;" />

<center>US2</center>
<img src="https://puff-blog.oss-cn-shenzhen.aliyuncs.com/个人博客/9.png" style="zoom:50%;" />

<center>US3</center>