[English](https://github.com/Ke1992/Fiddler-FPlug/blob/master/README.md) | 简体中文
# FPlug
FPlug是一个Fiddler插件，提供Web开发中用到的一系列工具 ([Fiddler插件开发指南](https://github.com/Ke1992/Fiddler-Plug-Example))
# 版本
v1.0.4
# 环境要求
Fiddler版本要求4.6以上，推荐5.0版本以上（FPlug是以Fiddler 5.0版本为基准），同时要求.NET Framework 4.6.1以上
# 下载安装
#### 1、Exe文件
下载dist文件夹中的[FPlug.exe](https://raw.githubusercontent.com/Ke1992/Fiddler-FPlug/master/dist/FPlug.exe)文件
#### 2、手动安装
下载dist文件夹中的dll文件，然后复制到Fiddler安装目录中的Scripts文件夹。
# 特性
* Host映射
* 文件映射
* Https 转 Http
* Header 替换
* ServerIP
* 禁止缓存
* vConsole
* Console日志
* JS注入
# 基础配置说明
### 启用/关闭插件
![启用/关闭插件](https://raw.githubusercontent.com/Ke1992/Fiddler-FPlug/master/guide/switch.gif "启用/关闭插件")
### 项目相关操作
![配置项目](https://raw.githubusercontent.com/Ke1992/Fiddler-FPlug/master/guide/item.gif "配置项目")
### 规则相关操作
![规则相关操作](https://raw.githubusercontent.com/Ke1992/Fiddler-FPlug/master/guide/rule.gif "规则相关操作")
# 特性功能说明
### Host映射
1、IP字段：填写映射机器的IP地址即可  
2、端口字段：非必填，填写则替换为指定端口号，为空则使用请求本身的端口号  
3、Url字段：  
　　(1)、不局限于域名，以映射https://www.example.com/test/index.html为例  
　　(2)、可以指定具体的Path，如：www.example.com/test  
　　(3)、可以是URL的任意部分，如：com/test/i  
　　(4)、支持正则表达式，如：\S*.example.com  
4、示例：
![Host映射](https://raw.githubusercontent.com/Ke1992/Fiddler-FPlug/master/guide/host.gif "Host映射")
### 文件映射
1、Url字段：  
　　(1)、不局限于域名，以映射https://www.example.com/test/index.html为例  
　　(2)、可以指定具体的Path，如：www.example.com/test  
　　(3)、可以是URL的任意部分，如：com/test/i  
　　(4)、支持正则表达式，如：\S*.example.com  
2、文件路径字段：  
　　(1)、仅支持正确的全路径（如果路径不正确将会有错误弹框！！！）  
　　(2)、如果映射的URL中带有callback字段，则会自动替换文件里面第一个callback字符串  
3、示例：
![文件映射](https://raw.githubusercontent.com/Ke1992/Fiddler-FPlug/master/guide/file.gif "文件映射")
### Https 转 Http
1、使用此配置必须开启Fiddler的HTTPS抓包功能  
2、Url字段：  
　　(1)、不局限于域名，以映射https://www.example.com/test/index.html为例  
　　(2)、可以指定具体的Path，如：www.example.com/test  
　　(3)、可以是URL的任意部分，如：com/test/i  
　　(4)、支持正则表达式，如：\S*.example.com  
3、示例：
![Https 转 Http](https://raw.githubusercontent.com/Ke1992/Fiddler-FPlug/master/guide/https.gif "Https 转 Http")
### Header替换
1、允许替换Request或者Response的头部字段   
2、Url字段：  
　　(1)、不局限于域名，以映射https://www.example.com/test/index.html为例  
　　(2)、可以指定具体的Path，如：www.example.com/test  
　　(3)、可以是URL的任意部分，如：com/test/i  
　　(4)、支持正则表达式，如：\S*.example.com  
3、Key字段：必须符合 User-Agent 的格式   
4、Request示例：
![Request Header](https://raw.githubusercontent.com/Ke1992/Fiddler-FPlug/master/guide/header_req.gif "Request Header")
5、Response示例：
![Response Header](https://raw.githubusercontent.com/Ke1992/Fiddler-FPlug/master/guide/header_res.gif "Response Header")
### ServerIP
1、开启后会自动在session面板中追加一列ServerIP，用来显示请求最终的IP地址  
2、示例：  
![ServerIP](https://raw.githubusercontent.com/Ke1992/Fiddler-FPlug/master/guide/serverip.gif "ServerIP")
### 禁止缓存
1、开启后会主动修改Request和Response头的相关字段，来禁止缓存  
　　(1)、Request头：  
　　　　a、删除Expires  
　　　　b、删除If-None-Match  
　　　　c、删除If-Modified-Since  
　　　　d、强制修改Pragma为no-cache  
　　　　e、强制修改Cache-Control为no-cache  
　　(2)、Response头：  
　　　　a、删除Expires  
　　　　b、强制修改Pragma为no-cache  
　　　　c、强制修改Cache-Control为no-cache  
### vConsole
1、开启后，会往Content-Type包含text/html，并且，包含&lt;html&gt;或者&lt;html 的请求中注入vConsole  
2、示例：  
![vConsole](https://raw.githubusercontent.com/Ke1992/Fiddler-FPlug/master/guide/vconsole.gif "vConsole")
### Console日志
1、开启后会增加日志面板，同时会主动往网页中注入JS脚本，修改console方法，捕获日志后发起POST请求  
2、日志输出的顺序请以序号为准  
3、开启后之前已经打开的页面需要刷新才能捕获日志  
4、仅会往Content-Type包含text/html，并且，包含&lt;html&gt;或者&lt;html 的请求中注入脚本  
5、示例：  
![Console日志](https://raw.githubusercontent.com/Ke1992/Fiddler-FPlug/master/guide/console.gif "Console日志")
### JS注入
1、开启后，在输入框中键入JavaScript脚本，然后点击发送，会主动向代理中的网页注入对应的脚本  
2、开启后之前已经打开的页面需要刷新才能响应注入的脚本  
3、仅对Content-Type包含text/html，并且，包含&lt;html&gt;或者&lt;html 的请求有效  
4、会每隔2S请求一次www.example.com，请忽略！！！  
5、示例：  
![JS注入](https://raw.githubusercontent.com/Ke1992/Fiddler-FPlug/master/guide/invade.gif "JS注入")
