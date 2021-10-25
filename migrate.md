---
description: Only applicable to 3.0-pre9 or earlier v3 version TrMenu
---

# Migration Guide

## Migrate from the earlier v3 version of TrMenu to 3.0-pre12 and above.
> Although TabooLib-pre29 and later versions have automatic migration, we still recommend you to migrate according to the following instructions to avoid migration failure.

After TabooLib 6.0.0 released the preview version, it has been adapted to the server above 1.17.
However, its framework is greatly changed, which may cause some features of TrMenu to be different from that of TabooLib 5.x.
Therefore, some content needs to be manually migrated to quickly update to TrMenu-pre12.

## Migration Instructions
To help you update to the latest version faster, some mandatory and optional \(optional\) migration options are marked below.
### Configuration File
#### [Optional] settings.yml
Because TabooLib 6.x updated the feature of automatically detecting the language of the executor, the node `Options.Language` has been removed,
Just remove the relevant nodes in the configuration file:
```yaml
Options:
  Language: en_US
```
#### [Requirement] lang/*.yml \(I.e. all language files\)
Because TabooLib 6.x has updated the function of automatically updating configuration files, in order to better realize automatic updating of configuration files.
Therefore, the language file is required to be 'flattened' instead of 'multi-level', so the original language file format cannot be read again.

Suggestion: Delete all language files in the `plugins/TrMenu/lang` directory.
#### [1.8 User] datasource.yml
Because the 1.8 server-side JDBC driver is too old, it is necessary to make some modifications to the configuration file.
However, the configuration file did not appear in the previous TrMenu \(pre9 and previous\) versions, so after completing the migration of the previous two configuration files, you need to start the server first.

Not surprisingly, you will see the following error message:
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
At this time, the configuration file `plugins/TrMenu/datasource.yml` will appear.

Then find the configuration file node `DefaultSettings.ConnectionTestQuery`, the default value is `~`, just change it to `SELECT 1` to complete the migration.
