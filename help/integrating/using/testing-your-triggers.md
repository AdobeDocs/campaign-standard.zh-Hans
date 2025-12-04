---
title: 测试触发器
description: 了解故障排除提示，以帮助您解决在将Triggers与Adobe Campaign结合使用时可能遇到的最常见问题。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 66628f2a-6ed3-4b12-b2ed-9b9eec440dc3
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 1%

---

# 测试触发器{#testing-your-triggers}

以下故障诊断提示可帮助您解决在将Triggers与Adobe Campaign结合使用时可能遇到的最常见问题：

**功能是否已激活？**

要检查是否已激活Triggers - Campaign集成，请单击左上角的Adobe Campaign徽标，然后选择&#x200B;**[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]**。 您应该会看到&#x200B;**[!UICONTROL Experience Cloud Triggers]**&#x200B;项。

如果您看到它，请转到下一步。

如果没有，请联系您的Adobe客户经理或专业服务合作伙伴。 请参阅[激活功能](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality)。

**尝试创建触发器**

按照[在Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign)中创建映射触发器中描述的步骤创建触发器。

如果已创建触发器，请继续执行下一步。 如果不存在，则表示触发器终结点连接失败。 检查是否在Experience Cloud（激活服务）中配置了触发器。 如果不是，请联系您的Adobe客户经理或专业服务合作伙伴。 需要以下信息：

* Marketing Cloud公司名称
* 组织 ID
* Analytics登录公司(可以与Marketing Cloud公司名称相同)

**尝试发布触发器**

按照[在Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign)中创建映射触发器中描述的步骤发布触发器。

如果发布成功，请继续下一步骤。 如果不能，请联系Adobe以重新启动您的实例，然后重试。

**从网站生成触发器**

按照[编辑事务型消息模板](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template)中描述的步骤编辑和发布事务型模板。 然后，测试从网站生成的触发器。

如果Analytics收到了触发器，请继续执行下一步。 如果没有，请检查以下各项：

* 已为Analytics启用触发器
* DTM中已启用使用MCID和Analytics的网站
* 创建触发器时使用正确的Analytics报表包

**Campaign是否收到触发器？**

如果没有，检查是否从管道收到了触发器。

如果不能，请联系Adobe以检查管道端点的配置。

如果是这样，请遵循以下准则：

* 在Campaign数据源中检查协调ID类型。
* CustomerId数据源通过客户属性创建。
* 检查数据源ID。
* 请求Adobe在配置数据源后重新启动Campaign实例。
* 检查触发器报告中的触发器解析问题。

**触发器是否处于挂起状态？**

如果不能，请继续下一步。 如果是这样，请遵循以下准则：

* 检查是否已发布事务型模板。
* 检查配置文件是否未处于阻止列表状态。
* 检查分类规则的应用。
* 检查事务型消息的日志。

**消息有效吗？**

如果消息无效，请检查以下各项：

* 对于标记为无效的触发器扩充个性化字段，请从关联的eventCusResource集合中验证事务型模板。
* 验证消息格式
