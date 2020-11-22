---
solution: Campaign Standard
product: campaign
title: 短信投放
description: 利用短信投放活动，可在工作流中配置发送单次发送短信，也可配置发送定期短信。
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: sms,main;delivery,smsContent,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 100%

---


# 短信投放{#sms-delivery}

## 说明{#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

利用 **[!UICONTROL SMS delivery]** 活动，可在工作流中配置发送短信。这可以是只发送一次的单次发送短信，也可以是定期短信。

* **单次发送短信是标准短信，只发送一次。**
* **而利用定期短信，则会在定义的时间段内多次向不同目标发送同一短信。**&#x200B;您可以按时段聚合投放，以获得对应于您需求的报告。

## 使用环境{#context-of-use}

**[!UICONTROL SMS delivery]** 活动通常用于向在同一工作流中算出的目标自动发送短信。

链接到调度程序时，您可以定义定期短信。

同一工作流中的上游活动，通过查询、交集之类的定向活动，定义了短信的收件人。

根据工作流执行参数，触发消息准备。在消息仪表板中，您可以选择是否请求手动确认以发送消息（默认要求）。您可以手动启动工作流，或在工作流中放置调度程序活动以自动执行。

## 配置{#configuration}

1. 将 **[!UICONTROL SMS delivery]** 活动拖放到工作流中。
1. 选择活动，然后使用所显示快捷操作中的 ![](assets/edit_darkgrey-24px.png) 按钮将其打开。

   >[!NOTE]
   >
   >您可以通过工作流操作栏中的 ![](assets/dlv_activity_params-24px.png) 按钮，访问活动的常规属性和高级选项（而非投放本身）。此按钮专用于 **[!UICONTROL SMS delivery]** 活动。可以通过短信仪表板中的操作栏，访问短信的属性。

1. 选择短信发送模式：

   * **[!UICONTROL SMS]**：短信只发送一次。您可以在此处指定是否向活动添加叫客过渡。此程序的第 7 步详细介绍了各种过渡类型。
   * **[!UICONTROL Recurring SMS]**: 根据 **[!UICONTROL Scheduler]** 活动中定义的频度，多次发送短信。选择发送的聚合期。这样，您可以将规定时间段内发生的所有发送重组到一封单独的视图中（也称为&#x200B;**定期执行**），并可从应用程序的营销活动列表访问该视图。

      例如，对于每天发送的定期生日短信，您可以选择聚合每月的发送。这样，尽管每天都会发送生日短信，但您可以按月接收投放报告。

1. 选择短信类型。短信类型来自在 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** 菜单中定义的短信模板。
1. 输入短信的常规属性。您还可以将其连接到现有营销策划。工作流投放活动的标签将更新为短信的标签。
1. 定义短信的内容。请参阅关于[创建短信](../../channels/using/creating-an-sms-message.md)的章节。
1. 默认情况下，**[!UICONTROL SMS delivery]** 活动不包含任何叫客过渡。如果要向 **[!UICONTROL SMS delivery]** 互动添加叫客过渡，请转到高级活动选项的 **[!UICONTROL General]** 选项卡（活动快捷操作中的 ![](assets/dlv_activity_params-24px.png) 按钮），然后选中以下选项之一：

   * **[!UICONTROL Add outbound transition without the population]**：通过此选项可生成叫客过渡，其中包含的群体与集客过渡完全相同。
   * **[!UICONTROL Add outbound transition with the population]**：通过此选项可生成叫客过渡，其中包含接收短信的群体。在投放准备期间被排除的目标成员（隔离、电话号码无效等）将从此过渡中排除。

1. 确认活动的配置并保存工作流。

重新打开活动时，您将直接转到短信仪表板。只能编辑其内容。

默认情况下，启动投放工作流只会触发消息准备。在工作流启动后，发送从工作流创建的消息，仍需要确认。但是在消息仪表板中，仅当通过工作流创建消息时，才能禁用 **[!UICONTROL Request confirmation before sending messages]** 选项。取消选中此选项后，消息在准备完成后即发送，不会进一步通知。

## 备注{#remarks}

可以在应用程序的营销活动列表中，访问在工作流中创建的投放。您可以使用仪表板查看工作流的执行状态。利用短信摘要窗格中的链接，可直接访问链接的元素（工作流、活动，如果是定期短信，还包括父投放）。

但是，默认情况下，定期投放的执行会被掩盖。要查看其详情，请勾选营销活动搜索面板中的 **[!UICONTROL Show recurring executions]** 选项。

在（可从营销活动列表访问，或直接通过关联的定期执行访问）父投放中，您可以查看已处理的发送总数（基于配置 **[!UICONTROL SMS delivery]** 活动时指定的聚合期）。要执行此操作，请通过选择 **[!UICONTROL Deployment]** 以打开父投放 ![](assets/wkf_dlv_detail_button.png) 块的详细视图。
