---
title: 短信投放
description: SMS交付活动允许您配置在工作流中发送单个发送SMS或重复的SMS。
page-status-flag: 从未激活
uuid: 736078c6-ac91-4440-825b-4a6ae31894ef
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 渠道活动
discoiquuid: 978592b8-989a-446a-8a84-12b7fecfc130
context-tags: sms,main；交付，sms内容，返回
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 短信投放{#sms-delivery}

## 说明 {#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

该 **[!UICONTROL SMS delivery]** 活动允许您配置在工作流中发送SMS。 这可以是单 **发SMS** ，只发送一次，也可以是重复 **的** SMS。

单发短信是标准短信，只发一次。

重复的SMS消息允许您在定义的时间段内多次向不同目标发送相同的SMS。 您可以汇总每个时段的交货数，以获得与您的需求对应的报表。

## 使用环境 {#context-of-use}

该活 **[!UICONTROL SMS delivery]** 动通常用于自动将SMS发送到在同一工作流中计算的目标。

当链接到调度程序时，您可以定义重复的SMS消息。

SMS收件人是通过诸如查询、交叉点等定位活动在同一工作流中活动的上游定义的。

根据工作流执行参数触发消息准备。 在消息功能板中，您可以选择是否请求手动确认以发送消息（默认情况下为必需）。 您可以手动启动工作流，或将调度程序活动放入工作流中以自动执行。

## 配置 {#configuration}

1. 将活动拖放 **[!UICONTROL SMS delivery]** 到工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮将其打开。

   >[!NOTE]
   >
   >您可以通过工作流操作栏中的按钮访问活动（而非交付本身）的 ![](assets/dlv_activity_params-24px.png) 常规属性和高级选项。 此按钮特定于活 **[!UICONTROL SMS delivery]** 动。 SMS属性可以通过SMS仪表板中的操作栏访问。

1. 选择SMS发送模式：

   * **[!UICONTROL SMS]**:短信只发送一次。 您可以在此处指定是否要向活动添加出站过渡。 此过程的步骤7中详细介绍了不同的过渡类型。
   * **[!UICONTROL Recurring SMS]**:根据活动中定义的频率，发送多次短消息 **[!UICONTROL Scheduler]** 。 选择发送的聚合期。 这允许您将定义期间发生的所有发送重新分组到一个称为“重复执行 **** ”的单一视图中，该视图可从应用程序的营销活动列表中访问。

      例如，对于每天发送的循环生日SMS，您可以选择每月汇总发送。 这样，尽管SMS每天都会发送，但您每月都可以收到有关您发送的报告。

1. 选择SMS类型。 SMS类型来自在&gt; **[!UICONTROL Resources]** &gt;菜单中定义的SMS **[!UICONTROL Templates]** 模 **[!UICONTROL Delivery templates]** 板。
1. 输入SMS的常规属性。 您还可以将其附加到现有营销活动。 工作流的交付活动的标签会更新为SMS标签。
1. 定义SMS内容。 请参阅有关创建 [SMS消息的部分](../../channels/using/creating-an-sms-message.md)。
1. 默认情况下，活 **[!UICONTROL SMS delivery]** 动不包括任何出站过渡。 如果要向活动添加出站过渡，请转到高级活动选项的选 **[!UICONTROL SMS delivery]** 项卡( **[!UICONTROL General]**![](assets/dlv_activity_params-24px.png) 活动快速操作中的按钮)，然后选中以下选项之一：

   * **[!UICONTROL Add outbound transition without the population]**:这样，您就可以生成一个出站过渡，其中包含与入站过渡完全相同的人数。
   * **[!UICONTROL Add outbound transition with the population]**:这样，您就可以生成一个出站过渡，其中包含将SMS发送到的人群。 在交付准备过程中被排除的目标成员（隔离、无效编号等）将被排除在此过渡之外。

1. 确认活动的配置并保存工作流。

重新打开活动后，您会直接转到SMS功能板。 只能编辑其内容。

默认情况下，启动传送工作流只会触发消息准备。 在工作流启动后，仍需要确认从工作流创建的消息的发送。 但是，在消息功能板中，并且仅当消息是从工作流创建的时候，您才能禁用该选 **[!UICONTROL Request confirmation before sending messages]** 项。 取消选中此选项后，准备完成后，消息将发送，无需进一步通知。

## 评论 {#remarks}

在工作流中创建的交货可以在应用程序的营销活动列表中访问。 您可以使用功能板查看工作流的执行状态。 SMS摘要窗格中的链接允许您直接访问链接的元素（在出现重复的SMS时，工作流、营销活动、父交付）。

但是，循环提交的执行在默认情况下是遮罩的。 要查看它们，请选中 **[!UICONTROL Show recurring executions]** 营销活动搜索面板中的选项。

在可从营销活动列表访问或直接通过关联的重复执行访问的父分发中，您可以查看已处理的发送的总数（根据配置活动时指定的汇总期间）。 **[!UICONTROL SMS delivery]** 为此，请选择以打开父分发块的详细信 **[!UICONTROL Deployment]** 息视图 ![](assets/wkf_dlv_detail_button.png)。

## Example {#example}

![](assets/wkf_sms_example_1.png)

此示例是生日工作流。 每天都会有短信被发送到当天生日的档案里。 操作步骤：

* 您 **[!UICONTROL Scheduler]** 可以在每天上午8点开始工作流。

   ![](assets/wkf_delivery_example_2.png)

* 该活 **[!UICONTROL Query]** 动允许您计算每次执行工作流时提供移动电话号码且其生日在当天的配置文件。 生日计算是使用查询编辑工具调色板中可用的预定义过滤器执行的。

   ![](assets/wkf_delivery_example_3.png)

* 重复 **[!UICONTROL SMS]** 出现。 发送按月汇总。 因此，每月发送的所有SMS消息都汇总到一个视图中。 因此，在一年内，将执行365次提交，但会在Adobe Campaign界面中将其重新分组为12个视图( **也称为重复执行**)。 历史记录和报告详细信息每月都会显示，而不是每次发送。

   ![](assets/wkf_sms_example_4.png)

有关工作流中SMS交付的另一个示例，请参 [阅用例：重定向向非打开者发送新分发的工作流](../../automating/using/workflow-cross-channel-retargeting.md)。
