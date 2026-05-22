# 通过任意 Android 设备申请 Giffgaff eSIM

Simon (Yu Ma) 收录于「杂技浅尝」  
发表于：2025-08-05 00:00  
更新于：2025-10-12 10:00  
约 2770 字，预计阅读 13 分钟，6343 次阅读，44 条评论

## 背景

Giffgaff 是英国的一家虚拟运营商，其 Giffgaff 卡适合长期保号使用。Giffgaff 原先只提供实体 SIM 卡，随后开始支持将实体 SIM 卡转换为 eSIM，或者直接购买新的 eSIM。

App 会直接将 eSIM 配置文件下载到手机中。Giffgaff 在申请或更换 eSIM 时都会检测当前手机是否支持 eSIM 功能。由于国内设备或早期发行的设备通常不支持 eSIM 功能，因此会导致这类设备无法直接申请或安装 eSIM。

## 失效提醒

在开始前，我要提醒大家：

这个方法当前只适用于：

- 新卡申请
- 老的 SIM / eSIM 仍然可用（能接码）时的换卡操作

Giffgaff 近期更新了 MFA 策略，下面简述一下：

### 换卡操作

现在要求所有换卡操作都必须由老卡接收���信验证码，不能使用邮箱。

- 如果你原来是 eSIM，那么必须由原 eSIM 接收验证码
- 如果你原来是实体卡，那么必须由原实体卡接收验证码

### 挂失补卡操作

现在挂失补卡只能换成一张物理白卡，挂失补卡不支持直接变成 eSIM 卡。

### 简言之

- **新申请可以用**：用此方法
- **换卡且老的 eSIM / SIM 还能用**：此方法也可以
- **换卡但老的 eSIM / SIM 不能用**：
  1. 先弄一张没激活过的 giffgaff 白卡
  2. 挂失并绑定到白卡
  3. 再用此方法

如果小伙伴们发现了新办法，记得 tg 联系我，我随时为大家更新。

## 操作步骤

## 1. 安装和测试必要的软件

### 1.1 安装 HookEuicc

下载地址：  
https://github.com/Unicorn369/HookEuicc/releases

### 1.2 安装 LSPatch

> 注意！这里要使用开发者最新的版本，老版本会有异常。

Issue 地址：  
https://github.com/JingMatrix/LSPatch/issues/29

下载地址：  
https://github.com/user-attachments/files/19442105/manager-v0.7-434-release.apk.zip

### 1.3 安装 eUICC Probe

下载地址：  
https://github.com/CursedHardware/euicc-probe/releases

### 1.4 测试框架

直接打开 eUICC Probe。以 HUAWEI Mate 30 为例，注意：

- `android.hardware.telephony.euicc` 这一项最初应是**未被选中**的

然后打开 LSPatch，按下面步骤操作：

1. 点击最下面的“管理”
2. 选择“模块”Tab，确认可以看到 HookEuicc
3. 选择“应用”Tab
4. 点击“+”号，选择已安装的应用程序
5. 选择 **eUICC Probe**
6. 默认选择“本地模式”
7. 点击“开始修补”

如果首次使用，会让你选择一个文件夹，随便选一个即可。

修补后：

1. 点击“安装”按钮
2. 提示卸载原来未注入的应用时，选择同意
3. 卸载成功后，再次点击安装
4. 重新安装注入后的应用

安装完成后：

1. 回到 LSPatch → “应用”Tab
2. 长按列表中的 **eUICC Probe**
3. 选择“模块作用域”
4. 勾选 **HookEuicc**
5. 点击右下角保存按钮（对钩形状）

然后：

1. 退出之前开启的 eUICC Probe
2. 重新打开 eUICC Probe
3. 如果失败请多次重试

此时注意：

- `android.hardware.telephony.euicc` 这一项应该已经被选中

> 如果这里没有被选中，请检查前面的操作是否正确。这一步如果失败，后续步骤不用尝试。

### 1.5 安装 Giffgaff 官方 App

Google Play 下载入口：  
https://play.google.com/store/apps/details?id=com.giffgaffmobile.controller

ApkPure 下载入口：  
https://apkpure.com/cn/giffgaff/com.giffgaffmobile.controller

### 1.6 注入 Giffgaff 官方 App

这一步和上面的步骤非常相似，只是把 eUICC Probe 换成 giffgaff。具体步骤如下：

1. 打开 LSPatch
2. 点击最下面的“管理”
3. 选择“模块”Tab，确认可以看到 HookEuicc
4. 选择“应用”Tab
5. 点击“+”号，选择已安装的应用程序
6. 选择 **giffgaff**
7. 默认选择“本地模式”
8. 点击“开始修补”

如果首次使用，会让你选择一个文件夹，随便选一个即可。

修补后：

1. 点击“安装”按钮
2. 提示卸载原来未注入的应用时，选择同意
3. 卸载成功后，再次点击安装
4. 重新安装注入后的应用

安装完成后：

1. 回到 LSPatch → “应用”Tab
2. 长按列表中的 **giffgaff**
3. 选择“模块作用域”
4. 勾选 **HookEuicc**
5. 点击右下角保存按钮（对钩形状）

然后：

1. 退出之前开启的 giffgaff 软件
2. 重新打开 giffgaff
3. 如果失败请多次重试

## 2. 完成注册登录

这里大家自由完成，无非是一些邮箱、验证码的操作。

## 3. 新户激活账号

如果你成功注入了官方 App，那么你可以在首页看到 **SIM card** 和 **eSIM** 两个 Tab。

如果没有看到这两个 Tab，说明你没有注入成功，不要进行后续操作。

操作流程：

1. 选择 **eSIM** 这个 Tab
2. 点击 **Choose your plan**
3. 滑动到最下方选择 **I don't want a plan**

后续为充值流程，与之前文章流程类似，在此不再重复讲解。

如果有疑问，可以参考之前的文章：  
https://simonmy.com/posts/giffgaff-esim-apply-without-official-app.html

## 4. 新户获取 eSIM 卡激活码

不出意外，支付完成后会提示你安装 eSIM，点击安装即可。

如果没有提示：

- 重新打开官方 App
- 首页通常会再次提示你安装 eSIM

因为是伪装支持 eSIM，所以会弹出一个分享提示框。

**一定要复制好这个字符串：**

```text
1$xxxx.ondemandconnectivity.com$xxxxxxxxxxx
```

## 5. 老户更换 eSIM，获取 eSIM 激活码

操作路径：

**Account → SIM → Replace my SIM → Switch to a new eSIM**

然后：

1. 同意各种协议、提示、条款
2. 输入之前 SIM / eSIM 上收到的验证码

> 这里需要输入之前 SIM / eSIM 上收到的验证码！！！

不出意外，会提示你安装 eSIM，点击安装即可。

如果没有提示：

- 重新打开官方 App
- 首页通常会再次提示你安装 eSIM

因为是伪装支持 eSIM，所以会弹出一个分享提示框。

**一定要复制好这个字符串：**

```text
1$xxxx.ondemandconnectivity.com$xxxxxxxxxxx
```

## 6. 安装 eSIM

在刚才复制的字符串前加上 `LPA:`，例如：

```text
LPA:1$xxxx.ondemandconnectivity.com$xxxxxxxxxxx
```

### iPhone 导入 eSTK

如果是 iPhone 导入 eSTK，直接使用拼好的激活码即可。

### Android 安装方式

如果是 Android，打开下面的网址生成二维码图片后扫码即可：

https://qrcode.show/

输入拼好的激活码，生成二维码图片，扫描即可。

## 7. 其他

如果你在过程中遇到了问题，可以在下方留言或通过以下方式寻求帮助：

https://t.me/Charpati

在寻求帮助前，请一定准备好下面材料和设备：

- 一个可用的安全邮箱
- 一个可支付的银行卡
- 一个支持 eSIM 的设备（可以是 estk、5ber、9esim 等）
- 当前遇到的问题描述

## 参考文章

- 安卓无 eSIM 手机获取 eSIM 激活码的简单方法

## 特别感谢

在此特别感谢网友 **mars1636** 在评论区提供的思路。

## 写在最后

我本不想写这段话，但是太多的人连最基本的转载尊重都没有。Seven 科技生活，说的就是你~

**要求：但凡使用本文章内容和方法的，请在内容中带上本文链接。**

## 更新说明

更新于 **2025-10-12 10:00**

注意：最新版本的 giffgaff 已经不能使用这个方法了。即使用了 HookEuicc 还是会被检测出来。

**最后一个可用版本是：giffgaff 19.12.0**

原文链接：  
https://simonmy.com/posts/giffgaff-esim-apply-use-hookeuicc.html
