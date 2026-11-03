# 使用 curl 获取网站 HTTP 响应头

## 一、实验目的

了解 curl 命令行工具的基本用法，使用 curl 获取网站的 HTTP 响应头，并分析返回结果。

## 二、实验环境

- 操作系统：Windows
- 命令行环境：Windows PowerShell
- curl 版本：8.21.0

## 三、实验步骤

首先，在 PowerShell 中执行以下命令，检查 curl 版本：

```powershell
curl.exe --version
```

命令成功输出版本信息，说明当前系统可以使用 curl。

随后，执行以下命令，获取百度首页的 HTTP 响应头：

```powershell
curl.exe -I https://www.baidu.com
```

其中，`-I` 参数表示发送 HEAD 请求，只获取响应头，不获取响应正文。

**【在这里插入操作截图】**

## 四、结果分析

本次请求返回了以下信息：

```text
HTTP/1.1 200 OK
Content-Length: 0
Content-Type: text/html
Server: bfe
```

`200 OK` 表示请求成功；`Content-Type: text/html` 表示资源的内容类型为 HTML；`Server: bfe` 是服务器返回的服务标识。

本次响应中还出现了缓存控制和 Cookie 相关字段。由于使用了 `-I` 参数，终端只显示响应头，没有显示网页正文。响应中的 `Content-Length: 0` 也不能据此说明百度首页没有内容。

## 五、实验总结

通过本次实验，我学会了使用 `curl.exe --version` 查看版本信息，以及使用 `curl.exe -I` 获取网站响应头，并了解了 HTTP 状态码和部分响应头字段的含义。
