# 隐私政策

> 最后更新：2026-03-16

## 核心承诺

智子X从第一天起就做了一个决定：**服务器不保存用户数据，不经手API Key，不代理平台请求。**

## 我们收集什么数据

**简短回答：我们不收集任何数据。**

智子X浏览器扩展仅在您的本地浏览器中运行，所有数据存储在您的设备上：
- 平台登录Cookie（存储在浏览器本地）
- AI API Key（存储在localStorage）
- 采集的文章内容（存储在IndexedDB）
- 平台认证Token（存储在chrome.storage.local）

## 数据如何使用

扩展作为"哑管道"，仅负责转发您的请求：
- 读取您的平台Cookie，用于向平台API发起请求
- 读取您的API Key，用于向AI服务商发起请求
- 所有请求都从您的浏览器直接发出，使用您自己的网络和IP

**扩展不会：**
- 上传任何数据到智子X服务器
- 记录您的浏览历史
- 分析您的使用行为
- 与第三方共享任何信息
- 在后台自动执行任何操作

## 权限说明

扩展请求以下权限，仅用于实现核心功能：

### storage
存储平台认证状态和AI任务队列数据到本地

### cookies
读取您在内容平台的登录Cookie，用于API请求认证。不会修改或删除Cookie，不会上传到任何服务器

### scripting
在平台页面注入脚本提取数据（如微信Token、抖音视频信息）。仅在您主动使用采集功能时执行，不会修改页面内容

### tabs
管理平台标签页，为采集功能创建后台标签页。不会监控您的浏览行为

### declarativeNetRequest
为快手平台临时注入移动端User-Agent（快手API仅向移动端返回数据）。仅在您解析快手链接时生效，不会拦截其他请求

## 第三方服务

当您使用扩展功能时，您的浏览器会直接连接：

### 内容平台
- 微信公众号（mp.weixin.qq.com）
- B站（bilibili.com）
- 抖音（douyin.com）
- 小红书（xiaohongshu.com）
- 快手（kuaishou.com）

### AI服务商（如果您配置了）
- Claude（anthropic.com）
- OpenAI（openai.com）
- Google Gemini（generativelanguage.googleapis.com）
- DeepSeek（deepseek.com）
- Grok（x.ai）

**重要**：这些连接不经过智子X服务器，直接从您的浏览器发出，受各平台自己的隐私政策约束。

## 数据安全

- 所有敏感数据仅存储在您的本地浏览器
- 扩展使用浏览器的安全存储API（chrome.storage.local、localStorage、IndexedDB）
- 您可以随时清除浏览器数据来删除所有信息
- 建议定期备份重要数据，避免浏览器重装或清理缓存时丢失

## 数据流向

```
您的浏览器 → 浏览器扩展（透明转发）→ 目标平台/AI API
            ↑ 您自己的网络和IP
            ↑ 数据不经过智子X服务器
```

## 您的权利

- 随时查看存储在本地的数据
- 随时导出您的数据
- 随时删除您的数据
- 随时卸载扩展

## 儿童隐私

智子X不针对13岁以下儿童，我们不会故意收集儿童的个人信息。

## 政策更新

我们可能会更新本隐私政策。更新后会在此页面发布新版本，并更新"最后更新"日期。

## 联系我们

如有隐私相关问题，请通过以下方式联系：
- GitHub Issues: https://github.com/zhiziX/zhiziX/issues
- 项目主页: https://github.com/zhiziX/zhiziX

## 更多信息

详细的数据主权理念和技术架构，请阅读：
- [数据所有权白皮书](https://github.com/zhiziX/zhiziX/blob/main/docs/data-ownership-whitepaper.md)
