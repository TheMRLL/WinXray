

# winXray V 2.5.1(修复了点击更新内核报错的问题！)      winxray.com 
导语：
     请用官网地址下载：https://winxray.com/%E4%B8%8B%E8%BD%BD%E4%B8%AD%E5%BF%83
     由于软件的特殊性，winxray没有任何群。不要相信任何winxray群里的消息，以免受骗！winxray已经和原作者走的是两个不同的内核（原作者走的是V2RAY核心，我走的Xray核心）请原作者不要恶意诽谤。我编写软件报错很正常，因为我之前没有接触过AARDIO，而我也一直在维护BUG（现在已经运行到稳定V2.5.1版本了）！如果你介意我使用你的开源程序，我将考虑更换编码程序不再使用AAROIO！？我原本是考虑到尊重源码尊重你的UI保留你的风格界面不破坏你的一切东西；至于为什么要加按钮也只是出于不想搞乱你的代码，当然我还想醒目的推广我的网站（0收益）！（首先我拥有网站，之前我也给你留言过，我将无偿提供网站和服务器给你）为什么没有让讨论区讨论原作者，那是因为有些人不停在攻击我。现在做到这个地步，我想说的是这个程序是我自己在维护，在更新，包括谷歌广告，脸书广告推广！我的网站能一天有1000的访问量都是我自己积累的。你如果自己不尊重自己，我也没办法了。
     
![测速图片](./screenshots/QQ图片20210129164350.png)

   WinXray是一个简洁稳定的 [Xray/V2Ray(vmess/vless/xtls)、Shadowsocks、Trojan、Trojan-go](https://github.com/XTLS/Xray-core)、SSR、NaïveProxy、 等等 通用客户端（Windows系统），可自动检测并连接访问速度最快的代理服务器。服务器连接异常时可以自动更换代理服务器 - 再也不用担心服务器抽风了。winXray 也提供一键安装 XRay(V2Ray、Shadowsocks、Trojan) 服务器工具。

  
之前我用过很多代理客户端，经常用一会就挂掉了，有些测试很久才找到下一个可用的服务器，有时怎么切换都不行，一定要把整个软件退出重启才能恢复。而且在WIN10上都有相同的BUG:PAC代理用一段时间就会卡死( winXray已经通过自行实现PAC服务器解决了这个问题 )，其实这些软件里提供的很多功能我并不需要，我只想愉快地用下 google 找点技术资料提升工作效率。但是在网上找了很久都没找到适合的软件，于是决定自己动手写一个，还好用 aardio 写软件的速度很快 - 大概用了几个小时就完成了 winXray 的主要代码，改进了几个版本以后就很稳定了，**我自己用了 winXray  几个月再也没有遇到 google 抽风访问不了的问题**。    

一些网友对 winXray 的测速功能存在误解，简单的测速不但不必要的消耗流量而且没有什么实用价值，例如Ping通了TCP访问不了，TCP通了但浏览器被阻断，或者下载测速需要连接代理服务器以后长时间测试才能得到下载速度 - 如果有很多服务器需要频繁快速地测速这样显然是不行的。**根据我长时间的实测，我使用一堆的服务器，大多时候 winXray 都能最快的找到其中速度最快、且能正常使用的线路**。要考虑到网络速度与服务器响应速度本来就是波动的，**winXray 能在连接代理服务器以前在零点几秒以内快速地在上百个代理服务器中找出最快的服务器** - 可以节省我们大量手动测试切换的时间，如果你有一个比我们幸福的网络环境，有一堆稳定流畅看4K视频的代理服务器 - 那你确实可以关闭自动切换功能 - 手动切换即可。

![winXray](./screenshots/winXray.png)

winXray支持批量导入 vless、vmess、ss、trojan、trojan-go …… 等格式的分享链接，  
也可以导入v2ray,、Shadowsocks、trojan等通用订阅链接，兼容 base 64、json …… 等不同格式的服务器配置，也可以导入 Clash proxy-provider 配置，winXray将自动转化各种不兼容的配置为统一、规范的格式。winXray 有强大的兼容性，我们甚至可以直接自 github 项目地址导入代理服务器，例如直接复制链接 [https://github.com/winXray/winXray/blob/master/sub/sample.json](./sub/sample.json) 即可一键导入 winXray。

![服务器配置](./screenshots/config.json.png)
**小技巧: JSON里点击任意字段都会显示该字段的用法说明。** 个人认为做很多对话框来配置服务器的参数是非常蠢的，winXray已经把各种代理协议的配置简化为几个统一命名的JSON字段（ **也可以作为一种标准的、统一的、通用的订阅响应格式使用** ），只要稍加学习就可以非常熟练的添加、修改各种代理协议的配置。而且对于大多数用户根本不需要改配置 - 简单的复制导入分享链接就可以，我们不必要把简单的事搞复杂。

可选在 ["/xray-core/winXray-default-servers.json"](./xray-core/winXray-default-servers.json) 文件中添加默认服务器配置（生成EXE后默认配置自动嵌入到EXE文件，可选删除该文件,也可以继续使用该文件覆盖EXE自带的默认服务器列表）。

![PAC配置](./screenshots/pac.png)
**小技巧: PAC编辑器里点击任意域名都会自动关联到单选框，可以直接切换代理或直连。**

软件首次运行时会在当前目录查找 "./xray-core/xray.exe"   
发行文件仅需要 "./winXray.exe"，可选带上 "./xray-core/" 目录（ 如果没有找到会自动到v2ray官网下载，不过没有代理服务器下载有时候非常慢 )。

![端口配置](./screenshots/config.advanced.png)

<img src="./screenshots/telegram.gif" width="1031" alt="Telegram 端口配置">
