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
source-wordcount: '816'
ht-degree: 5%

---

# 创建自定义用户档案维度{#creating-a-custom-profile-dimension}

还可根据在配置文件自定义资源扩展期间创建的自定义配置文件数据，创建和管理报表。

在本例中，我们要创建自定义用户档案字段&#x200B;**忠诚度计划**，该字段将分为三个级别：金级、银级和铜级。 然后，将扩展此自定义用户档案，以便能够将其用作动态报告中的自定义用户档案维度。

* [第1步：创建新的用户档案字段](#step-1--create-a-new-profile-field)
* [第2步：使用用户档案字段扩展发送日志](#step-2--extend-the-sending-logs-with-the-profile-field)
* [步骤3：创建定向已注册忠诚度计划的收件人的投放](#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [第4步：创建动态报告，以使用自定义用户档案维度筛选收件人](#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## 第1步：创建新的用户档案字段 {#step-1--create-a-new-profile-field}

我们首先需要创建新的用户档案字段&#x200B;**忠诚度计划**，以便为收件人分配忠诚度级别：金牌、银牌或铜牌。

>[!NOTE]
>
>自定义资源只能由管理员管理。

为实现此操作，请执行以下步骤：

1. 从高级菜单中，选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**，然后选择&#x200B;**[!UICONTROL Profile (profile)]**&#x200B;自定义资源。

   ![](assets/custom_profile_1.png)

1. 在&#x200B;**[!UICONTROL Data structure]**&#x200B;选项卡的&#x200B;**[!UICONTROL Fields]**&#x200B;类别中，单击&#x200B;**[!UICONTROL Add field]**&#x200B;按钮。

   ![](assets/custom_profile_2.png)

1. 输入&#x200B;**[!UICONTROL Label]**、**[!UICONTROL ID]**&#x200B;并选择自定义资源&#x200B;**[!UICONTROL Type]**。 在本例中，我们选择了&#x200B;**[!UICONTROL Text]**，因为收件人可以选择金牌、银牌和铜牌。

   ![](assets/custom_profile_3.png)

1. 单击![](assets/custom_profile_22.png)图标以定义您的字段。

   ![](assets/custom_profile_12.png)

1. 在此，我们需要通过选中&#x200B;**[!UICONTROL Specify a list of authorized valued]**&#x200B;来指定授权值，并通过单击&#x200B;**[!UICONTROL Create element]**&#x200B;来创建每个值。

   ![](assets/custom_profile_13.png)

1. 输入&#x200B;**[!UICONTROL Label]**&#x200B;和&#x200B;**[!UICONTROL Value]**，然后单击&#x200B;**[!UICONTROL Add]**。 在本例中，我们需要创造金、银和铜的价值。 完成后单击 **[!UICONTROL Confirm]**。

   ![](assets/custom_profile_14.png)

1. 选择 **[!UICONTROL Screen definition]** 选项卡。在&#x200B;**[!UICONTROL Detail screen configuration]**&#x200B;下拉列表中，选中&#x200B;**[!UICONTROL Add personalized fields]**&#x200B;部分以在我们的配置文件中创建新部分。

   ![](assets/custom_profile_4.png)

1. 单击&#x200B;**[!UICONTROL Add an element]**&#x200B;按钮以创建新分区。 选择&#x200B;**[!UICONTROL Type]**： **[!UICONTROL Input field]**、**[!UICONTROL Value]**&#x200B;或&#x200B;**[!UICONTROL List]**，然后选择要添加到此新节中的字段。

   ![](assets/custom_profile_5.png)

1. 您还可以在字段&#x200B;**[!UICONTROL Customize the title of the section where the fields will be displayed]**&#x200B;中的章节中添加标题。

   配置完成后，单击&#x200B;**[!UICONTROL Save]**。

   ![](assets/custom_profile_6.png)

1. 从高级菜单中，选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]**&#x200B;以开始发布自定义资源。
1. 单击&#x200B;**[!UICONTROL Prepare publication]**，准备完成后，单击&#x200B;**[!UICONTROL Publish]**&#x200B;按钮。

   ![](assets/custom_profile_7.png)

您的新用户档案字段现已准备就绪，可供收件人使用和选择。

![](assets/custom_profile_8.png)

## 第2步：使用用户档案字段扩展发送日志 {#step-2--extend-the-sending-logs-with-the-profile-field}

现在您的用户档案字段已创建，我们需要使用用户档案字段扩展发送日志，以在动态报告中创建关联的自定义用户档案维度。

在使用我们的用户档案字段扩展日志之前，请确保已接受PII窗口以访问&#x200B;**[!UICONTROL Sending logs extension]**&#x200B;选项卡。 有关详细信息，请参见此 [&#x200B; 页面](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

>[!NOTE]
>
>日志只能由管理员使用配置文件字段进行扩展。

1. 从高级菜单中，选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**，然后选择&#x200B;**[!UICONTROL Profile (profile)]**&#x200B;自定义资源。
1. 打开&#x200B;**[!UICONTROL Sending logs extension]**&#x200B;下拉列表。
1. 单击 **[!UICONTROL Create element]** 按钮。

   ![](assets/custom_profile_9.png)

1. 选择您之前创建的字段并单击&#x200B;**[!UICONTROL Confirm]**。
1. 选中&#x200B;**[!UICONTROL Add this field in Dynamic reporting as a new dimension]**&#x200B;以创建您的自定义配置文件维度。

   ![](assets/custom_profile_10.png)

   仅当接受PII窗口时，此选项才可用。 有关详细信息，请参见此 [&#x200B; 页面](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

1. 单击&#x200B;**[!UICONTROL Add]**，然后保存您的自定义资源。
1. 由于自定义资源已被修改，因此我们需要发布它以实施新的更改。

   从高级菜单中，选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]**&#x200B;以开始发布自定义资源。

1. 单击&#x200B;**[!UICONTROL Prepare publication]**，准备完成后，单击&#x200B;**[!UICONTROL Publish]**&#x200B;按钮。

   ![](assets/custom_profile_7.png)

您的自定义用户档案现在可作为自定义用户档案维度显示在报表中。

现在您的字段已创建，并且发送日志已使用该用户档案字段扩展，您就可以开始定位投放中的收件人。

## 步骤3：创建定向已注册忠诚度计划的收件人的投放 {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

发布用户档案字段后，即可开始投放。 在本例中，我们希望定位已注册忠诚度计划的每个收件人。

1. 在 **[!UICONTROL Marketing activities]** 选项卡中，单击 **[!UICONTROL Create]**，然后选择 **[!UICONTROL Email]**。
1. 选择&#x200B;**[!UICONTROL Email type]**，然后输入电子邮件的属性。
1. 要定位已注册忠诚度计划的收件人，请拖放&#x200B;**[!UICONTROL Profiles (attributes)]**&#x200B;活动。
1. 从&#x200B;**[!UICONTROL Field]**&#x200B;下拉列表中选择您之前创建的字段。

   ![](assets/custom_profile_16.png)

1. 选择您的&#x200B;**[!UICONTROL Filter conditions]**。 在本例中，我们希望定位属于三个忠诚度计划级别之一的收件人。

   ![](assets/custom_profile_17.png)

1. 单击&#x200B;**[!UICONTROL Confirm]**，然后在完成过滤后单击&#x200B;**[!UICONTROL Next]**。
1. 定义并个性化邮件内容、发件人姓名和主题。 有关电子邮件创建的更多信息，请参阅此[页面](../../designing/using/designing-content-in-adobe-campaign.md)。

   然后，单击&#x200B;**[!UICONTROL Create]**。

1. 准备就绪后，您可以预览并发送消息。 有关如何准备和发送消息的更多信息，请参阅此[页面](../../sending/using/preparing-the-send.md)。

将电子邮件正确发送给选定收件人后，您可以开始筛选数据并通过报告跟踪投放的成功情况。

## 第4步：创建动态报告，以使用自定义用户档案维度筛选收件人 {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

发送投放后，您可以使用&#x200B;**[!UICONTROL Profile]**&#x200B;表中的自定义用户档案维度划分报表。

1. 从&#x200B;**[!UICONTROL Reports]**&#x200B;选项卡中，选择一个现成的报表或单击&#x200B;**[!UICONTROL Create]**&#x200B;按钮以从头开始创建报表。

   ![](assets/custom_profile_18.png)

1. 在&#x200B;**[!UICONTROL Dimensions]**&#x200B;类别中，单击&#x200B;**[!UICONTROL Profile]**，然后将您的自定义&#x200B;**忠诚度计划**&#x200B;配置文件维度拖放到自由格式表中。

   ![](assets/custom_profile_19.png)

1. 拖放&#x200B;**[!UICONTROL Processed/Sent]**&#x200B;和&#x200B;**[!UICONTROL Open]**&#x200B;量度以开始筛选您的数据。

   ![](assets/custom_profile_20.png)

1. 如果需要，可将可视化图表拖放到工作区中。

   ![](assets/custom_profile_21.png)

**相关主题：**

* [使用自定义用户档案数据创建有洞察力的报告](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
