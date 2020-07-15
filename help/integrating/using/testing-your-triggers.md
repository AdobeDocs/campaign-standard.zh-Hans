---
title: 测试触发器
description: null
page-status-flag: never-activated
uuid: b3a6667d-e843-4ad6-817e-d91542b5f2e2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: f67e69f2-09fb-4f33-b2c3-c67a060743e3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bd74905985734412b4fb11ad11d70faf9fcc9ca6
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---


# 测试触发器{#testing-your-triggers}

以下疑难解答提示将帮助您解决在将触发器与Adobe Campaign结合使用时可能遇到的最常见问题：

**功能是否已激活？**

要检查触发器-活动集成是否已激活，请单击左上角的Adobe Campaign标志，然后选择 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]**。 您应该看到该 **[!UICONTROL Experience Cloud Triggers]** 项目。

如果您看到它，请继续下一步。

否则，请与您的Adobe客户经理或专业服务合作伙伴联系。 请参 [阅激活功能](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality)。

**尝试创建触发器**

按照活动中创建 [映射触发器中所述的步骤](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) ，创建触发器。

如果已创建触发器，请继续执行下一步。 否则，表示触发器端点连接失败。 检查触发器是否以Experience Cloud(激活服务)提供。 否则，请联系您的Adobe客户经理或专业服务合作伙伴。 需要以下信息：

* Marketing Cloud公司名称
* IMS组织ID
* Analytics登录公司(可以与Marketing Cloud公司名称相同)

**尝试发布触发器**

按照活动中创建 [映射触发器中所述的步骤](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) ，发布触发器。

如果发布成功，请继续执行下一步。 否则，请与Adobe联系以重新启动实例，然后重试。

**从网站生成触发器**

按照编辑事务性消息模板中 [所述的步骤](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) ，编辑和发布事务模板。 然后，测试从网站生成触发器。

如果Analytics接到触发器，请继续下一步。 如果不是，请检查以下项目：

* 触发器为Analytics启用
* 使用MCID的网站在DTM中启用Analytics
* 创建触发器时使用正确的Analytics报告套件

**活动是否收到触发器？**

如果没有，则检查是否从管道接收到触发器。

否则，请与Adobe联系以检查管线端点的配置。

如果是，请遵循以下指南行：

* 检查活动数据源中的对帐ID类型。
* CustomerId数据源是通过Customer Attributes创建的。
* 检查数据源ID。
* 请求Adobe在数据源配置后重新启动活动实例。
* 检查触发器报告中的触发器解析问题。

**触发器是否处于待定状态？**

否则，请继续下一步。 如果是，请遵循以下指南行：

* 检查事务模板是否已发布。
* 检查用户档案是否未开启阻止列表。
* 检查类型规则的应用。
* 检查事务性消息日志。

**邮件有效吗？**

如果消息无效，请检查以下项目：

* 对于标记为无效的触发扩充个性化字段，请从关联的eventCusResource集合验证事务模板。
* 验证消息格式

