---
description: 本文章皆在带你快速了解 TrMenu 3.0 以及升级步骤
---

# 升级向导

## 更新内容

### 底层

* 配置文件 & 语言文件 格式全部重新设计
* 90% 代码完全重写, 瞄准极致性能体验
* 发包虚拟容器结构完全重制，更快 & 更灵活

#### 功能

* 新增 `Free-Slot` 项，解除目标槽位的物品锁定 （不稳定）

#### 材质

```text
head:%player_name% head:BlackSky
head:eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvNDRmNDUyZDk5OGVhYmFjNDY0MmM2YjBmZTVhOGY0ZTJlNjczZWRjYWUyYTZkZmQ5ZTZhMmU4NmU3ODZlZGFjMCJ9fX0=
head:44f452d998eabac4642c6b0fe5a8f4e2e673edcae2a6dfd9e6a2e86e786edac0

repo:myCustomItem
repo:%custom_variable_whichreturnstheid%

source:HDB:random
source:ORAXEN:itemId

{json Content}
```

* 特殊物品不再需要 { } 、&lt;&gt; 等
* HeadDatabase / Oraxen / **ItemsAdder**\(新\) ****等物品挂钩需要以 ItemSource 格式
* SkinsRestorer 的挂钩和自定义材质头颅一律集合到玩家头颅中，将自动检测处理

#### 条件

条件检测是本次更新最大的改动部分

现在条件弃用了 TrMenu 2 所提供的 “智能表达式”，仅支持 **Kether** 和 **JavaScript** 两种语句. 且默认使用 Kether 语句

* **Kether**
  * Kether 官方文档会提供使用说明
* **JavaScript**
  * 需要 js 前缀，例如 `condition: 'js: player.getHealth() > 20.0'`
  * 全部缓存，不支持动态编译变量，使用变量需要套函数
  * 默认提供**对象**
    * `player`
    * `bukkitServer`
    * `utils`
  * 默认提供**函数**
    * `vars("STRING")` 编译变量，返回 String
    * `varInt("STRING")` 编译变量，返回整型

> 弃用 v2 写法原因:
>
> ```text
> 1. 臃肿不灵活，不完善引发的错误多
> 2. 没有规范缓存、变量处理
> ```

#### 函数

{% page-ref page="../usage/functions.md" %}

#### 动作

* **ActionBound** 弃用 v1 遗留的 \_\|\|\_ 写法，现阶段统一为 `&&&`
* **Title** 动作统一规范格式为
  * `title: [标题] [副标题] [渐入时间] [停留] [渐出时间]`
  * 包含空格的标题文本应用 · 括起
* **Refresh** 动作现在可以指定图标槽位来刷新单个图标
* **ActionOption** 动作参数现在推荐使用 `{[TYPE]=[VALUE]}` 的格式定义
* **InputCatcher** 捕获器现在规范的参数包括 `type`, `start`, `cancel`, `end`. 特殊参数有 `display`, `itemLeft`, `itemRight`, `content` & 新增 BOOK 类型的捕获器

#### 数据

* Meta & Data 功能模块重写，新增 GlobalData 用以设置全局变量
* 可通过 函数 功能调用

#### 命令

* 物品仓库和物品转换合并为一个命令
* 音效预览功能基于 ReceptacleAPI 重写
* 性能损耗统计功能重写
* 菜单列表格式化
* 调试功能重写 Mirror & Dump 功能集成到 Debug 下

{% page-ref page="../usage/command.md" %}

#### API

* 提供 `ReceptacleAPI` 创建自定义虚拟容器，使用实例可参照 `me.arasple.mc.trmenu.module.internal.command.impl.CommandSounds`

## 开始

由于 v3.x 与 v2.x 的配置 & 语言结构完全不兼容，菜单部分兼容

因此为了更好的完成升级，请先将旧的 TrMenu 文件夹重命名备用，

然后替换插件后生成新的 TrMenu 文件夹

## 配置

根据本 Wiki 快速了解配置结构 & 根据需要配置

## 菜单

不兼容的点

* 内置函数 & 条件 & 脚本
* 部分挂钩材质写法
* \(v1.x \) TITLE 动作写法
* \(v1.x\) 动作选项绑定写法 `_||_`

解决方案

* 确保完整阅读新版文档
* 按新格式重写条件（对于 JavaScript 需要处理字符串相关表达式）

## Q & A

#### 为什么不提供一键迁移

本次更新摒弃了 v2 的大部分臃肿设计 & 重写了几乎所有模块

尤其涉及到脚本、条件方面的，迁移功能实属不容易做

如果你只使用了一些简单的条件或 JavaScript 形式的，相对来说升级要容易些

例如应用替换功能 `hasPerm.`  -&gt; `perm *`

#### 有必要升级吗

对于正在运行的大型服务器，且菜单量大的，短期内没有必要

新服或菜单需求量少（条件表达式少）的推荐尽快升级

旧版本已停止维护和支持，不再处理遗留问题



