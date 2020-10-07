---
title: 创建自定义用户档案维度
description: 了解如何根据自定义用户档案数据创建自定义用户档案维。
page-status-flag: never-activated
uuid: f75e005b-5328-4c98-9e78-51d54fd0e246
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: customizing-reports
discoiquuid: b6d3de63-3add-4881-8917-04a6f8b6be4d
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 创建自定义用户档案维度{#creating-a-custom-profile-dimension}

还可以根据在用户档案自定义资源扩展期间创建的自定义用户档案数据创建和管理报告。

在此示例中，我们要创建自定义用户档案字段 **Loyalty** ，该项目将分为三个级别：金、银和铜。 此自定义用户档案随后将扩展为能够在动态报告中将其用作自定义用户档案维。

* [第1步：创建新用户档案字段](#step-1--create-a-new-profile-field)
* [第2步：使用用户档案字段扩展发送日志](#step-2--extend-the-sending-logs-with-the-profile-field)
* [第3步：创建登记在忠诚度投放中的收件人定位项目](#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [第4步：创建动态报表以使用自定义收件人维度筛选用户档案](#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## 第1步：创建新用户档案字段 {#step-1--create-a-new-profile-field}

我们首先需要创建新的用户档案字段 **忠诚度项目** ，以便为收件人分配忠诚度级别：金、银或铜。

>[!NOTE]
>
>自定义资源只能由管理员管理。

为实现此操作，请执行以下步骤：

1. 从高级菜单中，选择 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** 然后选择自 **[!UICONTROL Profile (profile)]** 定义资源。

   ![](assets/custom_profile_1.png)

1. 在选 **[!UICONTROL Data structure]** 项卡的类别 **[!UICONTROL Fields]** 中，单击 **[!UICONTROL Add field]** 按钮。

   ![](assets/custom_profile_2.png)

1. 输入 **[!UICONTROL Label]**，然 **[!UICONTROL ID]** 后选择自定义资 **[!UICONTROL Type]**&#x200B;源。 在这里，我们选 **[!UICONTROL Text]** 择了收件人，因为他们可以选择金、银和铜。

   ![](assets/custom_profile_3.png)

1. 单击图 ![](assets/custom_profile_22.png) 标以定义字段。

   ![](assets/custom_profile_12.png)

1. 在此，我们需要通过选中并通过单击创建每 **[!UICONTROL Specify a list of authorized valued]** 个值来指定授权值 **[!UICONTROL Create element]**。

   ![](assets/custom_profile_13.png)

1. 输入， **[!UICONTROL Label]** 然后 **[!UICONTROL Value]** 单击 **[!UICONTROL Add]**。 在本例中，我们需要创建金、银和铜的价值。 Click **[!UICONTROL Confirm]** when done.

   ![](assets/custom_profile_14.png)

1. 选择 **[!UICONTROL Screen definition]** 选项卡。在下 **[!UICONTROL Detail screen configuration]** 拉框中，选中 **[!UICONTROL Add personalized fields]** 该部分以在我们的用户档案中创建新部分。

   ![](assets/custom_profile_4.png)

1. 单击按 **[!UICONTROL Add an element]** 钮以创建新部分。 选择 **[!UICONTROL Type]**: **[!UICONTROL Input field]**, **[!UICONTROL Value]** 或 **[!UICONTROL List]**，然后添加到此新部分的字段。

   ![](assets/custom_profile_5.png)

1. 您还可以在字段中为您的章节添加标题 **[!UICONTROL Customize the title of the section where the fields will be displayed]**。

   完 **[!UICONTROL Save]** 成配置时单击。

   ![](assets/custom_profile_6.png)

1. 从高级菜单中，选择 **[!UICONTROL Administration]** > **[!UICONTROL Development]** >以 **[!UICONTROL Publication]** 开始发布自定义资源。
1. 单 **[!UICONTROL Prepare publication]** 击，准备完成后，单击按 **[!UICONTROL Publish]** 钮。

   ![](assets/custom_profile_7.png)

您的新用户档案字段现已准备好供收件人使用和选择。

![](assets/custom_profile_8.png)

## 第2步：使用用户档案字段扩展发送日志 {#step-2--extend-the-sending-logs-with-the-profile-field}

现在，您的用户档案字段已创建完毕，我们需要将发送日志与用户档案字段一起扩展，以在动态报告中创建关联的自定义用户档案维。

在用我们的用户档案字段扩展日志之前，请确保已接受PII窗口以有权访问选 **[!UICONTROL Sending logs extension]** 项卡。 有关详细信息，请参见此 [ 页面](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

>[!NOTE]
>
>日志只能由管理员用用户档案字段进行扩展。

1. 从高级菜单中，选择 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** 然后选择自 **[!UICONTROL Profile (profile)]** 定义资源。
1. 打开 **[!UICONTROL Sending logs extension]** 下拉框。
1. 单击 **[!UICONTROL Create element]** 按钮。

   ![](assets/custom_profile_9.png)

1. Select your previously created field and click **[!UICONTROL Confirm]**.
1. 选中 **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** 以创建自定义用户档案维。

   ![](assets/custom_profile_10.png)

   此选项仅在接受PII窗口时可用。 有关详细信息，请参见此 [ 页面](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

1. 单击 **[!UICONTROL Add]** 然后保存自定义资源。
1. 由于自定义资源已修改，因此我们需要发布它以实施新的更改。

   从高级菜单中，选择 **[!UICONTROL Administration]** > **[!UICONTROL Development]** >以 **[!UICONTROL Publication]** 开始发布自定义资源。

1. 单 **[!UICONTROL Prepare publication]** 击，准备完成后，单击按 **[!UICONTROL Publish]** 钮。

   ![](assets/custom_profile_7.png)

您的自定义用户档案现在可作为自定义用户档案维在报表中可用。

现在，您的字段已创建且发送日志已通过此用户档案字段进行扩展，您可以在投放中开始定位收件人。

## 第3步：创建登记在忠诚度投放中的收件人定位项目 {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

发布用户档案字段后，即可开始投放。 在此示例中，我们希望目标登记到忠诚度项目的每个收件人。

1. 在 **[!UICONTROL Marketing activities]** 选项卡中，单击 **[!UICONTROL Create]**，然后选择 **[!UICONTROL Email]**。
1. 选择一个 **[!UICONTROL Email type]** 电子邮件，然后输入电子邮件的属性。
1. 要目标收件人登记到忠诚度项目，请拖放 **[!UICONTROL Profiles (attributes)]** 活动。
1. 从下拉菜单中选择您之前 **[!UICONTROL Field]** 创建的字段。

   ![](assets/custom_profile_16.png)

1. 选择您的 **[!UICONTROL Filter conditions]**。 在此，我们希望目标收件人，这些是忠诚项目的三个级别之一的一部分。

   ![](assets/custom_profile_17.png)

1. 单击 **[!UICONTROL Confirm]** ，然后在完成筛选后单 **[!UICONTROL Next]**&#x200B;击。
1. 定义消息内容、发件人姓名和主题并实现个性化。 For more information on email creation refer to this [page](../../designing/using/designing-content-in-adobe-campaign.md).

   Then, click **[!UICONTROL Create]**.

1. 准备就绪后，您可以预览和发送消息。 有关如何准备和发送邮件的详细信息，请参阅本 [页](../../sending/using/preparing-the-send.md)。

将电子邮件正确发送到选定收件人后，您可以开始过滤数据，并通过报告跟踪投放的成功情况。

## 第4步：创建动态报表以使用自定义收件人维度筛选用户档案 {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

发送投放后，您可以使用表中的自定义用户档案维度细分 **[!UICONTROL Profile]** 报告。

1. 在选 **[!UICONTROL Reports]** 项卡中，选择现成报告，或单击按钮从头 **[!UICONTROL Create]** 开始开始一个报告。

   ![](assets/custom_profile_18.png)

1. 在类别 **[!UICONTROL Dimensions]** 中，单 **[!UICONTROL Profile]** 击，然后将自定义Loyalty **** 项目用户档案维拖放到自由形式表中。

   ![](assets/custom_profile_19.png)

1. 拖放和度 **[!UICONTROL Processed/Sent]** 量 **[!UICONTROL Open]** 以开始筛选数据。

   ![](assets/custom_profile_20.png)

1. 根据需要在工作区中拖放一个可视化内容。

   ![](assets/custom_profile_21.png)

**相关主题：**

* [使用自定义用户档案数据创建富有洞察力的报告](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
