---
title: 测试触发器
description: 了解疑难解答提示，以帮助您解决在将触发器与Adobe Campaign结合使用时可能遇到的最常见问题。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 66628f2a-6ed3-4b12-b2ed-9b9eec440dc3
source-git-commit: 602878233e919d01f3972167cb6d3a1acc4cfc02
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 1%

---

# 测试触发器{#testing-your-triggers}

以下故障诊断提示可帮助您解决在将触发器与Adobe Campaign结合使用时可能遇到的最常见问题：

**功能是否已激活？**

要检查Triggers - Campaign集成是否已激活，请单击左上角的Adobe Campaign徽标，然后选择 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]**. 您应会看到 **[!UICONTROL Experience Cloud Triggers]** 项目。

如果您看到它，请继续执行下一步。

如果没有，请联系您的Adobe客户经理或专业服务合作伙伴。 请参阅 [激活功能](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**尝试创建触发器**

按照 [在Campaign中创建映射触发器](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) 以创建触发器。

如果已创建触发器，请继续执行下一步。 否则，表示触发器端点连接失败。 检查Triggers是否在Experience Cloud（激活服务）中配置。 如果没有，请联系您的Adobe客户经理或专业服务合作伙伴。 需要提供以下信息：

* Marketing Cloud公司名称
* 组织ID
* Analytics登录公司(可以与Marketing Cloud公司名称相同)

**尝试发布触发器**

按照 [在Campaign中创建映射触发器](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) 来发布触发器。

如果发布成功，请继续执行下一步。 如果没有，请联系Adobe以重新启动实例并重试。

**从网站生成触发器**

按照 [编辑事务型消息模板](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) 以编辑和发布事务型模板。 然后，测试从网站生成触发器。

如果Analytics收到触发器，请继续执行下一步。 如果没有，请检查以下项目：

* 已为Analytics启用触发器
* 在DTM中启用了使用MCID和Analytics的网站
* 创建触发器时，会使用正确的Analytics报表包

**Campaign是否收到触发器？**

如果没有，则检查是否从管道接收到触发器。

如果没有，请联系Adobe以检查管线端点的配置。

如果是，请遵循以下准则：

* 在Campaign数据源中检查协调ID类型。
* 客户ID数据源是通过客户属性创建的。
* 检查数据源ID。
* 请求Adobe在数据源配置后重新启动Campaign实例。
* 在触发器报告中检查触发器解析问题。

**触发器是否处于待定状态？**

如果没有，请继续执行下一步。 如果是，请遵循以下准则：

* 检查事务型模板是否已发布。
* 检查用户档案是否未阻止列表。
* 检查分类规则的应用。
* 检查事务型消息的日志。

**消息有效吗？**

如果消息无效，请检查以下项目：

* 要触发标记为无效的扩充个性化字段，请从关联的eventCusResource集合中验证事务模板。
* 验证消息格式
