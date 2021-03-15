---
solution: Campaign Standard
product: campaign
title: 测试触发器
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: 触发器
role: 数据架构师
level: 中间
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 2%

---


# 测试触发器{#testing-your-triggers}

以下疑难解答提示将帮助您解决在将触发器与Adobe Campaign结合使用时可能遇到的最常见问题：

**功能是否已激活？**

要检查是否已激活触发器 — 活动集成，请单击左上角的Adobe Campaign标志，然后选择&#x200B;**[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]**。 您应当看到&#x200B;**[!UICONTROL Experience Cloud Triggers]**&#x200B;项。

如果您看到它，请继续执行下一步。

否则，请与您的Adobe客户经理或专业服务合作伙伴联系。 请参阅[激活功能](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality)。

**尝试创建触发器**

按照[在活动](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign)中创建映射触发器中所述的步骤创建触发器。

如果创建了触发器，请继续执行下一步。 否则，表示触发器端点连接失败。 检查是否已在Experience Cloud(激活服务)中设置触发器。 否则，请联系您的Adobe客户经理或专业服务合作伙伴。 需要以下信息：

* Marketing Cloud公司名称
* IMS 组织 ID
* Analytics登录公司(可以与Marketing Cloud公司名称相同)

**尝试发布触发器**

按照[在活动](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign)中创建映射触发器中所述的步骤发布触发器。

如果发布成功，请继续执行下一步。 否则，请与Adobe联系以重新启动实例并重试。

**从网站生成触发器**

按照[编辑事务性消息模板](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template)中所述的步骤编辑和发布事务模板。 然后，测试从网站生成触发器。

如果Analytics收到触发器，请继续执行下一步。 否则，请检查以下项目：

* 已为Analytics启用触发器
* 在DTM中启用了使用MCID和Analytics的网站
* 创建触发器时使用了正确的Analytics报表包

**触发器是否由活动接收？**

否则，检查是否从管线接收到触发器。

否则，联系Adobe以检查管线端点的配置。

如果是，请遵循以下准则：

* 检查活动数据源中的对帐ID类型。
* CustomerId数据源是通过Customer Attributes创建的。
* 检查数据源ID。
* 请求Adobe在数据源配置后重新启动活动实例。
* 检查触发器报告中的触发器分析问题。

**触发器是否处于待定状态？**

否则，请继续执行下一步。 如果是，请遵循以下准则：

* 检查是否已发布事务模板。
* 检查用户档案是否未。
* 检查类型规则的应用。
* 检查事务性消息的日志。

**消息是否有效？**

如果消息无效，请检查以下项目：

* 对于标记为无效的触发器扩充个性化字段，请从关联的eventCusResource集合中验证事务模板。
* 验证消息格式

