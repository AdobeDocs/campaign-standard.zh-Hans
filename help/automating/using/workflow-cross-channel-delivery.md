---
title: 跨渠道投放
description: 此用例说明如何创建跨渠道投放
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,wait,delivery
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 86%

---


# 创建跨渠道投放{#cross-channel-delivery}

本文档介绍了如何通过标准使用案例了解以下 Adobe Campaign 功能：创建跨渠道投放工作流。

本使用案例的目标是从数据库的收件人中选择受众，并将其划分为两个不同的组，以便向第一组发送电子邮件，向第二组发送短信消息。

![](assets/wkf_segment_overview.png)

有关 Adobe Campaign 可用的工作流和各种渠道的更多详细信息，请参见以下文档:

* [了解工作流](../../automating/using/get-started-workflows.md)
* [了解通信渠道](../../channels/using/get-started-communication-channels.md)

## 创建工作流{#creating-workflow}

要将两个不同的投放发送至给定的组，您必须先定义目标。

要实现此目的，您需要创建查询以标识收件人，因此，您必须创建工作流。

在选择的项目或营销策划中创建新工作流：

1. 在 **[!UICONTROL Marketing Activities]** 中，单击 **[!UICONTROL Create]** 并选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]** 作为工作流类型并单击 **[!UICONTROL Next]**。
1. 输入工作流的属性并单击 **[!UICONTROL Create]**。

有关创建工作流的详细步骤，请参阅[构建工作流](../../automating/using/building-a-workflow.md)一节。

## 创建查询活动{#creating-query-activity}

创建工作流后，即可访问其界面。

将查询活动插入您的工作流，以定向接收投放的用户档案。

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** 中，拖放[查询](../../automating/using/query.md)活动。
1. 双击该活动。
1. 在 **[!UICONTROL Target]** 选项卡中，浏览快捷方式并选择您的[受众](../../audiences/using/about-audiences.md)之一。
1. 将快捷方式拖放到编辑区域中。随即将根据所选快捷方式的类型，显示一个窗口。
1. 配置定向元素，然后确认查询。

![](assets/wkf_segment_query.png)

您可以基于一个或多个元素创建查询。

使用 **[!UICONTROL Count]** 该按钮可查看通过查询定向之用户档案数量的估算值。

## 创建分段活动{#creating-segmentation-activity}

一旦通过查询活动标识了目标，您就必须选择条件以将目标分为两个不同的群体：一个接收电子邮件，另一个接收短信。

You have to use a [Segmentation](../../automating/using/segmentation.md) activity to create one or several segments from a population computed upstream in a query.

![](assets/wkf_segment_activity.png)

**电子邮件**&#x200B;组的目标是定义了电子邮件地址但没有手机号码的收件人。**短信**&#x200B;组则包含其用户档案中保存了手机号码的收件人。

要配置第一个过渡（电子邮件），请执行以下步骤：

1. 在 **[!UICONTROL Segments]** 选项卡中，默认显示第一个区段。编辑其属性以配置该区段。

   ![](assets/wkf_segment_properties.png)

1. 选择用户档案的 **[!UICONTROL Email]** 作为筛选条件。

   ![](assets/wkf_segment_email.png)

1. 在屏幕上显示的新窗口中，选择 **[!UICONTROL Is not empty]** 运算符。

   ![](assets/wkf_segment_email_not_empty.png)

1. 添加第二个筛选条件 **[!UICONTROL Mobile]**，然后选择运算符 **[!UICONTROL Is empty]**。

   ![](assets/wkf_segment_mobile_empty.png)

   所有来自查询的、拥有电子邮件地址但未定义手机号码的用户档案，都将被纳入到此过渡中。

1. 要使工作流程更清晰，您可以编辑过渡标签。确认更改。

   ![](assets/wkf_segment_transition_label.png)

第一个过渡配置完成。配置第二个过渡（短信）：

1. 单击 **[!UICONTROL Add an element]** 按钮以添加一个新过渡。
1. 定义一个条件，用于检索提供了手机号码的所有用户档案。要实现此目的，请使用 **[!UICONTROL Is not empty]** 逻辑运算符在 **[!UICONTROL Mobile]** 字段上创建规则。

   ![](assets/wkf_segment_mobile_not_empty.png)

   来自查询的、所有拥有手机号码的用户档案，都将被纳入到此过渡中。

1. 您可以编辑过渡的标签。确认更改。

第二个过渡配置完成。

![](assets/wkf_segment_transitions.png)

## 创建投放{#creating-deliveries}

As two transitions were already created, you must now add two types of deliveries to the outbound transitions of the Segmentation activity: an [Email delivery](../../automating/using/email-delivery.md) activity and an [SMS delivery](../../automating/using/sms-delivery.md) activity.

利用 Adobe Campaign 可向工作流中添加投放。要实现此目的，请从工作流活动面板的 **[!UICONTROL Channels]** 类别中选择一个投放。

![](assets/wkf_segment_deliveries1.png)

要创建电子邮件投放，请执行以下步骤：

1. 将电子邮件投放 [活动拖](../../automating/using/email-delivery.md) 放到第一个区段之后。
1. 双击该活动以对其进行编辑。
1. 选择 **[!UICONTROL Simple email]**。
1. 选择 **[!UICONTROL Add an outbound transition with the population]** 并单击 **[!UICONTROL Next]**。

   ![](assets/wkf_segment_deliveries2.png)

   利用叫客过渡，可取回群体和跟踪日志。例如，您将能够使用叫客过渡向未点击第一封邮件的用户发送第二封邮件。

1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件的布局，请选择 **[!UICONTROL Use the Email Designer]**。
1. 编辑并保存您的内容。
1. In the **[!UICONTROL Schedule]** section of the message dashboard, unselect the **[!UICONTROL Request confirmation before sending messages]** option.

创建短信投放：

1. 将SMS投放 [活动拖放](../../automating/using/sms-delivery.md) 到另一段之后。
1. 双击该活动以对其进行编辑。
1. 选择 **[!UICONTROL SMS]** 并单击 **[!UICONTROL Next]**。
1. 选择短信模板并单击 **[!UICONTROL Next]**。
1. 输入短信属性并单击 **[!UICONTROL Next]**。
1. 编辑并保存您的内容。

创建并编辑投放后，工作流即准备就绪，可以启动。

![](assets/wkf_segment_deliveries.png)

## 运行工作流{#running-the-workflow}

Once the workflow is started, the population targeted by the **[!UICONTROL Query]** activity will be segmented to receive an Email or SMS delivery.

要执行工作流，请单击操作栏中的 **[!UICONTROL Start]** 按钮。

您可以通过 Adobe Campaign 徽标访问 **[!UICONTROL Marketing plans]** > **[!UICONTROL Marketing activities]** 高级菜单，以访问相关投放。单击投放，然后单击 **[!UICONTROL Reports]** 按钮以访问[投放报告](../../reporting/using/about-dynamic-reports.md#accessing-dynamic-reports)，例如投放摘要、打开率或基于收件人消息收件箱的电子邮件渲染。
