---
title: 直接邮递
seo-title: 直接邮递
description: 直接邮递
seo-description: “直接邮寄”活动允许您配置在工作流中发送单个发送直接邮寄邮件或重复发送的直接邮寄邮件。
page-status-flag: 从未激活
uuid: bfa7b176-a17c-4079-a073-64b8ce4788ed
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 渠道活动
discoiquuid: b9ddb2a0-54ff-4ada-be6f-8109fa06d461
context-tags: directMail，工作流，主
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ea825afe573959d95d0f7f3f6e79dd38ac5a678a

---


# 直接邮递{#direct-mail-delivery}

## 说明 {#description}

![](assets/paper.png)

![](assets/recurrentpaper.png)

该活 **[!UICONTROL Direct mail delivery]** 动允许您配置和准备包含要用于直接邮件营销活动的配置文件数据的文件。 这可以是一次性使用的直接邮寄邮件，也可以是一次 **性** 直接邮寄。

标准直接电子邮件发送一次。

重复邮件允许您在定义的时间段内多次向不同目标发送相同的直接邮件。 您可以汇总每个时段的交货数，以获得与您的需求对应的报表。

## 使用环境 {#context-of-use}

活 **[!UICONTROL Direct mail delivery]** 动通常用于自动准备包含配置文件数据的文件。 然后，可以将此文件发送给负责邮寄的合作伙伴／提供商。

链接到调度程序时，您可以定义重复的直接电子邮件。

直邮收件人通过查询、交叉点等定位活动在同一工作流中活动的上游进行定义。 准备直邮时，其邮寄地址未指定的配置文件将自动排除。

根据工作流执行参数触发消息准备。 在消息功能板中，您可以选择是否请求手动确认以发送消息（默认情况下为必需）。 您可以手动启动工作流，或将调度程序活动放入工作流中以自动执行。

## 配置 {#configuration}

1. 将活动拖放 **[!UICONTROL Direct mail delivery]** 到工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮将其打开。

   >[!NOTE]
   >
   >您可以通过活动快速操作中的按钮访问活动（而非交付本身）的 ![](assets/dlv_activity_params-24px.png) 常规属性和高级选项。 此按钮特定于渠道活动。 可通过直接邮件功能板中的操作栏访问直接邮件的属性。

1. 选择直邮发送模式：

   * **[!UICONTROL Direct mail]**:直邮只发一次。 您可以在此处指定是否要向活动添加出站过渡。 此过程的步骤7中详细介绍了不同的过渡类型。
   * **[!UICONTROL Recurring direct mail]**:根据活动中定义的频率，直邮会多次发送 **[!UICONTROL Scheduler]** 。 选择发送的聚合期。 这样，您就可以在一个称为“重复执行”的单个直接邮件中重新分组定义期间发生的所有发送，并可以从应用程序的营销活动列表中访问这些发送。 ****

      例如，对于每日处理的循环生日邮件，您可以选择每月汇总发送。 这样，尽管每天都会处理邮件，但您仍可以每月收到有关邮件发送的报告。

      >[!NOTE]
      >
      >对于重复的直接邮件，在工作流的每次执行时都会生成一个新文件。 所选的聚合期间对此行为没有影响。

1. 选择直邮类型。 直邮类型来自在 **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt;菜单中定义的 **[!UICONTROL Delivery templates]** 模板。
1. 输入直邮的常规属性。 您还可以将其附加到现有营销活动。 工作流的分发活动的标签将更新为直邮标签。
1. 定义直邮内容。 请参阅有关内容编辑 [的部分](../../designing/using/personalization.md)。
1. 默认情况下，活 **[!UICONTROL Direct mail delivery]** 动不包括任何出站过渡。 如果要向活动添加出站过渡，请转到高级活动选项的选 **[!UICONTROL Direct mail delivery]** 项卡( **[!UICONTROL General]**![](assets/dlv_activity_params-24px.png) 活动快速操作中的按钮)，然后选中以下选项之一：

   * **[!UICONTROL Add outbound transition without the population]**:这样，您就可以生成一个出站过渡，其中包含与入站过渡完全相同的人数。 此过渡包含由直接邮件活动生成的文件以及直接邮件活动收到的原始人口。
   * **[!UICONTROL Add outbound transition with the population]**:这样，您就可以生成一个出站过渡，其中包含将向其发送直接邮件的人群。 在准备直接邮件期间被排除的目标成员（隔离、无效地址等）将被排除在此过渡之外。 转换还包含由直邮生成的文件。

1. 确认活动的配置并保存工作流。

重新打开活动后，您会直接转到直邮功能板。 只能编辑其内容。

默认情况下，启动传送工作流只会触发消息准备。 在工作流启动后，仍需要确认从工作流创建的消息的发送。 但是，在消息功能板中，并且仅当消息是从工作流创建的时候，您才能禁用该选 **[!UICONTROL Request confirmation before sending messages]** 项。 取消选中此选项后，准备完成后，消息将发送，无需进一步通知。

## 评论 {#remarks}

在工作流中创建的交货可以在应用程序的营销活动列表中访问。 您可以使用功能板查看工作流的执行状态。 通过直邮摘要窗格中的链接，您可以直接访问链接的元素（如果是重复的直邮，则为工作流、营销活动、父分发）。

![](assets/wkf_display_parent_elements_direct_mail.png)

默认情况下，重复提交的执行被遮罩。 要查看它们，请选中 **[!UICONTROL Show recurring executions]** 营销活动搜索面板中的选项。

![](assets/wkf_display_recurrent_executions_direct_mail.png)

在可从营销活动列表访问或直接通过关联的重复执行访问的父提交中，您可以查看已处理的邮件总数（根据配置活动时指定的汇总期间）。 **[!UICONTROL Direct mail delivery]** 为此，请选择以打开父分发块的详细信 **[!UICONTROL Deployment]** 息视图 ![](assets/wkf_dlv_detail_button.png)。

![](assets/wkf_display_recurrent_executions_3_direct_mail.png)

## 示例 {#example}

“直邮” **[!UICONTROL Direct mail delivery]** 一章中提供 [了示例](../../channels/using/example-of-direct-mail-in-a-workflow.md) 。
