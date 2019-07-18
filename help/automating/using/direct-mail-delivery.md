---
title: 直接邮寄邮件
seo-title: 直接邮寄邮件
description: 直接邮寄邮件
seo-description: 通过直接邮件交付活动，您可以配置在工作流中发送单个发送直接邮件或重复的直接邮件。
page-status-flag: 从未激活
uuid: bfa7b176-a17 c-4079-a073-64b8 ce4788
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 渠道活动
discoiquuid: b9ddb2a0-54ff-4ada-be6 f-8109fa06 d461
context-tags: DirectMail，工作流程，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Direct mail delivery{#direct-mail-delivery}

## Description {#description}

![](assets/paper.png)

![](assets/recurrentpaper.png)

**[!UICONTROL Direct mail delivery]** 活动允许您配置和准备包含配置文件数据的文件，这些数据要用于直接邮寄活动。This can be a direct mail that is used just once, or it can be a **recurring** direct mail.

标准直接邮寄只发送一次。

重复的邮件允许您在定义的时间段内将相同的直接邮寄邮件发送到不同的目标。您可以将分发汇总为每个时段，以获得符合您的需求的报表。

## Context of use {#context-of-use}

**[!UICONTROL Direct mail delivery]** 该活动通常用于自动准备包含配置文件数据的文件。然后，可以将此文件发送给负责邮寄的合作伙伴/提供商。

链接到计划程序时，您可以定义重复的直接邮件。

直接邮寄收件人通过诸如查询、交叉点等定位活动在同一工作流程中定义活动上游。准备直邮时会自动排除邮件地址未指定的配置文件。

消息准备会根据工作流执行参数触发。在消息仪表板中，您可以选择是请求还是不需要手动确认发送消息(默认情况下需要)。您可以手动启动工作流或在工作流中放置调度程序活动以自动执行执行。

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Direct mail delivery]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   >[!NOTE]
   >
   >You can access the general properties and advanced options of the activity (and not of the delivery itself) via the ![](assets/dlv_activity_params-24px.png) button from the activity's quick actions. 此按钮特定于渠道活动。直接邮件的属性可通过直邮仪表板中的操作栏进行访问。

1. 选择直接邮件发送模式：

   * **[!UICONTROL Direct mail]**：直接邮寄邮件。您可以在此处指定是否要为活动添加出站过渡。此过程的步骤中详细介绍了不同的过渡类型。
   * **[!UICONTROL Recurring direct mail]**：直接邮件会根据 **[!UICONTROL Scheduler]** 活动中定义的频率多次发送。选择发送的汇总时间。This allows you to regroup all the sends that occur during the defined period in one single direct mail that is also called **Recurring execution** and can be accessed from the application's marketing activity list.

      例如，对于每天处理的重复生日邮件，您可以选择将发送汇总每个月。这允许您按月接收报告，但每天只能处理邮件。

      >[!NOTE]
      >
      >对于重复的直接邮件，在工作流的每个执行过程中都会生成一个新文件。选定的汇总时间段对此行为没有影响。

1. 选择直接邮寄类型。The direct mail types come from templates defined in the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** menu.
1. 输入直接邮件的常规属性。您还可以将其附加到现有营销活动。工作流的交付活动的标签使用直接邮件标签进行更新。
1. 定义直接邮件内容。Refer to the section concerning [content editing](../../designing/using/about-personalization.md).
1. By default, the **[!UICONTROL Direct mail delivery]** activity does not include any outbound transitions. If you would like to add an outbound transition to your **[!UICONTROL Direct mail delivery]** activity, go to the **[!UICONTROL General]** tab of the advanced activity options ( ![](assets/dlv_activity_params-24px.png) button in the activity's quick actions) then check one of the following options:

   * **[!UICONTROL Add outbound transition without the population]**：这使您能够生成包含与入站过渡相同的相同人群的出站过渡。此过渡包含由直接邮件活动和直接邮件活动收到的原始数据源生成的文件。
   * **[!UICONTROL Add outbound transition with the population]**：这允许您生成包含直接邮寄邮件人群的出站过渡。直接邮件准备过程中排除的目标成员(隔离、无效地址等)已排除在此过渡中。过渡还包含由直接邮件生成的文件。

1. 确认活动的配置并保存工作流。

重新打开活动时，您直接被转至直邮仪表板。只能编辑其内容。

默认情况下，启动交付工作流只会触发消息准备。在启动工作流之后，仍需要确认从工作流创建的消息的发送。But from the message dashboard, and only if the message was created from a workflow, you can disable the **[!UICONTROL Request confirmation before sending messages]** option. 通过取消选中此选项，准备完成后无需进一步通知即可发送消息。

## Remarks {#remarks}

在工作流中创建的分发可以在应用程序的营销活动列表中访问。您可以使用仪表板查看工作流的执行状态。直接邮件摘要窗格中的链接允许您直接访问链接元素(工作流、营销活动、父交付情况，以出现重复的直接邮件)。

![](assets/wkf_display_parent_elements_direct_mail.png)

默认情况下将遮罩重复分发的执行。To view them, check the **[!UICONTROL Show recurring executions]** option in the marketing activities' search panel.

![](assets/wkf_display_recurrent_executions_direct_mail.png)

In the parent deliveries, which can be accessed from the marketing activity list or directly via the associated recurring executions, you can view the total number of mails that have been processed (according to the aggregation period specified when the **[!UICONTROL Direct mail delivery]** activity was configured). To do this, open the detail view of the parent delivery's **[!UICONTROL Deployment]** block by selecting ![](assets/wkf_dlv_detail_button.png).

![](assets/wkf_display_recurrent_executions_3_direct_mail.png)

## Example {#example}

**[!UICONTROL Direct mail delivery]**[直接邮件](../../channels/using/example-of-direct-mail-in-a-workflow.md) 一章提供了一个示例。
