---
title: 短信投放
description: SMS投放活动允许您配置在工作流中发送单个发送SMS或重复的SMS。
page-status-flag: never-activated
uuid: 736078c6-ac91-4440-825b-4a6ae31894ef
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 978592b8-989a-446a-8a84-12b7fecfc130
context-tags: sms,main;delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 16afc307df6902584624d6457954a472b11c5129
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 0%

---


# 短信投放{#sms-delivery}

## 说明 {#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

该 **[!UICONTROL SMS delivery]** 活动允许您配置在工作流中发送SMS。 这可以是单 **个发送** SMS并只发送一次，也可以是重复 **的SMS** 。

单发短信是标准短信，只发一次。

重复的SMS消息允许您在定义的时间段内多次向不同目标发送相同的SMS。 您可以聚合每个时段的投放，以获得与您的需求对应的报告。

## 使用环境 {#context-of-use}

该 **[!UICONTROL SMS delivery]** 活动通常用于自动将SMS发送到在同一工作流中计算的目标。

当链接到调度程序时，您可以定义重复的SMS消息。

SMS收件人是在同一工作流中通过诸如查询、交叉点等定位活动在活动上游定义的。

根据工作流执行参数触发消息准备。 在消息仪表板中，您可以选择是否请求手动确认以发送消息（默认情况下为必需）。 您可以手动开始工作流，或在工作流中放置调度程序活动以自动执行。

## Configuration {#configuration}

1. 将活动拖放 **[!UICONTROL SMS delivery]** 到工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮打开它。

   >[!NOTE]
   >
   >您可以通过工作流操作栏中的按钮访问活动(而非投放本身)的 ![](assets/dlv_activity_params-24px.png) 常规属性和高级选项。 此按钮特定于 **[!UICONTROL SMS delivery]** 活动。 可以通过SMS仪表板中的操作栏访问SMS属性。

1. 选择SMS发送模式：

   * **[!UICONTROL SMS]**: 短信只发一次。 您可以在此处指定是否要向活动添加出站过渡。 不同的过渡类型在此过程的步骤7中详细介绍。
   * **[!UICONTROL Recurring SMS]**: 根据活动中定义的频率，短信被发送多次 **[!UICONTROL Scheduler]** 。 选择发送的聚合期间。 这允许您将定义期间发生的所有发送重新分组到一个视图中，该也称为“ **重复执行** ”，并可从应用程序的营销活动列表访问。

      例如，对于每天发送的循环生日SMS，您可以选择聚合每月发送的消息。 这样，尽管每天都会发送SMS，您仍可以每月接收投放报告。

1. 选择SMS类型。 SMS类型来自在> >菜单中定义的 **[!UICONTROL Resources]** SMS **[!UICONTROL Templates]** 模 **[!UICONTROL Delivery templates]** 板。
1. 输入SMS的常规属性。 您还可以将其附加到现有活动。 工作流的投放活动的标签将更新为SMS标签。
1. 定义SMS内容。 请参阅有关创建 [SMS消息的部分](../../channels/using/creating-an-sms-message.md)。
1. 默认情况下， **[!UICONTROL SMS delivery]** 活动不包含任何出站过渡。 如果要向过渡添加出站活动，请转 **[!UICONTROL SMS delivery]** 到高级活动 **[!UICONTROL General]** 选项的选项卡( ![](assets/dlv_activity_params-24px.png) 活动快速操作中的按钮)，然后选中以下选项之一：

   * **[!UICONTROL Add outbound transition without the population]**: 这样，您就可以生成一个出站过渡，其包含与入站过渡完全相同的人口。
   * **[!UICONTROL Add outbound transition with the population]**: 这样，您就可以生成一个出站过渡，其中包含发送SMS的人群。 在准备目标时排除的投放成员(隔离、无效编号等) 排除在此过渡。

1. 确认活动的配置并保存工作流。

重新打开活动时，将直接转到SMS仪表板。 只能编辑其内容。

默认情况下，启动投放工作流只会触发消息准备。 在工作流启动后，仍需要确认从工作流创建的消息的发送。 但是，从消息仪表板中，并且仅当消息是通过工作流创建的，您才能禁用该 **[!UICONTROL Request confirmation before sending messages]** 选项。 取消选中此选项后，消息在准备完成后即发送，无需进一步通知。

## 备注 {#remarks}

在工作流中创建的投放可以在应用程序的营销活动列表中访问。 您可以使用视图仪表板来工作流的执行状态。 SMS摘要窗格中的链接允许您直接访问链接的元素(如果出现重复的SMS，则为工作流、活动、父投放)。

但是，默认情况下，重复投放的执行会被遮罩。 要对其进行视图，请选 **[!UICONTROL Show recurring executions]** 中营销活动搜索面板中的选项。

在父投放中(可从营销活动列表访问，或直接通过关联的重复执行访问)，您可以视图已处理的发送总数(根据配置活动时指定的汇总期 **[!UICONTROL SMS delivery]** 间)。 为此，请通过选择打开父投放块的详细 **[!UICONTROL Deployment]** 视图 ![](assets/wkf_dlv_detail_button.png)。
