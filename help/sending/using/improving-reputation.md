---
solution: Campaign Standard
product: campaign
title: 提高你在Adobe Campaign Standard的声誉
description: 了解如何通过管理Adobe Campaign Standard电子邮件地址和隔离来提高您在重复的声誉。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 2%

---


# 提高您的声誉{#improving-reputation}

为避免让收件人精疲力尽，请从目标中删除重复电子邮件地址。 此步骤可保护您发送的信誉并确保良好的隔离管理。 Adobe Campaign优惠执行这些建议所需的工具，并避免被ISP添加阻止列表到的风险。

在下面，您将找到有关重复和隔离管理的详细信息。

## 重复{#duplicates}

拥有重复电子邮件地址可能会产生多种后果：
* 同一邮件被多次发送。 即使活动在发送前默认执行外部重复数据删除过程，在拆分目标时，也没有任何内容可以阻止具有相同内容的不同操作发送相同的消息。
* 退订请求未接受。 如果收件人在收到消息后取消订阅，其重复用户档案仍有资格获取将来的消息。

除了选择加入程序的这一侧行，这种情况还可能导致用户将消息视为垃圾信息，并在ISP阻止列表触发程序。

对数据库执行操作时，必须特别小心。 要尽可能避免重复，必须执行以下操作：
* **必须仔细配置导入。** 这在选择合并关键项时尤其重要。
* **修改电子邮件地址时请注意。** 更改的电子邮件地址也可以是重复源。特别地，具有不同域的两个地址可以被路由到同一邮箱，例如，在名称已更改且已保留前一个域一段时间的公司的情况下：joe.doe@amce-co.com和joe.doe@acme-rebranded.com。
* **在自动导入过程中请注意。** 无论是列表，还是来自其他数据库，它们都是管理用户档案时要考虑的元素。删除或移动其他分区中的用户档案时会发生什么情况？ 它可以通过自动导入在初始分区中重新创建，例如，下订单时。
* **用户档案应分类到不同的文件夹。**

同样，在不同分区之间的重复是正常的情况。 例如，当为第三方或不同的公司实体发送时，出于不同原因，同一人成为收件人符合逻辑。 但是，在同一分区内查找重复很少是正常的。

## 隔离{#quarantines}

Adobe Campaign 管理了一个隔离地址列表。在投放分析中，默认情况下将排除其地址被隔离的收件人:他们不是目标。

隔离管理详见[本节](../../sending/using/understanding-quarantine-management.md)。

可以隔离电子邮件地址，例如，当收件箱已满或地址不存在时。 在所有情况下，隔离均与本条[中所述的特定规则相对应。](../../sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine)
