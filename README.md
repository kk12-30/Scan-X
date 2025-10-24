# Scan-X 最新版本V5.6

最新介绍文章：https://mp.weixin.qq.com/s/zqTliLgVBimelAUQ26RgIw

演示视频： https://www.bilibili.com/video/BV18meizdEZ3

推荐模型：https://github.com/Clouditera/SecGPT

![image](https://github.com/kk12-30/Scan-X/blob/main/1755487681409.jpg)


Scan-X是一款基于mitmproxy高效的被动扫描器，专注于快速识别常见Web漏洞，包括SQL注入、越权访问、未授权访问等。通过代理模式自动分析HTTP流量，实现被动扫描，适合大规模资产安全评估与渗透测试场景。
![image](https://github.com/kk12-30/Scan-X/blob/main/22.png)
![image](https://github.com/kk12-30/Scan-X/blob/main/web.png)

![image](https://github.com/kk12-30/Scan-X/blob/main/12.png)
![image](https://github.com/kk12-30/Scan-X/blob/main/23.png)



使用：

```
接口API支持工具二开，modules类型有：xss_AIagent, sql_AIagent, rce_AIagent, cve_AIagent, upload_AIagent, fuzz_Aiagent, diy_AIagent, bypass403_AIagent, privilege_AIagent, waf_bypass_AIagent, bypass, horizontal_escalation, vertical_escalation, ai_scan, finger_scan, sensitive_info, unauthorized, fuzz, sql_baseinjection, sql_injection, model_select

curl -X POST http://localhost:8080/api/scan \
  -H "Content-Type: application/json" \
  -d '{
    "url": "http://example.com/login.php",
    "method": "POST",
    "body": "username=admin&password=123456",
    "headers": {
      "Content-Type": "application/x-www-form-urlencoded",
      "User-Agent": "Custom-Scanner/1.0"
    },
    "modules": {
      "sql_AIagent": true,
      "xss_AIagent": true,
      "sensitive_info": true,
      "unauthorized": true
    }
  }'
```




```
更新记录：

V6.0（beta）：自动化任务编排、MCP管理、Web界面集成、远程下发指令

V5.6：适配本地ollma模型（需要在配置文件中增加延时时间，具体配置参考使用手册最后部分）

V5.5：优化提示词、web界面（新增任务进度、AI对话助手、数据包扫描）

V5.2：Kali-MCP自动化渗透
```

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


