# Scan-X
Scan-X是一款基于mitmproxy高效的被动扫描器，专注于快速识别常见Web漏洞，包括SQL注入、越权访问、未授权访问等。通过代理模式自动分析HTTP流量，实现被动扫描，适合大规模资产安全评估与渗透测试场景。
![image](https://github.com/kk12-30/Scan-X/blob/main/web.png)



使用：https://mp.weixin.qq.com/s/WJp3yk46dSQ_aMMMj2AP0A

更新记录：

v3.0（beta）：新增Web操作页面

v2.4：新增多个针对特定漏洞的AI-Agent扫描模块(SQL、xss、fuzz、越权、自定义模块)、新增响应体长度限制防止消耗过多token

v2.3：优化web界面、支持并发多任务进行AI漏洞扫描  scan-x.exe -uf url.txt

v2.2：新增web界面、新增数据库报错检测

v2.0：新增指纹识别、基于指纹的AI漏洞扫描

v1.9：修复AI生成的请求包和响应包格式问题（之前的版本会导致400错误）、优化提示词

v1.8：跳过TLS证书验证、优化提示词

v1.7：AI漏洞扫描功能，防止API接口超时，新增在配置中自定义超时时间

v1.6：新增AI二次扫描

v1.5：若干bug修复

v1.4：优化AI提示词、修复AI配置信息

v1.3：新增AI扫描测试

v1.2：新增fuzz测试

v1.1：支持请求三次转发，可联动xscan等工具


## 🚀 使用场景如下

1、浏览器直接开启7777端口代理进行检测（不推荐）
![image](https://github.com/kk12-30/Scan-X/blob/main/4.png)
2、使用burpsuit下游代理或passive-scan-client插件进行检测（不会影响正常请求，推荐）
![image](https://github.com/kk12-30/Scan-X/blob/main/5.png)


## 🚀 使用说明

一：证书安装

根据步骤双击安装即可、浏览器也需要导入该证书
![image](https://github.com/kk12-30/Scan-X/blob/main/1.png)

导入到受信任的根证书颁发机构即可
![image](https://github.com/kk12-30/Scan-X/blob/main/2.png)

二：配置文件说明
![image](https://github.com/kk12-30/Scan-X/blob/main/3.png)
![image](https://github.com/kk12-30/Scan-X/blob/main/6.png)
![image](https://github.com/kk12-30/Scan-X/blob/main/7.png)

三：漏洞检测

![image](https://github.com/kk12-30/Scan-X/blob/main/12.png)
![image](https://github.com/kk12-30/Scan-X/blob/main/10.png)
![image](https://github.com/kk12-30/Scan-X/blob/main/11.png)
![image](https://github.com/kk12-30/Scan-X/blob/main/8.png)
![image](https://github.com/kk12-30/Scan-X/blob/main/9.png)

四：AI扫描自动化测试
可以修改配置文件中的AI模型，通过AI自动构造请求包，受限于API的速度一次只构造5个请求包
使用burpsuit下游代理或passive-scan-client插件进行检测（不会影响正常请求）
![image](https://github.com/kk12-30/Scan-X/blob/main/ai1.png)
![image](https://github.com/kk12-30/Scan-X/blob/main/ai2.png)
![image](https://github.com/kk12-30/Scan-X/blob/main/ai3.png)


