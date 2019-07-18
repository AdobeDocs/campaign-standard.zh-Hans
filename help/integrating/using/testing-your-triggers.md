---
title: 测试触发器
seo-title: 测试触发器
description: 测试触发器
seo-description: null
page-status-flag: 从未激活
uuid: b3a6667d-e843-4ad6-817e-d91542 b5 f2 e2
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 集成
content-type: reference
topic-tags: 使用营销活动和触发器
discoiquuid: f67e69f2-09fb-4f33-b2 c3-c67 a060743 e3
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Testing your triggers{#testing-your-triggers}

以下故障排除提示将帮助您解决在Adobe Campaign中使用触发器时可能遇到的最常见问题：

**该功能是否已激活？**

To check if the Triggers - Campaign integration is activated, click the Adobe Campaign logo, in the top left corner, then select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]**. You should see the **[!UICONTROL Experience Cloud Triggers]** item.

如果您看到它，请继续执行下一步。

如果没有，请与您的Adobe客户经理或专业服务合作伙伴联系。See [Activating the functionality](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**尝试创建触发器**

Follow the steps described in [Creating a mapped trigger in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) to create a trigger.

如果创建了触发器，请转到下一步。如果没有，则表示触发器端点连接失败。检查是否在Experience Cloud中设置触发器(激活服务)。如果不是，请与您的Adobe客户经理或专业服务合作伙伴联系。需要以下信息：

* Marketing Cloud公司名称
* IMS ORG ID
* Analytics登录公司(可以与Marketing Cloud公司名称相同)

**尝试发布触发器**

Follow the steps described in [Creating a mapped trigger in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) to publish the trigger.

如果出版物成功，请继续执行下一步。如果没有，请联系Adobe重新启动实例，然后重试。

**从网站生成触发器**

Follow the steps described in [Editing the transactional message template](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) to edit and publish the transactional template. 然后，从网站测试触发器生成。

如果Analytics收到触发器，请继续执行下一步。如果没有，请检查以下项目：

* 触发器已启用Analytics
* 已在DTM中启用使用了MCID和Analytics的网站
* 在创建触发器时使用正确的Analytics报告套件

**Campaign是否接收到触发器？**

如果没有，请检查是否从渠道收到触发器。

如果没有，请联系Adobe以检查管道端点的配置。

如果是，请遵循以下指南线：

* 在Campaign数据源中检查帐帐ID类型。
* CustomerID数据源是通过客户属性创建的。
* 检查数据源ID。
* 要求Adobe在数据源配置后重新启动Campaign实例。
* 选中触发报告中的分析问题。

**等待状态中是否有触发器？**

否则，请继续执行下一步。如果是，请遵循以下指南线：

* 检查交易模板是否已发布。
* 如果启用了Campaign的appublyTyScore阈值，请检查该触发器的倾向得分。
* 检查配置文件未列入黑名单。
* 检查字型规则的应用。
* 检查交易消息的日志。

**消息是否有效？**

如果消息无效，请检查下列项目：

* 对于标记为无效的丰富的丰富个性化字段，请从关联的EventCusResource集合验证交易模板。
* 验证消息格式

