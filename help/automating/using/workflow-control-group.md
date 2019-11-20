---
title: “工作流用例：控制组”
seo-title: “工作流用例：控制组”
description: “工作流用例：控制组”
seo-description: “工作流用例：控制组”
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
source-git-commit: 2912e3b75b817347b832f9c89ca2320868cbc355

---


# 工作流用例：构建控制组 {#building-control-group}

要衡量分发的影响，您可能希望从目标中排除某些配置文件，以便它们不会收到给定的消息。 该控制组可用于与接收消息的目标群体的行为进行比较。

要在Adobe Campaign standard中执行此操作，您可以构建包含以下活动的工作流：
* 用于定位给定人口的查询活动。
* 用于将随机控制组与此群体隔离的分段活动。
* 用于向主目标发送消息的电子邮件传送活动。
* 用于更新从目标（随机控制组）中排除的配置文件的更新数据活动。

![](assets/wkf_control-group.png)

## 扩展配置文件资源 {#extending-profile}

首先，您需要使用与控 **[!UICONTROL Profile]** 制组对应的新字段扩展资源。 运行工作流后，将检查此字段中是否有从目标中排除的配置文件。

1. 从 **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom Resources]**，单击 **[!UICONTROL Create]**。
1. 如果尚未扩展该资源，请选择并 **[!UICONTROL Extend an existing resource]** 选择该资 **[!UICONTROL Profile]** 源。
1. 在选 **[!UICONTROL Data structure]** 项卡中，为控件组添加新字段，然后为该 **[!UICONTROL Boolean]** 字段选 **[!UICONTROL Type]** 择。

   ![](assets/wkf_control-group-profile-field.png)

1. 从选 **[!UICONTROL Screen definition]** 项卡中，展开该 **[!UICONTROL Detail screen configuration]** 部分并选择您刚刚创建的字段，以便显示每个配置文件。

   ![](assets/wkf_control-group-profile-field-screen.png)

1. 保存更改。
1. 更新数据库结构以发布扩 **[!UICONTROL Profile]** 展资源。 请参 [阅发布自定义资源](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。

有关扩展自定义资源的详细信息，请参 [阅添加资源的关键步骤](../../developing/using/key-steps-to-add-a-resource.md)。

## 创建工作流 {#creating-a-workflow}

1. 在中， **[!UICONTROL Marketing Activities]**&#x200B;单击并 **[!UICONTROL Create]** 选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]** 为工作流类型，然后单击 **[!UICONTROL Next]**。
1. 输入工作流的属性，然后单击 **[!UICONTROL Create]**。

创建工作流的详细步骤在构建工作流 [部分中介绍](../../automating/using/building-a-workflow.md) 。

## 创建查询活动 {#create-a-query-activity}

1. 在 **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**&#x200B;中，拖放 **[!UICONTROL Query activity]**。
1. 双击活动以定义目标。
1. 例如，在拖放 **[!UICONTROL Shortcuts]**&#x200B;中，使用运算符进行 **[!UICONTROL Profile]**&#x200B;选择，并在字 **[!UICONTROL Age]** 段中键入25 **[!UICONTROL Greater than]****[!UICONTROL Value]** 。
1. Click **[!UICONTROL Confirm]**.

“查询”部分显示了构建查询活动的详细 [步骤](../../automating/using/query.md) 。

## 创建分段活动 {#creating-a-segmentation-activity}

1. 拖放活动 **[!UICONTROL Segmentation]** 并双击它。
1. 在选项卡 **[!UICONTROL Segments]** 中，选择要编辑的区段。
1. 在该区 **[!UICONTROL Configuration]** 段的选项卡中，选择 **[!UICONTROL Limit the population of this segment]** 选项。

   ![](assets/wkf_control-segment-configuration.png)

1. 在选 **[!UICONTROL Limitation]** 项卡中，确保选 **[!UICONTROL Random sampling]** 中此选项。

   ![](assets/wkf_control-segment-limitation.png)

1. 定义初始人口的百分比，例如10%，然后单击 **[!UICONTROL Confirm]**。 对照组将由目标人群中的10%组成，随机选择。
1. 在选 **[!UICONTROL Advanced options]** 项卡中，选择 **[!UICONTROL Generate complement]** 选项并填写和 **[!UICONTROL Transition label]** 字 **[!UICONTROL Segment code]** 段。

   ![](assets/wkf_control-segment-advanced.png)

1. Click **[!UICONTROL Confirm]**.

“分段”部分介绍了构建分段活动的详细 [步骤](../../automating/using/segmentation.md) 。

## 创建电子邮件活动 {#creating-an-email-activity}

1. 在 **[!UICONTROL Activities]** &gt; **[!UICONTROL Channels]**&#x200B;中，拖放主目标区 **[!UICONTROL Email Delivery]** 段后面的一个。
1. 单击活动，然后选择 ![](assets/edit_darkgrey-24px.png) 以编辑它。
1. 选择 **[!UICONTROL Single send email]** 并单击 **[!UICONTROL Next]**。
1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件布局，请单击 **[!UICONTROL Use the Email Designer]**。
1. 编辑和保存您的内容。
1. 在消 **[!UICONTROL Schedule]** 息功能板的部分中，取消选择 **[!UICONTROL请求确认，然后发送消息}** 。

构建电子邮件活动的详细步骤在电子邮件分发部 [分中介绍](../../automating/using/email-delivery.md) 。

## 创建更新数据活动 {#creating-update-data-activity}

1. 在控件组区段 **[!UICONTROL Update data]** 之后拖放活动。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮将其打开。
1. 在选 **[!UICONTROL General]** 项卡中，从 **[!UICONTROL Update]** 下拉列 **[!UICONTROL Operation type]** 表中选择。
1. 在选项卡 **[!UICONTROL Identification]** 中，选择相应的 **[!UICONTROL Directly using the targeting dimension]** 选项。
1. 选择您 **[!UICONTROL Profile]** 之前扩展的资源作为要更新的维。

   ![](assets/wkf_control-update-identification.png)

1. 在选 **[!UICONTROL Fields to update]** 项卡中，选择您添加到资源的控制组字 **[!UICONTROL Profile]** 段作为 **[!UICONTROL Destination]** ，然后输入true作为条件。

   ![](assets/wkf_control-update-fields-to-update.png)

1. Click **[!UICONTROL Confirm]**.

“更新数据”部分介绍了构建“更新”数据活动的 [详细步骤](../../automating/using/update-data.md) 。

## 运行工作流 {#running-the-workflow}

单击 **[!UICONTROL Start]** 以运行工作流。

运行工作流后，将排除控制组的人口，并将消息发送到其余的主目标。

资 **[!UICONTROL Profile]** 源将更新如下：如果控件组中有配置文件，则选中相应的字段。

![](assets/wkf_control-group-profile-checked.png)

您现在可以比较邮件收件人的反应方式与从邮件中排除而未收到邮件的小组。

## 重用同一控制组 {#reusing-same-control-group}

上例允许创建全局控制组，因为它作为独立于分发的配置文件属性存储。 事实上，作为资源扩展的一部分创建的新“控制组”字段在运行上述工作流 **[!UICONTROL Profile]** 后会更新。

因此，下次要使用同一控制组时，您可以在新的“控制组”字段上进行分段，而不是进行随机分段。

操作步骤：
1. 创建活动 **[!UICONTROL Segmentation]** 时，请在选项卡中选择要编辑的 **[!UICONTROL Segments]** 区段。
1. 在该区 **[!UICONTROL Configuration]** 段的选项卡中，确保不选择该选 **[!UICONTROL Limit the population of this segment]** 项。
1. 在该选 **[!UICONTROL Filtering]** 项卡中，拖放到 **[!UICONTROL Profiles (attributes)]** 主工作区。

   ![](assets/wkf_control-group-segment-profiles-attributes.png)

1. 在窗 **[!UICONTROL Add a rule - Profiles (attributes)]** 口中，选择“控制组”（您添加到资源的字段）并选 **[!UICONTROL Profile]** 择 **[!UICONTROL Yes]** 作为筛选条件。

   ![](assets/wkf_control-group-segment-profiles-attributes-field.png)