# Fork 前言

选用 shell 脚本的原因就是运行无依赖。  
作者很久没更新了，issue 不解决，PR 不合并。  
具体修改如下 
> 1、修改获取 ip 的方式，直接通过第三方获取 ，`curl -s ip.sb `  
> 2、使用 ip.txt 缓存之前的 ip 地址，如果 ip 没有改动就不需要请求 dnspod 的接口  
> 3、优化部分代码  



# ArDNSPod

基于 DNSPod 用户 API 实现的纯 Shell 动态域名客户端，适配网卡地址。

# Usage

复制`dns.conf.example`到同一目录下的`dns.conf`并根据你的配置修改即可。

执行时直接运行`ddnspod.sh`，支持cron任务。

配置文件格式：
```
# 安全起见，不推荐使用密码认证
# arMail="test@gmail.com"
# arPass="123"

# 推荐使用Token认证
# 按`TokenID,Token`格式填写
arToken="12345,7676f344eaeaea9074c123451234512d"

# 每行一个域名 "根域名" "二级域名"
arDdnsCheck "test.org" "subdomain"
```

# 最近更新

2015/2/24
- 增加token鉴权方式 (by wbchn)

2015/7/7
- 使用D+服务获取域名解析

2016/2/25
- 增加配置文件，分离脚本与配置，适配内网。
- 加入Mac支持
- sed脚本POSIX化，可跨平台

2016/3/23
- 进一步POSIX化，支持Mac和大部分Linux发行版
- 更改配置文件格式

# Credit

Original: anrip

This version maintained by ProfFan
