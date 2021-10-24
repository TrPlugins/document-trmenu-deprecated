---
description: 仅适用于 3.0-pre9 或更早的 v3 版本 TrMenu
---

# 迁移指南

## 从更早的 v3 版本 TrMenu 迁入 3.0-pre12 以上.
> 尽管 TabooLib-pre29 及之后的版本已具备自动迁移, 但我们仍然建议您根据以下说明进行迁移, 以免发生迁移失败.

在 TabooLib 6.0.0 发布 preview 版后, 已适配 1.17 以上服务端.
但其框架大改, 可能导致 TrMenu 部分特性与 TabooLib 5.x 时期有所不同,
因此部分内容需要手动迁移以快速更新到 TrMenu-pre12.

## 迁移说明
为了帮助您更快地更新到最新版, 以下会标注一些必须执行和非必须(可选)迁移选项.
### 配置文件
#### [可选] settings.yml
因 TabooLib 6.x 更新了自动检测执行者语言的特性, 故移除了节点 `Options.Language`,
只需要移除位于该配置文件中的相关节点即可:
```yaml
Options:
  Language: en_US
```
#### [必须] lang/*.yml (即所有语言文件)
因 TabooLib 6.x 更新了自动更新配置文件的功能, 为了更好地实现自动更新配置文件.
因此要求语言文件'扁平化', 而不是'多级化', 故无法再次读取原语言文件格式.

建议: 删除 `plugins/TrMenu/lang` 目录下的所有语言文件.
#### [1.8 用户] datasource.yml
因 1.8 服务端 JDBC 驱动过旧, 因此需要对该配置文件做一些修改.
但该配置文件并没有出现在先前的 TrMenu(pre9 及以前) 版本中, 因此在完成前面两项配置文件的迁移后需要先启动一次服务端.

不出意外, 您会看到以下错误信息:
```
[xx:xx:xx] [Server thread/INFO]: [TrMenu] Enabling TrMenu v3.0-PRE-15
[xx:xx:xx] [Server thread/WARN]: SLF4J: No SLF4J providers were found.
[xx:xx:xx] [Server thread/WARN]: SLF4J: Defaulting to no-operation (NOP) logger implementation
[xx:xx:xx] [Server thread/WARN]: SLF4J: See http://www.slf4j.org/codes.html#noProviders for further details.
[xx:xx:xx] [Server thread/ERROR]: Error occurred while enabling TrMenu v3.0-PRE-15 (Is it up to date?)
java.lang.AbstractMethodError: org.sqlite.Conn.isValid(I)Z
	at com.zaxxer.hikari_4_0_3.pool.PoolBase.checkValidationSupport(PoolBase.java:464) ~[?:?]
	at com.zaxxer.hikari_4_0_3.pool.PoolBase.checkDriverSupport(PoolBase.java:447) ~[?:?]
	at com.zaxxer.hikari_4_0_3.pool.PoolBase.setupConnection(PoolBase.java:416) ~[?:?]
	at com.zaxxer.hikari_4_0_3.pool.PoolBase.newConnection(PoolBase.java:369) ~[?:?]
	at com.zaxxer.hikari_4_0_3.pool.PoolBase.newPoolEntry(PoolBase.java:206) ~[?:?]
	at com.zaxxer.hikari_4_0_3.pool.HikariPool.createPoolEntry(HikariPool.java:476) ~[?:?]
	at com.zaxxer.hikari_4_0_3.pool.HikariPool.checkFailFast(HikariPool.java:561) ~[?:?]
...
```
此时, 配置文件 `plugins/TrMenu/datasource.yml` 将会出现.

然后找到该配置文件节点 `DefaultSettings.ConnectionTestQuery`, 默认值为 `~`, 只需要将它更改为 `SELECT 1` 即可完成迁移.
