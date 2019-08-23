---
title: 创建自定义配置文件维度
seo-title: 创建自定义配置文件维度
description: 创建自定义配置文件维度
seo-description: 了解如何基于自定义配置文件数据创建自定义配置文件维度。
page-status-flag: 从未激活
uuid: f75e005b-5328-4c98-9e78-51d54fd0e246
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 报告报告
content-type: reference
topic-tags: 自定义报告
discoiquuid: b6d3de63-3add-4881-8917-04a6f8b6be4d
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 782a5f89b0361f1cbe59c9b353ca90dec90c3906

---


# 创建自定义配置文件维度{#creating-a-custom-profile-dimension}

还可以根据在配置文件自定义资源扩展过程中创建的自定义配置文件数据来创建和管理报告。

在此示例中，我们希望创建自定义配置文件字段 **忠诚度计划** ，这些计划将分为三个级别：金牌、银牌和铜牌。随后将扩展此自定义配置文件，以将其用作动态报告中的自定义配置文件维度。

* [步骤1：创建新的配置文件字段](../../reporting/using/creating-a-custom-profile-dimension.md#step-1--create-a-new-profile-field)
* [步骤2：用配置文件字段扩展发送日志](../../reporting/using/creating-a-custom-profile-dimension.md#step-2--extend-the-sending-logs-with-the-profile-field)
* [步骤3：创建在忠诚度计划中登记的交付目标收件人](../../reporting/using/creating-a-custom-profile-dimension.md#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [第步：创建动态报告以过滤具有自定义配置文件维度的收件人](../../reporting/using/creating-a-custom-profile-dimension.md#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## 步骤1：创建新的配置文件字段 {#step-1--create-a-new-profile-field}

我们首先需要创建新的配置文件字段 **忠诚度计划** ，以将忠诚度级别分配给我们的收件人：金牌、银牌或铜牌。

>[!NOTE]
>
>自定义资源只能由管理员管理。

要执行此操作，请执行以下操作：

1. 从高级菜单中，选择 **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom resources]** 然后选择 **[!UICONTROL Profile (profile)]** 自定义资源。

   ![](assets/custom_profile_1.png)

1. 在 **[!UICONTROL Data structure]** 选项卡 **[!UICONTROL Fields]** 的类别中，单击 **[!UICONTROL Add field]** 按钮。

   ![](assets/custom_profile_2.png)

1. 输入， **[!UICONTROL Label]****[!UICONTROL ID]** 然后选择自定义资源 **[!UICONTROL Type]**。我们选择 **[!UICONTROL Text]** 此选项后，收件人将选择黄金、银和铜牌。

   ![](assets/custom_profile_3.png)

1. 单击 ![](assets/custom_profile_22.png) 图标以定义您的字段。

   ![](assets/custom_profile_12.png)

1. 此处，我们需要通过单击来 **[!UICONTROL Specify a list of authorized valued]** 指定授权值，并通过单击创建每个值 **[!UICONTROL Create element]**。

   ![](assets/custom_profile_13.png)

1. 输入 **[!UICONTROL Label]** 然后 **[!UICONTROL Value]** 单击 **[!UICONTROL Add]**。在本例中，我们需要创造黄金、银和铜牌的价值。完成后单击 **[!UICONTROL Confirm]** 。

   ![](assets/custom_profile_14.png)

1. 选择 **[!UICONTROL Screen definition]** 选项卡。在 **[!UICONTROL Detail screen configuration]** 下拉列表中，选中 **[!UICONTROL Add personalized fields]** 部分以在我们的配置文件中创建新部分。

   ![](assets/custom_profile_4.png)

1. 单击 **[!UICONTROL Add an element]** 按钮以创建新部分。选择以下内容： **[!UICONTROL Type]****[!UICONTROL Input field]** 或 **[!UICONTROL Value]**&#x200B;在此新部分中添加的字段。**[!UICONTROL List]**

   ![](assets/custom_profile_5.png)

1. 您还可以在字段中添加标题的标题 **[!UICONTROL Customize the title of the section where the fields will be displayed]**。

   完成 **[!UICONTROL Save]** 配置后单击。

   ![](assets/custom_profile_6.png)

1. 从高级菜单中，选择 **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Publication]** 以开始发布自定义资源。
1. 单击 **[!UICONTROL Prepare publication]** 准备完成后，单击 **[!UICONTROL Publish]** 按钮。

   ![](assets/custom_profile_7.png)

您的新配置文件字段现在可供收件人使用和选择。

![](assets/custom_profile_8.png)

## 步骤2：用配置文件字段扩展发送日志 {#step-2--extend-the-sending-logs-with-the-profile-field}

创建配置文件字段后，我们需要使用我们的配置文件字段扩展发送日志，以便在动态报告中创建关联的自定义配置文件维度。

在使用我们的配置文件字段扩展日志之前，请确保PII窗口被接受访问 **[!UICONTROL Sending logs extension]** 选项卡。有关此操作的详细信息，请参阅此 [页面](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

>[!NOTE]
>
>日志只能由管理员使用配置文件字段进行扩展。

1. 从高级菜单中，选择 **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom resources]** 然后选择 **[!UICONTROL Profile (profile)]** 自定义资源。
1. 打开下 **[!UICONTROL Sending logs extension]** 拉列表。
1. 单击 **[!UICONTROL Create element]** 按钮。

   ![](assets/custom_profile_9.png)

1. 选择之前创建的字段，然后单击 **[!UICONTROL Confirm]**。
1. 选中 **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** 以创建自定义配置文件维度。

   ![](assets/custom_profile_10.png)

   仅当PII窗口被接受时，此选项才可用。有关此操作的详细信息，请参阅此 [页面](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

1. 单击 **[!UICONTROL Add]** 然后保存自定义资源。
1. 自定义资源被修改后，我们需要发布它以实施新的更改。

   从高级菜单中，选择 **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Publication]** 以开始发布自定义资源。

1. 单击 **[!UICONTROL Prepare publication]** 准备完成后，单击 **[!UICONTROL Publish]** 按钮。

   ![](assets/custom_profile_7.png)

自定义配置文件现在可作为报表中的自定义配置文件维度提供。

既然您的字段已创建，并且已经用此配置文件字段扩展了日志日志，您可以开始定位交付中的收件人。

## 步骤3：创建在忠诚度计划中登记的交付目标收件人 {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

发布配置文件字段后，您可以开始提交。在此示例中，我们希望针对在忠诚度计划中登记的每个收件人。

1. 从 **[!UICONTROL Marketing activities]** 选项卡中，单击 **[!UICONTROL Create]** 然后选择 **[!UICONTROL Email]**。
1. 选择一 **[!UICONTROL Email type]** 个然后输入您的电子邮件的属性。
1. 要锁定忠诚度计划中登记的收件人，请拖放 **[!UICONTROL Profiles (attributes)]** 活动。
1. 从下 **[!UICONTROL Field]** 拉列表中选择之前创建的字段。

   ![](assets/custom_profile_16.png)

1. 选择 **[!UICONTROL Filter conditions]**&#x200B;您的。这里，我们希望定位属于三个忠诚度计划级别之一的收件人。

   ![](assets/custom_profile_17.png)

1. 单击 **[!UICONTROL Confirm]** 完成过滤后，单击 **[!UICONTROL Next]**。
1. 定义和个性化消息内容、发送者姓名和主题。有关电子邮件创建的详细信息，请参阅此 [页面](../../designing/using/about-email-content-design.md#about-the-email-designer)。

   然后，单击 **[!UICONTROL Create]**。

1. 准备就绪后，您可以预览并发送消息。有关如何准备和发送消息的详细信息，请参阅此 [页](../../sending/using/preparing-the-send.md)。

将电子邮件正确发送给选定收件人后，您可以开始筛选数据并通过报告跟踪交付成功与否。

## 第步：创建动态报告以过滤具有自定义配置文件维度的收件人 {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

发送交付后，您可以使用 **[!UICONTROL Profile]** 表格中的自定义配置文件维度划分报表。

1. 从 **[!UICONTROL Reports]** 选项卡中，选择现成的报表，或单击 **[!UICONTROL Create]** 按钮以从头开始一个。

   ![](assets/custom_profile_18.png)

1. **[!UICONTROL Dimensions]** 在该类别中，单击将 **[!UICONTROL Profile]** 自定义 **忠诚度计划** 个人资料维度拖放到自由表格中。

   ![](assets/custom_profile_19.png)

1. 拖放操作， **[!UICONTROL Processed/Sent]****[!UICONTROL Open]** 开始筛选数据。

   ![](assets/custom_profile_20.png)

1. 根据需要在工作区中拖放可视化。

   ![](assets/custom_profile_21.png)

**相关主题：**

* [使用自定义配置文件数据创建富有洞察力的报表](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
