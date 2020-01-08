---
title: “工作流用例：跨渠道交付”
description: “工作流用例：跨渠道交付”
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
source-git-commit: f959441647d1fea41ecce2fc41e3cad3cb536bac

---


# 工作流用例：创建跨渠道交付{#cross-channel-delivery}

本文档允许您通过标准用例发现以下Adobe Campaign功能：创建跨渠道交付工作流。

此处的目标是从数据库的接收者中选择受众并将其细分为两个不同的组，以便向第一组发送电子邮件，向第二组发送SMS消息。

![](assets/wkf_segment_overview.png)

有关Adobe Campaign中可用的工作流和不同渠道的更多详细信息，请检查以下文档：

* [了解工作流](../../automating/using/discovering-workflows.md)
* [了解通信渠道](../../channels/using/discovering-communication-channels.md)

## 创建工作流 {#creating-workflow}

要向给定组发送两个不同的提交，您必须先定义目标。

为此，您需要创建查询以标识收件人，因此，您必须创建工作流。

在计划或您选择的营销活动中创建新的工作流：

1. 在中， **[!UICONTROL Marketing Activities]**单击并**[!UICONTROL Create]** 选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]**为工作流类型，然后单击**[!UICONTROL Next]**。
1. 输入工作流的属性，然后单击 **[!UICONTROL Create]**。

创建工作流的详细步骤在构建工作流 [部分中介绍](../../automating/using/building-a-workflow.md) 。

## 创建查询活动 {#creating-query-activity}

创建工作流后，您便可以访问其界面。

在工作流中插入查询活动，以定位将接收您的提交的配置文件。

1. 在 **[!UICONTROL Activities]**>**[!UICONTROL Targeting]**&#x200B;中，拖放 **[!UICONTROL Query activity]**。
1. 双击活动。
1. 在选项卡 **[!UICONTROL Target]**中，浏览快捷键并选择您的某个受[众](../../audiences/using/about-audiences.md)。
1. 将快捷键拖放到编辑区域。 根据所选快捷键的类型，将显示一个窗口。
1. 配置定位元素，然后确认查询。

![](assets/wkf_segment_query.png)

可以对一个或多个元素创建查询。

使用 **[!UICONTROL Count]**按钮可查看查询所定位的配置文件数的估计。

“查询”部分显示了构建查询活动的详细 [步骤](../../automating/using/query.md) 。

## 创建分段活动 {#creating-segmentation-activity}

在查询活动识别目标后，您必须选择一个标准来将目标细分为两个不同的人群：一个会收到一封电子邮件，另一个会收到一条短信。

您必须使用分段活动从查询上游计算的人群创建一个或多个区段。

![](assets/wkf_segment_activity.png)

“电 **子邮件** ”组将以定义了电子邮件地址但没有移动电话号码的收件人为目标。 SMS **** 组将包含其手机号码保存在其配置文件中的收件人。

要配置第一次过渡（电子邮件），请执行以下操作：

1. 在选项 **[!UICONTROL Segments]**卡中，默认情况下存在第一个区段。 编辑其属性以配置该区段。

   ![](assets/wkf_segment_properties.png)

1. 选择配置文件 **[!UICONTROL Email]**作为筛选标准。

   ![](assets/wkf_segment_email.png)

1. 在屏幕上出现的新窗口中，选择运算 **[!UICONTROL Is not empty]**符。

   ![](assets/wkf_segment_email_not_empty.png)

1. 添加第二个过滤标准， **[!UICONTROL Mobile]**然后选择运算符**[!UICONTROL Is empty]**。

   ![](assets/wkf_segment_mobile_empty.png)

   来自查询的所有配置文件都将处于此过渡阶段，这些配置文件包含电子邮件，但未定义移动电话号码。

1. 要使工作流程更清晰，您可以编辑过渡标签。 确认更改。

   ![](assets/wkf_segment_transition_label.png)

您的第一个过渡已配置好。 要配置第二个过渡(SMS)，请执行以下操作：

1. 单击该 **[!UICONTROL Add an element]**按钮可添加新过渡。
1. 定义一个条件，允许您检索其手机号码已提供的所有配置文件。 为此，请使用逻辑运算符在字 **[!UICONTROL Mobile]**段上创建**[!UICONTROL Is not empty]** 规则。

   ![](assets/wkf_segment_mobile_not_empty.png)

   来自查询且定义了移动电话号码的所有配置文件都将处于此转换中。

1. 您可以编辑过渡的标签。 确认更改。

您的第二个过渡现在也已配置好。

![](assets/wkf_segment_transitions.png)

“分段”部分介绍了构建分段活动的详细 [步骤](../../automating/using/segmentation.md) 。

## 创建提交 {#creating-deliveries}

由于已创建两个过渡，您现在必须向分段活动的出站过渡添加两种类型的提交：一个 **[!UICONTROL Email delivery]**和一个**[!UICONTROL SMS delivery]**。

Adobe Campaign允许您向工作流中添加分发。 为此，请从工作流活动调板 **[!UICONTROL Channels]**的类别中选择分发。

![](assets/wkf_segment_deliveries1.png)

要创建电子邮件分发，请执行以下操作：

1. 在第一个区段 **[!UICONTROL Email delivery]**后拖放一个。
1. 双击活动以对其进行编辑。
1. Select **[!UICONTROL Simple email]**.
1. 选择 **[!UICONTROL Add an outbound transition with the population]**并单击**[!UICONTROL Next]**。

   ![](assets/wkf_segment_deliveries2.png)

   出站过渡将允许您恢复人口和跟踪日志。 例如，您将能够使用它向未点击第一封邮件的用户发送第二封邮件。

1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件布局，请选择 **[!UICONTROL Use the Email Designer]**。
1. 编辑和保存您的内容。
1. 在消 **[!UICONTROL Schedule]**息功能板的部分中，取消选择**[!UICONTROL请求确认，然后发送消息}**。

构建电子邮件活动的详细步骤在电子邮件分发部 [分中介绍](../../automating/using/email-delivery.md) 。

创建SMS交付：

1. 在另一个区段 **[!UICONTROL SMS delivery]**后拖放一个。
1. 双击活动以对其进行编辑。
1. 选择 **[!UICONTROL SMS]**并单击**[!UICONTROL Next]**。
1. 选择SMS模板，然后单击 **[!UICONTROL Next]**。
1. 输入SMS属性，然后单击 **[!UICONTROL Next]**。
1. 编辑和保存您的内容。

构建SMS活动的详细步骤在 [SMS交付部分中介绍](../../automating/using/sms-delivery.md) 。

在创建和编辑您的提交后，您的工作流即可开始。

![](assets/wkf_segment_deliveries.png)

## 运行工作流 {#running-the-workflow}

启动工作流后，查询活动所定位的人群将被分段，以接收电子邮件或短信发送。

要执行工作流，请单击操 **[!UICONTROL Start]**作栏中的按钮。

您可以通过Adobe Campaign徽标从 **[!UICONTROL Marketing plans]**>高**[!UICONTROL Marketing activities]** 级菜单访问您的分发。 单击传送，然 **[!UICONTROL Reports]**后单击按钮以访问传送报[告](../../reporting/using/about-dynamic-reports.md#accessing-dynamic-reports)，如传送摘要、打开率或根据收件人的邮件收件箱显示电子邮件。