---
title: 使用Adobe Campaign Standard提高您的声誉
description: 了解如何通过管理重复的电子邮件地址和隔离来提高Adobe Campaign Standard的声誉。
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44049443f8028ed26089ee0d49944ebac6a62111

---


# 提高声誉{#improving-reputation}

为避免让收件人精疲力尽，请从目标中删除重复的电子邮件地址。 此步骤可保护您的发送信誉，并确保良好的隔离管理。 Adobe Campaign提供了实施这些建议的必要工具，并避免了被ISP列入黑名单的风险。

您将在下面找到有关复制和隔离管理的详细信息。

## 重复项 {#duplicates}

拥有重复的电子邮件地址可能会产生多种后果：
* 同一消息已多次发送。 即使Campaign在发送之前默认执行重复数据消除过程，在拆分目标时，也无法阻止具有相同内容的不同操作发送相同的消息。
* 未接受取消订阅请求。 如果收件人在收到消息后取消订阅，则其重复的配置文件仍有资格获取将来的消息。

除了选择加入程序的这一侧，这种情况还可能导致用户将消息视为垃圾信息，并在ISP触发黑名单过程。

对数据库执行操作时必须特别小心。 要尽可能避免重复，必须执行以下操作：
* **必须仔细配置导入。** 这在选择协调密钥时尤其重要。
* **修改电子邮件地址时请注意。** 更改后的电子邮件地址也可以是重复的源。 特别地，具有不同域的两个地址可以被路由到同一邮箱，例如，在某个公司已经更改名称并且已维护前一个域一段时间的情况下：joe.doe@amce-co.com和joe.doe@acme-rebranded.com。
* **在自动导入过程中要注意。** 无论是列表还是来自其他数据库，它们都是管理配置文件时要考虑的元素。 当您删除或移动另一个分区中的配置文件时会发生什么情况？ 它可能通过自动导入在初始分区中重新创建，例如，下订单时。
* **配置文件应分类到不同的文件夹。**

同样，在不同分区之间重复的情况也是正常的。 例如，当为第三方或不同的公司实体发送时，出于不同的原因，同一人成为收件人是合乎逻辑的。 但是，在同一分区内查找副本很少是正常的。

## 检疫 {#quarantines}

Adobe Campaign管理隔离地址列表。 在传送分析过程中，默认情况下将排除其地址被隔离的收件人：他们没有目标。

隔离管理在本节中 [有详细介绍](../../sending/using/understanding-quarantine-management.md)。

例如，当收件箱已满或地址不存在时，可以隔离电子邮件地址。 在所有情况下，隔离都与本条中规定的特定规 [则相对应](../../sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine)。
