---
title: 直邮投放
description: 直接邮件投放活动允许您配置在工作流中发送单个发送直接邮件或循环直接邮件。
page-status-flag: never-activated
uuid: bfa7b176-a17c-4079-a073-64b8ce4788ed
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: b9ddb2a0-54ff-4ada-be6f-8109fa06d461
context-tags: directMail,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 1%

---


# 直邮投放{#direct-mail-delivery}

## 说明 {#description}

![](assets/paper.png)

![](assets/recurrentpaper.png)

活动 **[!UICONTROL Direct mail delivery]** 允许您配置和准备包含要用于直接邮件活动的用户档案数据的文件。 这可以是一次性使用的直接邮寄邮件，也可以是一次 **性** 直接邮寄。

标准直接电子邮件发送一次。

循环邮件允许您在定义的时间段内多次向不同目标发送相同的直邮。 您可以聚合每个时段的投放，以获得与您的需求对应的报告。

## 使用环境 {#context-of-use}

活动 **[!UICONTROL Direct mail delivery]** 通常用于自动准备包含用户档案数据的文件。 然后，可以将此文件发送给负责邮寄的合作伙伴／提供商。

链接到调度程序后，您可以定义重复的直接电子邮件。

直接邮件收件人是在同一工作流中通过定位活动(如查询、交叉点等)在活动上游定义的。 准备直邮时，未指定邮寄地址的用户档案将自动排除。

根据工作流执行参数触发消息准备。 在消息仪表板中，您可以选择是否请求手动确认以发送消息（默认情况下为必需）。 您可以手动开始工作流，或在工作流中放置调度程序活动以自动执行。

**相关主题：**

* [用例： 将电子邮件和直邮投放](../../automating/using/coupling-email-direct-mail.md)
* [关于直邮](../../channels/using/about-direct-mail.md)

## Configuration {#configuration}

1. 将活动拖放 **[!UICONTROL Direct mail delivery]** 到工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮打开它。

   >[!NOTE]
   >
   >您可以通过活动快速操作中的按钮访问投放(而非活动本身)的常规属 ![](assets/dlv_activity_params-24px.png) 性和高级选项。 此按钮特定于渠道活动。 可以通过直接邮件仪表板中的操作栏访问直接邮件的属性。

1. 选择直邮发送模式：

   * **[!UICONTROL Direct mail]**: 直邮只发一次。 您可以在此处指定是否要向活动添加出站过渡。 不同的过渡类型在此过程的步骤7中详细介绍。
   * **[!UICONTROL Recurring direct mail]**: 根据活动中定义的频率，直接邮件会发送多次 **[!UICONTROL Scheduler]** 。 选择发送的聚合期间。 这样，您就可以重新分组在一个直接邮件（也称为“重复执行”）中定义的时间段内发 **送的所有** ，并可以从应用程序的营销活动列表进行访问。

      例如，对于每日处理的循环生日邮件，您可以选择聚合每月发送的邮件。 这样，尽管每天都会处理邮件，但您仍可以按月收到投放报告。

      >[!NOTE]
      >
      >对于重复的直接邮件，在工作流的每次执行时都会生成一个新文件。 所选的聚合期间对此行为没有影响。

1. 选择直接邮件类型。 直接邮件类型来自在> >菜单中定 **[!UICONTROL Resources]** 义 **[!UICONTROL Templates]** 的 **[!UICONTROL Delivery templates]** 模板。
1. 输入直邮的常规属性。 您还可以将其附加到现有活动。 工作流的投放活动的标签将更新为直接邮件标签。
1. 定义直邮内容。 请参阅有关内容编 [辑的部分](../../designing/using/personalization.md)。
1. 默认情况下， **[!UICONTROL Direct mail delivery]** 活动不包含任何出站过渡。 如果要向过渡添加出站活动，请转 **[!UICONTROL Direct mail delivery]** 到高级活动 **[!UICONTROL General]** 选项的选项卡( ![](assets/dlv_activity_params-24px.png) 活动快速操作中的按钮)，然后选中以下选项之一：

   * **[!UICONTROL Add outbound transition without the population]**: 这样，您就可以生成一个出站过渡，其包含与入站过渡完全相同的人口。 此过渡包含直接邮件活动生成的文件以及直接邮件活动接收的原始数据。
   * **[!UICONTROL Add outbound transition with the population]**: 这样，您就可以生成一个出站过渡，其中包含将向其发送直接邮件的人口。 直接邮件准备过程中排除的目标成员(隔离、无效地址等) 排除在此过渡。 该过渡还包含由直邮生成的文件。

1. 确认活动的配置并保存工作流。

重新打开活动时，您将直接转到直接邮寄仪表板。 只能编辑其内容。

默认情况下，启动投放工作流只会触发消息准备。 在工作流启动后，仍需要确认从工作流创建的消息的发送。 但是，从消息仪表板中，并且仅当消息是通过工作流创建的，您才能禁用该 **[!UICONTROL Request confirmation before sending messages]** 选项。 取消选中此选项后，消息在准备完成后即发送，无需进一步通知。

## 备注 {#remarks}

在工作流中创建的投放可以在应用程序的营销活动列表中访问。 您可以使用视图仪表板来工作流的执行状态。 直接邮寄摘要窗格中的链接允许您直接访问链接的元素(如果出现重复的直接邮寄，工作流、活动、父投放)。

![](assets/wkf_display_parent_elements_direct_mail.png)

默认情况下，重复投放的执行被遮罩。 要对其进行视图，请选 **[!UICONTROL Show recurring executions]** 中营销活动搜索面板中的选项。

![](assets/wkf_display_recurrent_executions_direct_mail.png)

在父投放中(可从营销活动列表访问，或直接通过关联的重复执行访问)，您可以视图已处理的邮件总数(根据配置活动时指定的汇总 **[!UICONTROL Direct mail delivery]** 期间)。 为此，请通过选择按钮打开父投放块 **[!UICONTROL Deployment]** 的详细视图 ![](assets/wkf_dlv_detail_button.png) 符。

![](assets/wkf_display_recurrent_executions_3_direct_mail.png)
