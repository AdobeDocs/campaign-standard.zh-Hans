---
title: 测试触发器
description: null
page-status-flag: 从未激活
uuid: b3a6667d-e843-4ad6-817e-d91542b5f2e2
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 集成
content-type: 参考
topic-tags: 使用系列活动和触发器
discoiquuid: f67e69f2-09fb-4f33-b2c3-c67a060743e3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 测试触发器{#testing-your-triggers}

以下疑难解答提示将帮助您解决在Adobe Campaign中使用触发器时可能遇到的最常见问题：

**是否激活了该功能？**

要检查触发器——营销活动集成是否已激活，请单击左上角的Adobe Campaign徽标，然后选择 **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]**。 您应该看到该 **[!UICONTROL Experience Cloud Triggers]** 项目。

如果您看到它，请继续执行下一步。

如果没有，请与您的Adobe客户主管或专业服务合作伙伴联系。 请参 [阅激活功能](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality)。

**尝试创建触发器**

按照在Campaign中创建映 [射触发器中所述的步骤](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) ，创建触发器。

如果已创建触发器，请继续执行下一步。 否则，表示触发器端点连接失败。 检查Experience Cloud中是否提供了触发器（激活服务）。 否则，请联系您的Adobe客户主管或专业服务合作伙伴。 需要以下信息：

* Marketing cloud公司名称
* IMS组织ID
* Analytics登录公司（可以与Marketing cloud公司名称相同）

**尝试发布触发器**

按照在Campaign中创建映 [射触发器中所述的步骤](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) ，发布触发器。

如果发布成功，请继续执行下一步。 如果没有，请与Adobe联系以重新启动实例，然后重试。

**从网站生成触发器**

按照编辑事务消息模 [板中所述的步骤进行操作](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) ，以编辑和发布事务模板。 然后，测试从网站生成触发器。

如果Analytics收到触发器，请继续执行下一步。 如果不是，请检查以下项目：

* 已为Analytics启用触发器
* 在DTM中启用了使用MCID和Analytics的网站
* 创建触发器时使用正确的Analytics报表包

**系列活动是否收到触发器？**

否则，检查是否从管道接收到触发器。

否则，请与Adobe联系以检查管线端点的配置。

如果是，请遵循以下指南行：

* 检查营销活动数据源中的对帐ID类型。
* CustomerId数据源是通过Customer Attributes创建的。
* 检查数据源ID。
* 请求Adobe在配置数据源后重新启动Campaign实例。
* 检查触发器报告中的触发器解析问题。

**触发器是否处于待定状态？**

否则，请继续执行下一步。 如果是，请遵循以下指南行：

* 检查是否已发布事务模板。
* 如果为Campaign启用了prediteScore阈值，则从渠道中检查触发器的倾向得分。
* 检查配置文件是否未列入黑名单。
* 检查排版规则的应用。
* 检查事务性消息的日志。

**消息是否有效？**

如果消息无效，请检查以下项目：

* 要触发标记为无效的丰富化个性化字段，请验证关联的eventCusResource集合中的事务模板。
* 验证消息格式

