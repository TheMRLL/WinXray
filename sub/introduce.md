# winXray 小技巧

### 一、批量导入链接技巧

winXray  最新版支持直接使用 github 网址作为订阅链接。例如，我们在浏览器里访问 github项目文件的地址是这样的： [https://github.com/winXray/winXray/blob/master/sub/sample.json](./sample.json) 我们直接复制前面的链接，然后在 winXray 中点击 **「批量导入链接」** 就可以导入里面的服务器配置了。

winXray可以兼容以下格式的github文件地址( 支持省略域或并以斜杆开头的地址 ）：  
https://github.com/winXray/winXray/blob/master/sub/sample.json  
[/winXray/blob/master/sub/sample.json](./sample.json)  
https://github.com/winXray/winXray/raw/master/sub/sample.json  
[/winXray/winXray/raw/master/sub/sample.json](./sample.json)  
https://raw.githubusercontent.com/winXray/winXray/master/sub/sample.json  

即使在国内打不开 githubusercontent.com，winXray 仍然可以机智地调用 github 的API 顺利地把目标文件下载下来。 

winXray 的订阅链接可以返回所有 winXray 能兼容的服务器配置，例如：  
1、直接返回一行或多行分享链接，支持vmess,vless,ss,trojan,trojan-go 这一堆的各种通用分享格式，每行一个有效链接，无效的行 winXray 会自动忽略。  
2、可以每行一个服务器配置JSON，也可以把多个服务器配置JSON放到一个数组里（就是放到方括号里），winXray都能兼容，JSON推荐使用 winXray 的语法 - winXray已经把各种不同的代理协议配置规范化为了几个简单且通用的字段。当然你可以返回一些 winXray 可以兼容的通用JSON，winXray 会最大可能的识别并转换各种JSON格式，例如服务器的字段名你可以写为add,address,server 等等不同的名字。  
服务器可以返回base64编码的配置，也可以直接返回服务器配置，winXray都能识别。 winXray可以导入v2ray,、Shadowsocks、trojan等通用订阅链接，也可以导入 Clash proxy-provider 配置，winXray将自动转化各种不兼容的配置为统一、规范的格式。

我们平时复制配置和链接导入 winXray 一样，winXray都会最大可能的识别并兼容各种格式，并且尝试自动清除复制文本中的无效内容。例如使用 winXray 自带的 v2ray agent 安装服务端以后，我们不需要在给出的配置中挑选出JSON慢慢的修改和设置，你只需要把安装程序返回的一大堆账号配置文本直接复制出来（包含各种无效的、无关的说明文字）， winXray 会自动分析识别并导入有效的服务器配置。

有些人崇尚复杂，但是winXray 的目标就是让一切变得更简单，软件能自动做的事就自动做好，**人生苦短，哪有那么多时间折腾？！**

###  二、使用JSON配置服务器技巧
![服务器配置](./../screenshots/config.json.png)
JSON配置界面里点击任意字段都会显示该字段的用法说明。个人认为做很多对话框来配置服务器的参数是非常蠢的，winXray已经把各种代理协议的配置简化为几个统一命名的JSON字段（ **也可以作为一种标准的、统一的、通用的订阅响应格式使用** ），只要稍加学习就可以非常熟练的添加、修改各种代理协议的配置。而且对于大多数用户根本不需要改配置 - 简单的复制导入分享链接就可以，我们不必要把简单的事搞复杂。

###  三、Telegram 代理设置
因为Telegram 使用的IP非常多，PAC代理确实不好支持Telegram ，但是使用IP路由去适配Telegram其实是不必要的，试想一下一个IP路由的数据就几十MB - 有这个必要吗？！我们为什么不直接告诉 Telegram 他要使用的代理服务器地址，而是 他在每个IP请求的时候都去判断一下呢？。

所以更简洁、更聪明的方法就是直接告诉 Telegram 他要使用的代理服务器地址，这个操作非常简单 - 绝对比下载 Telegram 更简单，请看下面的动画：

![Telegram 代理设置](./../screenshots/telegram.gif)



