---
layout: default
title: FAQ
nav_order: 99
---

## JVM

### Fail to identify build tool for compile

选择 JVM，但是未能识别到构建工具，

建议使用 Java、Kotlin 进行扫描。

## Scanner 没有数据

```
java "-Ddburl=jdbc:mysql://localhost:3306/archguard?user=root&password=&useSSL=false" -jar scan_sourcecode.jar --system-id=6 --language=java --path=.
```

1. 运行目录 scanner 中的 .jar 是否完整。如果出错了，需要从 GitHub 重新下载。
2. 查看是否生成对应的 sql 文件。如果没有的话，建议可以提交 issue，包含错误日志。

### Error: Unable to access jarfile scan_sourcecode.jar

出错：Error: Unable to access jarfile scan_sourcecode.jar

原因：连接不了 Github 下载对应的 jar

建议：

1. 选择合适的 VPN 工具，连接下载。
2. 将 jar 包打包到进窗口中

未来将提供一个 all in one 的大版本包。

## Git

### Git 源码配置

error: cannot run ssh: No such file or directory
fatal: unable to fork

ArchGuard 直接调用 `git clone` 去 clone 源码

如果配置了用户名和秘密，则会执行 `repo.replace("//", "//${urlEncode(systemInfo.username)}:${urlEncode(systemInfo.getDeCryptPassword())}@")`，以生成一个带用户名和密码的 URL。
