---
solution: Campaign Standard
product: campaign
title: 创建自定义用户档案维度
description: 了解如何根据自定义用户档案数据创建自定义用户档案维度。
audience: reporting
content-type: reference
topic-tags: customizing-reports
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '813'
ht-degree: 5%

---


# 创建自定义用户档案维度{#creating-a-custom-profile-dimension}

还可以根据在用户档案自定义资源扩展期间创建的自定义用户档案数据创建和管理报告。

在此示例中，我们要创建自定义用户档案字段&#x200B;**Loyalty项目**，该字段将分为三个级别：金、银和铜。 此自定义用户档案随后将扩展，以便能够在动态报表中将其用作自定义用户档案维度。

* [第1步：创建新用户档案字段](#step-1--create-a-new-profile-field)
* [第2步：使用“用户档案”字段扩展发送日志](#step-2--extend-the-sending-logs-with-the-profile-field)
* [第3步：创建登记到忠诚度投放的收件人定位项目](#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [第4步：创建动态报表以使用自定义收件人维度筛选用户档案](#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## 第1步：新建一个用户档案字段{#step-1--create-a-new-profile-field}

我们首先需要创建新的用户档案字段&#x200B;**忠诚度项目**，以向收件人分配忠诚度级别：金、银或铜。

>[!NOTE]
>
>自定义资源只能由管理员管理。

为实现此操作，请执行以下步骤：

1. 从高级菜单中，选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** ，然后选择&#x200B;**[!UICONTROL Profile (profile)]**&#x200B;自定义资源。

   ![](assets/custom_profile_1.png)

1. 在&#x200B;**[!UICONTROL Data structure]**&#x200B;选项卡的&#x200B;**[!UICONTROL Fields]**&#x200B;类别中，单击&#x200B;**[!UICONTROL Add field]**&#x200B;按钮。

   ![](assets/custom_profile_2.png)

1. 输入&#x200B;**[!UICONTROL Label]**、**[!UICONTROL ID]**&#x200B;并选择自定义资源&#x200B;**[!UICONTROL Type]**。 在此，我们选择了&#x200B;**[!UICONTROL Text]**，因为收件人可以选择金、银和铜。

   ![](assets/custom_profile_3.png)

1. 单击![](assets/custom_profile_22.png)图标以定义字段。

   ![](assets/custom_profile_12.png)

1. 在此，我们需要通过检查&#x200B;**[!UICONTROL Specify a list of authorized valued]**&#x200B;来指定授权值，并通过单击&#x200B;**[!UICONTROL Create element]**&#x200B;来创建每个值。

   ![](assets/custom_profile_13.png)

1. 输入&#x200B;**[!UICONTROL Label]**&#x200B;和&#x200B;**[!UICONTROL Value]**，然后单击&#x200B;**[!UICONTROL Add]**。 在此示例中，我们需要创建金、银和铜的价值。 完成后，单击&#x200B;**[!UICONTROL Confirm]**。

   ![](assets/custom_profile_14.png)

1. 选择 **[!UICONTROL Screen definition]** 选项卡。在&#x200B;**[!UICONTROL Detail screen configuration]**&#x200B;下拉列表中，选中&#x200B;**[!UICONTROL Add personalized fields]**&#x200B;部分以在我们的用户档案中创建新部分。

   ![](assets/custom_profile_4.png)

1. 单击&#x200B;**[!UICONTROL Add an element]**&#x200B;按钮以创建新部分。 选择&#x200B;**[!UICONTROL Type]**:**[!UICONTROL Input field]**、**[!UICONTROL Value]**&#x200B;或&#x200B;**[!UICONTROL List]**，然后添加到此新部分中的字段。

   ![](assets/custom_profile_5.png)

1. 您还可以在字段&#x200B;**[!UICONTROL Customize the title of the section where the fields will be displayed]**&#x200B;中为您的章节添加标题。

   完成配置后，单击&#x200B;**[!UICONTROL Save]**。

   ![](assets/custom_profile_6.png)

1. 从高级菜单中，选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]**&#x200B;以开始发布自定义资源。
1. 单击&#x200B;**[!UICONTROL Prepare publication]**，准备完毕后单击&#x200B;**[!UICONTROL Publish]**&#x200B;按钮。

   ![](assets/custom_profile_7.png)

您的新用户档案字段现已准备好供收件人使用和选择。

![](assets/custom_profile_8.png)

## 第2步：使用用户档案字段{#step-2--extend-the-sending-logs-with-the-profile-field}扩展发送日志

既然您的用户档案字段已创建完毕，我们需要将发送日志与用户档案字段一起扩展，以在动态报表中创建关联的自定义用户档案维度。

在使用“用户档案”字段扩展日志之前，请确保接受PII窗口以访问&#x200B;**[!UICONTROL Sending logs extension]**&#x200B;选项卡。 有关详细信息，请参见此 [ 页面](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

>[!NOTE]
>
>只能由管理员使用用户档案字段扩展日志。

1. 从高级菜单中，选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** ，然后选择&#x200B;**[!UICONTROL Profile (profile)]**&#x200B;自定义资源。
1. 打开&#x200B;**[!UICONTROL Sending logs extension]**&#x200B;下拉列表。
1. 单击 **[!UICONTROL Create element]** 按钮。

   ![](assets/custom_profile_9.png)

1. 选择您之前创建的字段，然后单击&#x200B;**[!UICONTROL Confirm]**。
1. 选中&#x200B;**[!UICONTROL Add this field in Dynamic reporting as a new dimension]**&#x200B;可创建自定义用户档案维。

   ![](assets/custom_profile_10.png)

   此选项仅在接受PII窗口时可用。 有关详细信息，请参见此 [ 页面](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

1. 单击&#x200B;**[!UICONTROL Add]**，然后保存您的自定义资源。
1. 由于自定义资源已修改，因此我们需要发布它以实施新更改。

   从高级菜单中，选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]**&#x200B;以开始发布自定义资源。

1. 单击&#x200B;**[!UICONTROL Prepare publication]**，准备完毕后单击&#x200B;**[!UICONTROL Publish]**&#x200B;按钮。

   ![](assets/custom_profile_7.png)

现在，您的自定义用户档案可在报表中作为自定义用户档案维度使用。

现在，您的字段已创建，并且发送日志已通过此用户档案字段扩展，您可以在投放中开始定位收件人。

## 第3步：创建登记到忠诚度项目{#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}的投放定位收件人

发布用户档案字段后，即可开始投放。 在此示例中，我们希望目标登记到忠诚度项目的每个收件人。

1. 在 **[!UICONTROL Marketing activities]** 选项卡中，单击 **[!UICONTROL Create]**，然后选择 **[!UICONTROL Email]**。
1. 选择&#x200B;**[!UICONTROL Email type]**，然后输入电子邮件的属性。
1. 要目标收件人登记到忠诚度项目，请拖放&#x200B;**[!UICONTROL Profiles (attributes)]**&#x200B;活动。
1. 从&#x200B;**[!UICONTROL Field]**&#x200B;下拉列表中选择您之前创建的字段。

   ![](assets/custom_profile_16.png)

1. 选择&#x200B;**[!UICONTROL Filter conditions]**。 在此，我们希望目标收件人，这些客户是三个忠诚度项目级别之一的一部分。

   ![](assets/custom_profile_17.png)

1. 单击&#x200B;**[!UICONTROL Confirm]**，过滤完毕后，单击&#x200B;**[!UICONTROL Next]**。
1. 定义和个性化消息内容、发件人姓名和主题。 有关创建电子邮件的详细信息，请参阅此[页面](../../designing/using/designing-content-in-adobe-campaign.md)。

   然后，单击&#x200B;**[!UICONTROL Create]**。

1. 准备就绪后，您可以预览和发送消息。 有关如何准备和发送消息的详细信息，请参阅此[页面](../../sending/using/preparing-the-send.md)。

在将电子邮件正确发送到选定收件人后，您可以开始过滤数据并通过报告跟踪投放成功与否。

## 第4步：创建动态报告以筛选自定义收件人维{#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}的用户档案

在发送投放后，您可以使用&#x200B;**[!UICONTROL Profile]**&#x200B;表中的自定义用户档案维度划分报表。

1. 从&#x200B;**[!UICONTROL Reports]**&#x200B;选项卡中，选择现成报告，或单击&#x200B;**[!UICONTROL Create]**&#x200B;按钮从头开始开始一个。

   ![](assets/custom_profile_18.png)

1. 在&#x200B;**[!UICONTROL Dimensions]**&#x200B;类别中，单击&#x200B;**[!UICONTROL Profile]**，然后将自定义&#x200B;**忠诚度项目**&#x200B;用户档案维度拖放到自由格式表中。

   ![](assets/custom_profile_19.png)

1. 拖放&#x200B;**[!UICONTROL Processed/Sent]**&#x200B;和&#x200B;**[!UICONTROL Open]**&#x200B;量度以开始筛选数据。

   ![](assets/custom_profile_20.png)

1. 根据需要在工作区中拖放一个可视化。

   ![](assets/custom_profile_21.png)

**相关主题：**

* [使用自定义用户档案数据创建富有洞察力的报告](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
