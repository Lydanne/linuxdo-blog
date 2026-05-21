通过任意Android设备申请Giffgaff ESIM Simon (Yu Ma) 收录于 类别 杂技浅尝
2025-08-05 00:00 2025-10-12 10:00 约 2770 字 预计阅读 13 分钟 6343 次阅读 44
条评论 背景
Giffgaff是英国的一家虚拟运营商，其Giffgaff卡适合长期保号使用。Giffgaff原先只提供实体SIM卡，随后开始支持将实体SIM卡转换为esim或者直接购买新的esim。Giffgaff并不提供ESIM的二维码，而是通过Giffgaff
APP直接将ESIM配置文件下载到手机中。Giffgaff在申请或更换ESIM时都会检测当前手机是否能够支持ESIM功能，由于国内设备或早期发行的设备不支持ESIM功能，客户端将无法进行申请。本文介绍如何使用任意Android设备，配合HookEuicc伪装支持eSIM功能，并获取eSIM激活码
失效提醒 再开始前，我要提醒大家。
这个方法当前只适用于新卡申请，和老的SIM/ESIM还可用(能接码)的情况下的换卡操作。
Giffgaff近期更新了MFA策略，下面简述一下：
换卡操作：要求所有的换卡操作必须要老卡接收短信验证码，不能使用邮箱。
如果你是esim那必须要esim接收，如果是实体卡，那么要实体卡接收
挂失补卡操作：要求换卡只能换一张物理白卡，挂失补卡不支持直接变成esim卡 简言之：
新申请可以用： 用此方法 换卡如果老的ESIM/SIM还能用： 此方法也可以
换卡如果老的ESIM/SIM不能用：
先弄一张没激活过的giffgaff白卡，然后挂失绑定到白卡。 再用此方法
如果小伙伴们发现了新办法，记得tg联系我，我随时为大家更新 操作步骤 1.
安装和测试必要的软件 1.1 安装HookEuicc
下载地址：https://github.com/Unicorn369/HookEuicc/releases 1.2 安装LSPatch
版本提醒 注意！这里要使用开发者最新的版本，老版本会有异常。
Issue地址：https://github.com/JingMatrix/LSPatch/issues/29
下载地址：https://github.com/user-attachments/files/19442105/manager-v0.7-434-release.apk.zip
1.4 安装eUICC Probe
下载地址：https://github.com/CursedHardware/euicc-probe/releases 1.5 测试框架
直接打开eUICC Probe, 以 HUAWEI Mate 30为例, 注意
android.hardware.telephony.euicc 这一项是未被选中的。 打开LSPatch,
点击最下面的管理 选择模块Tab，应该可以看到HookEuicc 选择应用Tab,
点击+号，选择已安装的应用程序， 选择eUICC Probe 默认选择本地模式，
点击开始修补即可， 如果首次使用，会让你选择一个文件夹，随便选一个即可。
修补后，点击安装按钮，提示卸载原来未注入的应用，同意即可。
卸载成功，再次点击安装，重新安装注入后的应用。 安装完成后，回到LSPatch -
应用Tab，长按列表中的eUICC Probe，选择模块作用域 勾选HookEuicc，
注意要点击右下角的保存按钮， 是一个对钩的形状。 退出之前开启的eUICC
Probe软件，重新打开eUICC Probe， 如果失败请多次重试。 注意
android.hardware.telephony.euicc 这一项是应该是被选中了。 操作提醒
如果这里没有被选中，请检查前面的操作是否正确。这一步如果失败，后续步骤不用尝试。
1.6 安装Giffgaff官方APP Google Play下载入口：
https://play.google.com/store/apps/details?id=com.giffgaffmobile.controller
ApkPure下载入口： https://apkpure.com/cn/giffgaff/com.giffgaffmobile.controller
1.7 注入Giffgaff官方APP 这一步和上面的步骤非常相似，就是把eUICC
Probe换成giffgaff，具体步骤我直接Copy。 打开LSPatch, 点击最下面的管理
选择模块Tab，应该可以看到HookEuicc 选择应用Tab, 点击+号，选择已安装的应用程序，
选择giffgaff 默认选择本地模式， 点击开始修补即可，
如果首次使用，会让你选择一个文件夹，随便选一个即可。
修补后，点击安装按钮，提示卸载原来未注入的应用，同意即可。
卸载成功，再次点击安装，重新安装注入后的应用。 安装完成后，回到LSPatch -
应用Tab，长按列表中的giffgaff，选择模块作用域 勾选HookEuicc，
注意要点击右下角的保存按钮， 是一个对钩的形状。
退出之前开启的giffgaff软件，重新打开giffgaff， 如果失败请多次重试。2.
完成注册登录 这里大家自由完成，无非是些邮箱、验证码的操作。 1. 新户激活账号
如果你成功注入了官方App，那么你可以在首页看到SIM
card和eSIM两个Tab。如果没有看到，两个Tab，说明你没有注入成功，不要进行后续操作。
选择eSIM这个Tab， 点击Choose your plan 滑动到最下方选择I don't want a plan
后续为充值流程，与之前文章流程类似，在此我不再重复讲解 如果有疑问参考之前的文章
文章地址：https://simonmy.com/posts/giffgaff-esim-apply-without-official-app.html 4. 新户获取eSIM卡激活码 不出意外，支付完成后，会提示你安装eSIM， 点击安装即可
如果没有提示，重新打开官方app，首页会提示你安装eSIM
因为是伪装支持eSIM，所以会弹出一个分享提示框 一定要复制好这个字符串
1$xxxx.ondemandconnectivity.com$xxxxxxxxxxx 5. 老户更换eSIM，获取eSIM激活码
找到最下方 Account - SIM 点击 Replace my SIM - Switch to a new esiM
同意各种协议、提示、条款… 并继续 这里需要输入之前SIM/ESIM上收到的验证码！！！
不出意外，会提示你安装eSIM，点击安装即可
如果没有提示，重新打开官方app，首页会提示你安装eSIM
因为是伪装支持eSIM，所以会弹出一个分享提示框 一定要复制好这个字符串
1$xxxx.ondemandconnectivity.com$xxxxxxxxxxx 深入探索 SIM卡 SIM 手机 6. 安装eSIM
在刚才复制的字符串前加上LPA:,
例如：LPA:1$xxxx.ondemandconnectivity.com$xxxxxxxxxxx
如果是iPhone导入eSTK，使用拼好的激活码即可
如果是Android，打开https://qrcode.show/ ,
输入拼好的激活码，生成二维码图片，扫描即刻。 7. 其他
如果你在过程中遇到了问题，可以在下方留言或通过 https://t.me/Charpati 寻求帮助
寻求帮助前，请一定准备好下面材料和设备： 一个可用的安全邮箱 一个可支付的银行卡
一个支持ESIM的设备(可以是estk、5ber、9esim等) 当前遇到的问题 参考文章 安卓无
esim 手机获取 esim 激活码的简单方法 特别感谢 在此特别感谢网友 mars1636
在评论区提供的思路。 写在最后
我本不想写这段话，但是太多的人连最基本的转载尊重都没有。 Seven科技生活
说的就是你~ 要求：但凡使用本文章内容和方法的，请在内容中带上本文链接。 更新于
2025-10-12 10:00
注意最新版本的giffgaff不能使用这个方法了，即使用了hookeuicc还是会被检测出来，最后一个可用的版本是giffgaff
19.12.0
原文链接：https://simonmy.com/posts/giffgaff-esim-apply-use-hookeuicc.html
