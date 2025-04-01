# Scan-X
Scan-X是一款基于mitmproxy高效的被动扫描器，专注于快速识别常见Web漏洞，包括SQL注入、越权访问、未授权访问等。通过代理模式自动分析HTTP流量，实现被动扫描，适合大规模资产安全评估与渗透测试场景。

https://mp.weixin.qq.com/s/L7WRhOp7hlgA6a3pPZLGhA


使用场景如下：

1、浏览器直接开启7777端口代理进行检测（不推荐）
![image](https://github.com/kk12-30/Scan-X/blob/main/4.png)
2、使用burpsuit下游代理或passive-scan-client插件进行检测（不会影响正常请求，推荐）
![image](https://github.com/kk12-30/Scan-X/blob/main/5.png)


一：证书安装
根据步骤双击安装即可、浏览器也需要导入该证书
![image](https://github.com/kk12-30/Scan-X/blob/main/1.png)

导入到受信任的根证书颁发机构即可
![image](https://github.com/kk12-30/Scan-X/blob/main/2.png)

二：配置文件说明
![image](https://github.com/kk12-30/Scan-X/blob/main/3.png)


