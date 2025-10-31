# Scan-X 最新版本V6.0

最新介绍文章：https://mp.weixin.qq.com/s/zqTliLgVBimelAUQ26RgIw

推荐模型：https://github.com/Clouditera/SecGPT

![image](https://github.com/kk12-30/Scan-X/blob/main/1755487681409.jpg)


Scan-X是一款基于mitmproxy高效的被动扫描器，专注于快速识别常见Web漏洞，包括SQL注入、越权访问、未授权访问等。通过代理模式自动分析HTTP流量，实现被动扫描，适合大规模资产安全评估与渗透测试场景。
![image](https://github.com/kk12-30/Scan-X/blob/main/22.png)




```
更新记录：

V6.0：流量审计、JSSS接口自动化测试

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


### 流量代理与分析流程

```mermaid
sequenceDiagram
    participant Client as 客户端(Burp)
    participant Proxy as 代理服务器(7777)
    participant Target as 目标服务器
    participant Storage as 流量存储
    participant WebUI as Web UI
    participant Browser as 浏览器用户
    participant AI as AI服务
    
    Note over Client,Target: 1. 流量捕获阶段
    Client->>Proxy: HTTP/HTTPS请求
    Proxy->>Proxy: 拦截请求
    Proxy->>Proxy: 应用黑白名单过滤
    
    alt 在黑名单中
        Proxy->>Client: 直接转发
    else 不在黑名单中
        Proxy->>Proxy: 解析请求头和请求体
        Proxy->>Proxy: 生成流量记录ID
        Proxy->>Storage: 保存请求信息
        
        Proxy->>Target: 转发请求
        Target-->>Proxy: 返回响应
        
        Proxy->>Proxy: 解析响应头和响应体
        Proxy->>Proxy: 处理压缩内容(gzip/br)
        Proxy->>Storage: 更新流量记录(添加响应)
        
        Proxy->>WebUI: WebSocket推送新流量
        Proxy->>Client: 返回响应
    end
    
    Note over Storage,Browser: 2. 流量查看阶段
    Browser->>WebUI: 访问流量分析页面
    WebUI->>Storage: 查询流量记录
    Storage-->>WebUI: 返回流量列表
    WebUI-->>Browser: 展示流量(列表/树/域名视图)
    
    Browser->>WebUI: 点击查看详细信息
    WebUI->>Storage: 获取完整流量记录
    Storage-->>WebUI: 返回请求/响应详情
    WebUI-->>Browser: 展示请求和响应内容
    
    Note over Browser,AI: 3. AI分析阶段
    Browser->>WebUI: 点击AI分析按钮
    WebUI->>Storage: 获取流量记录
    Storage-->>WebUI: 返回流量数据
    
    WebUI->>WebUI: 构建分析提示词
    WebUI->>AI: 调用AI API分析安全性
    
    AI->>AI: 分析请求/响应
    AI->>AI: 识别潜在漏洞
    AI->>AI: 生成分析报告
    AI-->>WebUI: 返回分析结果
    
    WebUI->>Storage: 保存分析结果
    WebUI-->>Browser: 展示分析结果和漏洞
    
    Note over Browser,Target: 4. 流量重放阶段
    Browser->>WebUI: 修改并重放请求
    WebUI->>Storage: 获取原始流量
    Storage-->>WebUI: 返回流量数据
    
    WebUI->>WebUI: 应用用户修改
    WebUI->>Target: 发送修改后的请求
    Target-->>WebUI: 返回响应
    WebUI-->>Browser: 展示重放结果
```




