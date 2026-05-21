# 记一次成功申请海外电话卡（giffgaff）的坎坷

今天是 2026 年的 5 月 22 日深夜 2 点，经历了 3 天的等待终于收到了 PDD 购买的 sim白卡了，佬你知道我一夜是怎么过的吗，各种找攻略各种测试，终于找到一套可行的方案，并且实践成功，现在分享给大家。

我在5 月 18 号的时候想申请一张 giffgaff 的电话卡，当时跟着网上的教程申请了一种卡（我记得我应该是当时用苹果申请了，我直接申请的 esim，申请完成后付款后发现不支持 esim，又换成我的 redmi k90 promax，当时我手机上有一个 install，但是一直安装不上后来查了一圈 tm 的国内的手机大部分不支持 esim，我这台也不支持），后来发现我的手机都不支持 esim，只能买一个白卡了。

我测试使用 postman 去获取 esim token 的时候我是在登录时候失败了，没办法我找攻略，找到了新的方案使用安卓手机去拦截 giffgaff 客户端的 esim token，
后来我换了另一台手机 k60，去按教程走（因为要安装一些软件我担心不安全），这时又出现一个坑，要登录验证码但是我使用邮箱发验证一直收不到，而且跟着教程走也不顺利，不知道为啥我这个手机安装他那些软件总是缺东西，后来没办法只能使用我的 k90 了

因为之前登录过所以k90是不需要验证码的，后来我按照教程破解了 giffgaff app，安装之后走教程还是不通正常是会弹出 toast 的后来在评论区看到需要安装[旧版本的客户端](https://apkpure.com/cn/giffgaff/com.giffgaffmobile.controller/download/19.12.0)，后来我又卸载掉重新下载安装并且跟着教程破解，最终我终于拿到了，然后用 PDD 给的软件去将这个 token 写入了 sim 白卡，到这一步我终于成功了。

教程地址：为了防止被秦始皇佬大说我贴脸（贴别家的论坛）我就将内容复制下来放在我 github 了（[giffgaff-esim-apply-use-hookeuicc](https://github.com/lydanne/linuxdo-blog/tree/main/snapshot/giffgaff-esim-apply-use-hookeuicc.md)），需要的佬友可以来这里查看教程。

最后如何保号可以看：https://linux.do/t/topic/662646
