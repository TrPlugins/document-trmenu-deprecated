---
description: After obtaining the JAR file of this plugin from a regular channel, install it on the server
---

# Install

## Requirement

{% hint style="info" %}
TrMenu needs to be downloaded and installed on the Internet
{% endhint %}

| Software | Version |
| :--- | :--- |
| Spigot | 1.8-1.17 |
| Paper / Tuinity | 1.8-1.17 |
| CatSever \(Forge\) | √ |
| Akarin | unknown |
| Arclight \(Forge\) | √ |
| Mohist \(Forge\) | √ |
| Other unknown servers so | uncertain |

* Recommended:[PlaceholderAPI](http://ci.extendedclip.com/job/PlaceholderAPI/) \(Must ensure that the version is in **v2.10.10 +**\)

## Install

* Throw **TrMenu.jar** into the plugins directory
* Restart the server

## Compatible

Known incompatible plugins & solutions：

* **LibsDisguises**
  * Reason: Incompatible
  * Solution:
    * Set `Remove-Armor` to `false` in the configuration file of LibsDisguises

## Note

{% hint style="warning" %}
TrMenu **does not support all** forms of **reload**，

Forcible hot reload operation may cause unknown errors, please operate with caution

including but not limited to：

* TrMenu reload TrMenu via Plugman \(or similar plugin\)
* Restart the server through the /reload \(confirm\) command
{% endhint %}

