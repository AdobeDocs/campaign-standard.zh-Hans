---
title: 构建对照组
description: 此用例说明如何构建对照组。
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,segmentation,delivery
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e689e6bc362f4e948593c3b251f3825aab20ac
workflow-type: tm+mt
source-wordcount: '763'
ht-degree: 1%

---


# 构建对照组 {#building-control-group}

要衡量投放的影响，您可能希望从目标中排除某些用户档案，以便他们不会收到给定的消息。 此对照组可用于与接收消息的目标群体的行为进行比较。

要在Adobe Campaign Standard中执行此操作，您可以构建包含以下活动的工作流：
* 查询 [活动](../../automating/using/query.md) ,目标特定人口。
* 分 [段活动](../../automating/using/segmentation.md) ，用于从此群体中分离随机对照组。
* 电 [子邮件投放](../../automating/using/email-delivery.md) 活动，用于向主目标发送消息。
* 更 [新活动](../../automating/using/update-data.md) ，用于更新从目标中排除的用户档案(随机对照组)。

![](assets/wkf_control-group.png)

## 扩展用户档案资源 {#extending-profile}

首先，您需要使用与 **[!UICONTROL Profile]** 对照组对应的新字段扩展资源。 运行工作流后，将检查此字段是否有从用户档案中排除的目标。

1. 从 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**&#x200B;单击 **[!UICONTROL Create]**。
1. 如果尚未扩展，请选择并 **[!UICONTROL Extend an existing resource]** 选择资 **[!UICONTROL Profile]** 源。
1. 在选 **[!UICONTROL Data structure]** 项卡中，为对照组添加新字段，然后 **[!UICONTROL Boolean]** 选择该 **[!UICONTROL Type]** 字段。

   ![](assets/wkf_control-group-profile-field.png)

1. 从选 **[!UICONTROL Screen definition]** 项卡中，展开 **[!UICONTROL Detail screen configuration]** 该部分并选择您刚刚创建的字段，以便显示每个用户档案。

   ![](assets/wkf_control-group-profile-field-screen.png)

1. 保存更改。
1. 更新数据库结构以发布扩 **[!UICONTROL Profile]** 展资源。 请参 [阅发布自定义资源](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。

有关扩展自定义资源的详细信息，请 [参阅添加资源的关键步骤](../../developing/using/key-steps-to-add-a-resource.md)。

## 创建工作流 {#creating-a-workflow}

1. 在中 **[!UICONTROL Marketing Activities]**，单击 **[!UICONTROL Create]** 并选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]** 为工作流类型并单击 **[!UICONTROL Next]**。
1. 输入工作流的属性并单击 **[!UICONTROL Create]**。

创建工作流的详细步骤在构建工作流 [部分中介绍](../../automating/using/building-a-workflow.md) 。

## 创建查询活动 {#create-a-query-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**&#x200B;中，拖放一个 [查询](../../automating/using/query.md) 活动。
1. 多次-单击活动以定义目标。
1. 例如，在拖 **[!UICONTROL Shortcuts]**&#x200B;放中，使 **[!UICONTROL Profile]**&#x200B;用运 **[!UICONTROL Age]** 算符进行选择， **[!UICONTROL Greater than]** 并在字段中键入 **[!UICONTROL Value]** 25。
1. 单击 **[!UICONTROL Confirm]**.

## 创建分段活动 {#creating-a-segmentation-activity}

1. 拖放分段 [活动](../../automating/using/segmentation.md) ，然后多次单击它。
1. 在选项卡 **[!UICONTROL Segments]** 中，选择要编辑的区段。
1. 在该区 **[!UICONTROL Configuration]** 段的选项卡中，选择 **[!UICONTROL Limit the population of this segment]** 选项。

   ![](assets/wkf_control-segment-configuration.png)

1. 在选 **[!UICONTROL Limitation]** 项卡中，确保选 **[!UICONTROL Random sampling]** 择了该选项。

   ![](assets/wkf_control-segment-limitation.png)

1. 定义初始人口的百分比，例如10%并单击 **[!UICONTROL Confirm]**。 对照组将由目标人群中的10%随机选择。
1. 在选 **[!UICONTROL Advanced options]** 项卡中，选 **[!UICONTROL Generate complement]** 择选项并填写 **[!UICONTROL Transition label]** 和字 **[!UICONTROL Segment code]** 段。

   ![](assets/wkf_control-segment-advanced.png)

1. 单击 **[!UICONTROL Confirm]**.

## 创建电子邮件活动 {#creating-an-email-activity}

1. 在> **[!UICONTROL Activities]** 中 **[!UICONTROL Channels]**，将电子邮件投放 [活动拖放](../../automating/using/email-delivery.md) 到主目标段之后。
1. 单击活动并选 ![](assets/edit_darkgrey-24px.png) 择以编辑它。
1. 选择 **[!UICONTROL Single send email]** 并单击 **[!UICONTROL Next]**。
1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件的布局，请单击 **[!UICONTROL Use the Email Designer]**。
1. 编辑和保存您的内容。
1. 在消 **[!UICONTROL Schedule]** 息仪表板的一节中，在发送消 **息之前取消选择[!UICONTROL请求确认** 。

## 创建更新数据活动 {#creating-update-data-activity}

1. 将更新活动拖 [放到对照组](../../automating/using/update-data.md) 段之后。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮打开它。
1. 在选 **[!UICONTROL General]** 项卡中， **[!UICONTROL Update]** 从下 **[!UICONTROL Operation type]** 拉列表中选择。
1. 在选项 **[!UICONTROL Identification]** 卡中，选择 **[!UICONTROL Directly using the targeting dimension]** 选项。
1. 选择您 **[!UICONTROL Profile]** 之前扩展的资源作为要更新的维。

   ![](assets/wkf_control-update-identification.png)

1. 在选 **[!UICONTROL Fields to update]** 项卡中，选择您作为添加到资源的对照组 **[!UICONTROL Profile]** 字段， **[!UICONTROL Destination]** 然后输入true作为条件。

   ![](assets/wkf_control-update-fields-to-update.png)

1. 单击 **[!UICONTROL Confirm]**.

## 运行工作流 {#running-the-workflow}

单击 **[!UICONTROL Start]** 以运行工作流。

运行工作流后，将排除对照组的填充，并将消息发送到其余的主目标。

资源 **[!UICONTROL Profile]** 将按如下方式更新： 如果用户档案在对照组中，则检查相应的字段。

![](assets/wkf_control-group-profile-checked.png)

您现在可以比较消息的收件人将如何响应，而小组被排除在消息之外但未收到消息。

## 重用相同的对照组 {#reusing-same-control-group}

上面的示例允许创建全局对照组，因为它作为独立于投放的用户档案属性存储。 事实上，作为资源扩展的一部分创建的新“对照组 **[!UICONTROL Profile]** ”字段会在运行上述工作流后更新。

因此，下次要使用相同对照组时，您可以在新的“对照组”字段中进行分段，而不是进行随机分段。

操作步骤：
1. 创建活动 **[!UICONTROL Segmentation]** 时，在选项卡中选择要编辑的 **[!UICONTROL Segments]** 区段。
1. 在该 **[!UICONTROL Configuration]** 区段的选项卡中，确保不选择该选 **[!UICONTROL Limit the population of this segment]** 项。
1. 在选项卡 **[!UICONTROL Filtering]** 中，拖放到主工 **[!UICONTROL Profiles (attributes)]** 作区中。

   ![](assets/wkf_control-group-segment-profiles-attributes.png)

1. 在窗 **[!UICONTROL Add a rule - Profiles (attributes)]** 口中，选择“对照组”(添加到资源的字 **[!UICONTROL Profile]** 段)并选 **[!UICONTROL Yes]** 择作为筛选条件。

   ![](assets/wkf_control-group-segment-profiles-attributes-field.png)
