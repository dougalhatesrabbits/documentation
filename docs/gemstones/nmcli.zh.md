---
title: nmcli - 设置自动连接
author: wale soyinka
---

# 修改 NetworkManager 配置文件的自动连接属性

在Rocky Linux 系统上，首先使用 nmcli 来查询和显示所有网络连接的自动连接属性的当前值。 输入：

```
nmcli -f name,autoconnect connection 
```

要更改网络连接的属性值，请使用 `nmcli connect` 的子命令 `modify`。 例如，要将 `ens3` 网卡的配置中的自动连接属性值 从 `no` 改为 `yes`，输入：

```
sudo nmcli con mod ens3 connection.autoconnect yes
```

## 命令说明

```
connection (con)       :  NetworkManager 连接对象 
modify (mod)           :  修改给定连接配置文件的一个或多个属性
connection.autoconnect :  设置项和要更改的属性 (<setting>.<property>)
-f, --fields           :  指定要输出的字段

```

## 说明

这篇提示说明了修改现存的 NetworkManager 的连接档案的方法。  在刚刚安装 Rocky Linux 或收到系统更新后，网络接口不会自动被激活的情况下，本篇提示是非常有用的。 该问题的原因往往是自动连接属性的值被设置为 `no`。 您可以使用 `nmcli` 命令快速将值更改为 `yes`。  