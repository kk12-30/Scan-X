# Scan-X 最新版本V7.1

QQ:2649566514

Scan-X是一款AI赋能渗透测试的框架平台。


```
重要更新记录：

V7.1：工具智能调用、工作流设置、日志分析、智能爬虫

V6.0：流量审计、Burpsuit插件、JSSS接口自动化测试、漏洞测试

V5.6：适配本地ollma模型（需要在配置文件中增加延时时间，具体配置参考使用手册最后部分）

V5.5：优化提示词、web界面（新增任务进度、AI对话助手、数据包扫描）

V5.2：Kali-MCP自动化渗透
```

### 扫描模块详细功能

####  AI智能扫描模块

| 模块名称           | 检测类型   | AI能力                                        | 状态 |
| ------------------ | ---------- | --------------------------------------------- | ---- |
| SQL_AIagent        | SQL注入    | 智能payload生成、时间盲注、布尔盲注、报错注入 | ✅    |
| XSS_AIagent        | 跨站脚本   | 反射型XSS、存储型XSS、DOM型XSS                | ✅    |
| RCE_AIagent        | 命令注入   | 命令执行、代码执行、OGNL注入                  | ✅    |
| Privilege_AIagent  | 越权检测   | 水平越权、垂直越权                            | ✅    |
| Upload_AIagent     | 文件上传   | 文件上传漏洞、文件读取、目录遍历              | ✅    |
| WAF_Bypass_AIagent | WAF绕过    | 智能绕过WAF防护                               | ✅    |
| CVE_AIagent        | CVE漏洞    | 已知CVE漏洞检测                               | ✅    |
| Bypass403_AIagent  | 403绕过    | 403状态码绕过                                 | ✅    |
| Fuzz_AIagent       | 模糊测试   | AI辅助模糊测试                                | ✅    |
| JSSS_AIagent       | JS智能扫描 | JavaScript代码分析、API测试                   | ✅    |
| JSSSVUL_AIagent    | JS漏洞测试 | JavaScript上下文漏洞检测                      | ✅    |
| DIY_AIagent        | 自定义检测 | 用户自定义检测规则                            | ✅    |

####  传统扫描模块

| 模块名称     | 功能说明                    | 特点                  |
| ------------ | --------------------------- | --------------------- |
| SQL基础注入  | 基于规则的SQL注入检测       | 快速、误报率低        |
| 敏感信息检测 | 检测API密钥、密码等敏感数据 | 正则匹配、自定义规则  |
| 指纹识别     | Web应用指纹识别             | 基于finger.json指纹库 |
| 越权检测     | 水平/垂直越权               | 基于角色令牌检测      |


![image](https://github.com/kk12-30/Scan-X/blob/main/4eb619d59dbb642e700047b19378fd45.png)
![image](https://github.com/kk12-30/Scan-X/blob/main/819b63b5-bee6-4cea-857f-2f747b076f88.png)
![image](https://github.com/kk12-30/Scan-X/blob/main/faf1b150-b12c-4878-b43e-816f104258ef.png)
![image](https://github.com/kk12-30/Scan-X/blob/main/9d86d2f8-04b9-40ba-998c-626792657173.png)
![image](https://github.com/kk12-30/Scan-X/blob/main/31536752-7ee4-475c-b9e3-0a2275189507.png)
![image](https://github.com/kk12-30/Scan-X/blob/main/66a9748b-6c01-4558-86b2-5d21ab3d684f.png)
![image](https://github.com/kk12-30/Scan-X/blob/main/e4d246c3-2d4f-4539-a0fd-082cc2ced4bb.png)
![image](https://github.com/kk12-30/Scan-X/blob/main/9b73edcf-3e88-4fa4-81e1-061457b6d4af.png)
![image](https://github.com/kk12-30/Scan-X/blob/main/a37f9fb6-9131-4ade-b59a-29b9512798ff.png)
![image](https://github.com/kk12-30/Scan-X/blob/main/1755487681409.jpg)

