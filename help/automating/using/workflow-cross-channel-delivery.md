---
title: “工作流用例： 跨渠道投放”
description: “工作流用例： 跨渠道投放”
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,wait,delivery
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# 工作流用例： 创建跨渠道投放{#cross-channel-delivery}

此文档允许您通过标准用例发现以下Adobe Campaign功能： 创建跨渠道投放工作流。

此处的目标是从受众库的收件人中选择一个，并将其分段为两个不同的组，以便向第一组发送电子邮件，向第二组发送SMS消息。

![](assets/wkf_segment_overview.png)

有关工作流和Adobe Campaign中可用的不同渠道的更多详细信息，请查看以下文档:

* [了解工作流](../../automating/using/get-started-workflows.md)
* [了解通信渠道](../../channels/using/get-started-communication-channels.md)

## 创建工作流 {#creating-workflow}

要将两个不同的投放发送给给定的组，您必须先定义目标。

为此，您需要创建查询来标识收件人，因此，您必须创建工作流。

在您选择的项目或活动中创建新工作流：

1. 在中 **[!UICONTROL Marketing Activities]**，单击 **[!UICONTROL Create]** 并选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]** 为工作流类型并单击 **[!UICONTROL Next]**。
1. 输入工作流的属性并单击 **[!UICONTROL Create]**。

创建工作流的详细步骤在构建工作流 [部分中介绍](../../automating/using/building-a-workflow.md) 。

## 创建查询活动 {#creating-query-activity}

创建工作流后，您可以访问其界面。

将查询活动插入您的工作流，以目标将接收您的投放的用户档案。

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**&#x200B;中，拖放 **[!UICONTROL Query activity]**。
1. 多次单击活动。
1. 在选项卡 **[!UICONTROL Target]** 中，浏览快捷键并选择您的受众 [之一](../../audiences/using/about-audiences.md)。
1. 将快捷方式拖放到编辑区域。 根据所选快捷键的类型，将显示一个窗口。
1. 配置定位元素，然后确认您的查询。

![](assets/wkf_segment_query.png)

可以对一个或多个元素创建查询。

使用 **[!UICONTROL Count]** 该按钮可以查看查询目标的用户档案数估计。

构建查询活动的详细步骤在“查询” [部分](../../automating/using/query.md) 。

## 创建分段活动 {#creating-segmentation-activity}

一旦目标由查询活动识别，您必须选择一个标准将目标分为两个不同的群体： 一个会收到一封电子邮件，另一个会收到一条短信。

您必须使用分段活动，从查询上游计算的人群创建一个或多个区段。

![](assets/wkf_segment_activity.png)

电子 **邮件组** 将目标定义了电子邮件地址但没有移动电话号码的收件人。 SMS **组将包** 含其移动电话号码保存在其用户档案中的收件人。

配置第一个过渡（电子邮件）:

1. 在选项 **[!UICONTROL Segments]** 卡中，默认情况下存在第一个区段。 编辑其属性以配置该区段。

   ![](assets/wkf_segment_properties.png)

1. 选择用户档案 **[!UICONTROL Email]** 作为筛选标准。

   ![](assets/wkf_segment_email.png)

1. 在屏幕上显示的新窗口中，选择运算 **[!UICONTROL Is not empty]** 符。

   ![](assets/wkf_segment_email_not_empty.png)

1. 添加第二个筛选条 **[!UICONTROL Mobile]**&#x200B;件，然后选择运算符 **[!UICONTROL Is empty]**。

   ![](assets/wkf_segment_mobile_empty.png)

   来自查询的所有用户档案都将包含电子邮件，但未定义移动电话号码。

1. 要使工作流程更清晰，您可以编辑过渡标签。 确认更改。

   ![](assets/wkf_segment_transition_label.png)

您的第一个过渡已配置。 配置第二个过渡(SMS):

1. 单击按 **[!UICONTROL Add an element]** 钮以添加新过渡。
1. 定义一个条件，允许您检索其手机号码已提供的所有用户档案。 为此，请使用逻辑运算符在字 **[!UICONTROL Mobile]** 段上创建 **[!UICONTROL Is not empty]** 规则。

   ![](assets/wkf_segment_mobile_not_empty.png)

   来自定义了移动电话号码的查询的所有用户档案都将在此过渡中。

1. 您可以编辑过渡的标签。 确认更改。

您的第二个过渡现在也已配置。

![](assets/wkf_segment_transitions.png)

构建分段活动的详细步骤在分段部分 [中介绍](../../automating/using/segmentation.md) 。

## 创建投放 {#creating-deliveries}

由于已创建两个过渡，您现在必须向分段活动的出站过渡添加两种类型的投放: 一 **[!UICONTROL Email delivery]** 个 **[!UICONTROL SMS delivery]**。

Adobe Campaign允许您向工作流中添加投放。 为此，请从工作流的投放 **[!UICONTROL Channels]** 面板的类别中选择一个活动。

![](assets/wkf_segment_deliveries1.png)

要创建电子邮件投放，请执行以下操作：

1. 在第一个区段 **[!UICONTROL Email delivery]** 后拖放一个。
1. 多次-单击活动进行编辑。
1. Select **[!UICONTROL Simple email]**.
1. 选择 **[!UICONTROL Add an outbound transition with the population]** 并单击 **[!UICONTROL Next]**。

   ![](assets/wkf_segment_deliveries2.png)

   出站过渡将允许您恢复人口和跟踪日志。 例如，您将能够使用它向未点击第一封邮件的用户发送第二封邮件。

1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件布局，请选择 **[!UICONTROL Use the Email Designer]**。
1. 编辑和保存您的内容。
1. 在消 **[!UICONTROL Schedule]** 息仪表板的一节中，在发送消 **息之前取消选择[!UICONTROL请求确认** 。

构建电子邮件活动的详细步骤会在“电子邮件 [投放](../../automating/using/email-delivery.md) ”部分。

创建SMS投放:

1. 拖放另一个 **[!UICONTROL SMS delivery]** 区段之后。
1. 多次-单击活动进行编辑。
1. 选择 **[!UICONTROL SMS]** 并单击 **[!UICONTROL Next]**。
1. 选择SMS模板并单击 **[!UICONTROL Next]**。
1. 输入SMS属性并单击 **[!UICONTROL Next]**。
1. 编辑和保存您的内容。

构建SMS活动的详细步骤在SMS投放 [部分中介绍](../../automating/using/sms-delivery.md) 。

创建和编辑投放后，工作流即可开始。

![](assets/wkf_segment_deliveries.png)

## 运行工作流 {#running-the-workflow}

启动工作流后，查询活动所针对的人群将被分段，以接收电子邮件或短信投放。

要执行工作流，请单 **[!UICONTROL Start]** 击操作栏中的按钮。

您可以通过“投放”徽标 **[!UICONTROL Marketing plans]** 从“ **[!UICONTROL Marketing activities]** 高级”菜单访问Adobe Campaign。 单击投放，然 **[!UICONTROL Reports]** 后单击按钮以访 [问投放报告](../../reporting/using/about-dynamic-reports.md#accessing-dynamic-reports)，如投放摘要、打开率或根据收件人邮件收件箱显示电子邮件。