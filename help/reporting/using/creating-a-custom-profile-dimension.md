---
title: 创建自定义用户档案维度
description: 了解如何根据自定义用户档案数据创建自定义用户档案维度。
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: 98516af1-d4dd-4c1f-b360-f19208c22f82
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '813'
ht-degree: 5%

---

# 创建自定义用户档案维度{#creating-a-custom-profile-dimension}

还可以根据在用户档案自定义资源扩展期间创建的自定义用户档案数据来创建和管理报表。

在本例中，我们要创建自定义用户档案字段 **忠诚计划** 分为三个层次：金、银、铜。 随后，此自定义用户档案将进行扩展，以便能够将其用作动态报告中的自定义用户档案维度。

* [步骤1:创建新用户档案字段](#step-1--create-a-new-profile-field)
* [步骤2:使用用户档案字段扩展发送日志](#step-2--extend-the-sending-logs-with-the-profile-field)
* [步骤3:创建投放定位已注册到忠诚度计划的收件人](#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [步骤4:创建动态报告以使用自定义用户档案维度过滤收件人](#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## 步骤1:创建新用户档案字段 {#step-1--create-a-new-profile-field}

我们首先需要创建新用户档案字段 **忠诚度计划** 来为收件人分配忠诚度级别：金、银或铜。

>[!NOTE]
>
>自定义资源只能由管理员管理。

为实现此操作，请执行以下步骤：

1. 从高级菜单中，选择 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** 然后 **[!UICONTROL Profile (profile)]** 自定义资源。

   ![](assets/custom_profile_1.png)

1. 从 **[!UICONTROL Data structure]** 选项卡 **[!UICONTROL Fields]** 类别，单击 **[!UICONTROL Add field]** 按钮。

   ![](assets/custom_profile_2.png)

1. 输入 **[!UICONTROL Label]**, **[!UICONTROL ID]** 并选择自定义资源 **[!UICONTROL Type]**. 在这里，我们选择 **[!UICONTROL Text]** 因为收件人可以选择金、银和铜。

   ![](assets/custom_profile_3.png)

1. 单击 ![](assets/custom_profile_22.png) 图标来定义字段。

   ![](assets/custom_profile_12.png)

1. 在此，我们需要通过检查 **[!UICONTROL Specify a list of authorized valued]** 通过单击 **[!UICONTROL Create element]**.

   ![](assets/custom_profile_13.png)

1. 输入 **[!UICONTROL Label]** 和 **[!UICONTROL Value]** 然后单击 **[!UICONTROL Add]**. 在本例中，我们需要创建价值金、银和铜。 完成后单击 **[!UICONTROL Confirm]**。

   ![](assets/custom_profile_14.png)

1. 选择 **[!UICONTROL Screen definition]** 选项卡。在 **[!UICONTROL Detail screen configuration]** 下拉框，检查 **[!UICONTROL Add personalized fields]** 创建新章节。

   ![](assets/custom_profile_4.png)

1. 单击 **[!UICONTROL Add an element]** 按钮以创建新部分。 选择 **[!UICONTROL Type]**: **[!UICONTROL Input field]**, **[!UICONTROL Value]** 或 **[!UICONTROL List]**，然后添加到此新部分中的字段。

   ![](assets/custom_profile_5.png)

1. 您还可以在字段中为部分添加标题 **[!UICONTROL Customize the title of the section where the fields will be displayed]**.

   单击 **[!UICONTROL Save]** 配置完成后。

   ![](assets/custom_profile_6.png)

1. 从高级菜单中，选择 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** 以开始发布自定义资源。
1. 单击 **[!UICONTROL Prepare publication]** 然后，在准备完成后，单击 **[!UICONTROL Publish]** 按钮。

   ![](assets/custom_profile_7.png)

您的新用户档案字段现已准备就绪，可供收件人使用和选择。

![](assets/custom_profile_8.png)

## 步骤2:使用用户档案字段扩展发送日志 {#step-2--extend-the-sending-logs-with-the-profile-field}

现在，您的用户档案字段已创建完毕，我们需要使用我们的用户档案字段扩展发送日志，以便在动态报告中创建关联的自定义用户档案维度。

在使用用户档案字段扩展日志之前，请确保已接受PII窗口，以便能够访问 **[!UICONTROL Sending logs extension]** 选项卡。 有关详细信息，请参见此 [ 页面](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

>[!NOTE]
>
>只能由管理员通过用户档案字段扩展日志。

1. 从高级菜单中，选择 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** 然后 **[!UICONTROL Profile (profile)]** 自定义资源。
1. 打开 **[!UICONTROL Sending logs extension]** 下拉菜单。
1. 单击 **[!UICONTROL Create element]** 按钮。

   ![](assets/custom_profile_9.png)

1. 选择您之前创建的字段，然后单击 **[!UICONTROL Confirm]**.
1. 检查 **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** 创建自定义用户档案维度。

   ![](assets/custom_profile_10.png)

   仅当PII窗口被接受时，此选项才可用。 有关详细信息，请参见此 [ 页面](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

1. 单击 **[!UICONTROL Add]** 然后保存自定义资源。
1. 由于自定义资源已修改，因此我们需要发布它以实施新更改。

   从高级菜单中，选择 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** 以开始发布自定义资源。

1. 单击 **[!UICONTROL Prepare publication]** 然后，在准备完成后，单击 **[!UICONTROL Publish]** 按钮。

   ![](assets/custom_profile_7.png)

现在，您的自定义用户档案可用作报表中的自定义用户档案维度。

现在，您已创建字段并且使用此用户档案字段扩展了发送日志，接下来便可以开始定位投放中的收件人。

## 步骤3:创建投放定位已注册到忠诚度计划的收件人 {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

发布用户档案字段后，即可开始投放。 在此示例中，我们希望定位忠诚度计划中注册的每个收件人。

1. 在 **[!UICONTROL Marketing activities]** 选项卡中，单击 **[!UICONTROL Create]**，然后选择 **[!UICONTROL Email]**。
1. 选择 **[!UICONTROL Email type]** 然后输入电子邮件的属性。
1. 要定位已注册加入忠诚度计划的收件人，请拖放 **[!UICONTROL Profiles (attributes)]** 活动。
1. 从 **[!UICONTROL Field]** 下拉菜单。

   ![](assets/custom_profile_16.png)

1. 选择 **[!UICONTROL Filter conditions]**. 在此，我们要定位属于三个忠诚度计划级别之一的收件人。

   ![](assets/custom_profile_17.png)

1. 单击 **[!UICONTROL Confirm]** 过滤完成后，单击 **[!UICONTROL Next]**.
1. 定义和个性化消息内容、发件人姓名和主题。 有关创建电子邮件的更多信息，请参阅 [页面](../../designing/using/designing-content-in-adobe-campaign.md).

   然后，单击 **[!UICONTROL Create]**.

1. 准备就绪后，您可以预览并发送消息。 有关如何准备和发送消息的更多信息，请参阅此 [页面](../../sending/using/preparing-the-send.md).

在将电子邮件正确发送到选定收件人后，您可以开始过滤数据并通过报表跟踪投放是否成功。

## 步骤4:创建动态报告以使用自定义用户档案维度过滤收件人 {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

发送投放后，您可以使用 **[!UICONTROL Profile]** 表。

1. 从 **[!UICONTROL Reports]** 选项卡上，选择现成报表或单击 **[!UICONTROL Create]** 按钮从头开始。

   ![](assets/custom_profile_18.png)

1. 在 **[!UICONTROL Dimensions]** 类别，单击 **[!UICONTROL Profile]** 然后拖放您的自定义 **忠诚度计划** 配置文件维度添加到自由格式表。

   ![](assets/custom_profile_19.png)

1. 拖放 **[!UICONTROL Processed/Sent]** 和 **[!UICONTROL Open]** 量度来开始过滤数据。

   ![](assets/custom_profile_20.png)

1. 根据需要，在工作区中拖放可视化图表。

   ![](assets/custom_profile_21.png)

**相关主题：**

* [使用自定义用户档案数据创建有洞察力的报表](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
