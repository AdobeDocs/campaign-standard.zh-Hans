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
source-git-commit: e9a4d99ddf311898c48b2b352fa13f5b59ed1fbe

---


# Creating a custom profile dimension{#creating-a-custom-profile-dimension}

还可以根据在配置文件自定义资源扩展过程中创建的自定义配置文件数据来创建和管理报告。

In this example, we want to create the custom profile field **Loyalty programs** which will be divided into three levels: gold, silver and bronze. 随后将扩展此自定义配置文件，以将其用作动态报告中的自定义配置文件维度。

* [步骤1：创建新的配置文件字段](../../reporting/using/creating-a-custom-profile-dimension.md#step-1--create-a-new-profile-field)
* [步骤2：用配置文件字段扩展发送日志](../../reporting/using/creating-a-custom-profile-dimension.md#step-2--extend-the-sending-logs-with-the-profile-field)
* [步骤3：创建在忠诚度计划中登记的交付目标收件人](../../reporting/using/creating-a-custom-profile-dimension.md#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [第步：创建动态报告以过滤具有自定义配置文件维度的收件人](../../reporting/using/creating-a-custom-profile-dimension.md#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## Step 1: Create a new profile field {#step-1--create-a-new-profile-field}

We first need to create the new profile field **Loyalty program** that will assign loyalty level to our recipients: gold, silver or bronze.

>[!NOTE]
>
>自定义资源只能由管理员管理。

要执行此操作，请执行以下操作：

1. From the advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom resources]** then the **[!UICONTROL Profile (profile)]** custom resource.

   ![](assets/custom_profile_1.png)

1. From the **[!UICONTROL Data structure]** tab, in the **[!UICONTROL Fields]** category, click the **[!UICONTROL Add field]** button.

   ![](assets/custom_profile_2.png)

1. Enter the **[!UICONTROL Label]**, **[!UICONTROL ID]** and select the custom resource **[!UICONTROL Type]**. Here, we selected **[!UICONTROL Text]** since recipients will have the choice between gold, silver and bronze.

   ![](assets/custom_profile_3.png)

1. Click the ![](assets/custom_profile_22.png) icon to define your field.

   ![](assets/custom_profile_12.png)

1. Here, we need to specify the authorized values by checking **[!UICONTROL Specify a list of authorized valued]** and create each value by clicking **[!UICONTROL Create element]**.

   ![](assets/custom_profile_13.png)

1. Enter the **[!UICONTROL Label]** and **[!UICONTROL Value]** then click **[!UICONTROL Add]**. 在本例中，我们需要创造黄金、银和铜牌的价值。Click **[!UICONTROL Confirm]** when done.

   ![](assets/custom_profile_14.png)

1. Select the **[!UICONTROL Screen definition]** tab. In the **[!UICONTROL Detail screen configuration]** drop-down, check **[!UICONTROL Add personalized fields]** section to create a new section in our profile.

   ![](assets/custom_profile_4.png)

1. Click the **[!UICONTROL Add an element]** button to create your new section. Select the **[!UICONTROL Type]**: **[!UICONTROL Input field]**, **[!UICONTROL Value]** or **[!UICONTROL List]**, then the field to add in this new section.

   ![](assets/custom_profile_5.png)

1. You can also add a title to your section in the field **[!UICONTROL Customize the title of the section where the fields will be displayed]**.

   Click **[!UICONTROL Save]** when the configuration is done.

   ![](assets/custom_profile_6.png)

1. From the advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Publication]** to start publishing your custom resource.
1. Click **[!UICONTROL Prepare publication]** then when the preparation is done, click the **[!UICONTROL Publish]** button.

   ![](assets/custom_profile_7.png)

您的新配置文件字段现在可供收件人使用和选择。

![](assets/custom_profile_8.png)

## Step 2: Extend the sending logs with the profile field {#step-2--extend-the-sending-logs-with-the-profile-field}

创建配置文件字段后，我们需要使用我们的配置文件字段扩展发送日志，以便在动态报告中创建关联的自定义配置文件维度。

Before extending the log with our profile field, make sure that the PII window was accepted to have access to the **[!UICONTROL Sending logs extension]** tab. For more on this, refer to this [page](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

>[!NOTE]
>
>日志只能由管理员使用配置文件字段进行扩展。

1. From the advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom resources]** then the **[!UICONTROL Profile (profile)]** custom resource.
1. Open the **[!UICONTROL Sending logs extension]** drop-down.
1. Click the **[!UICONTROL Create element]** button.

   ![](assets/custom_profile_9.png)

1. Select your previously created field and click **[!UICONTROL Confirm]**.
1. Check **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** to create your custom profile dimension.

   ![](assets/custom_profile_10.png)

   仅当PII窗口被接受时，此选项才可用。For more on this, refer to this [page](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

1. Click **[!UICONTROL Add]** then save your custom resource.
1. 自定义资源被修改后，我们需要发布它以实施新的更改。

   From the advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Publication]** to start publishing your custom resource.

1. Click **[!UICONTROL Prepare publication]** then when the preparation is done, click the **[!UICONTROL Publish]** button.

   ![](assets/custom_profile_7.png)

自定义配置文件现在可作为报表中的自定义配置文件维度提供。

既然您的字段已创建，并且已经用此配置文件字段扩展了日志日志，您可以开始定位交付中的收件人。

## Step 3: Create a delivery targeting recipients enrolled in the loyalty program {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

发布配置文件字段后，您可以开始提交。在此示例中，我们希望针对在忠诚度计划中登记的每个收件人。

1. From the **[!UICONTROL Marketing activities]** tab, click **[!UICONTROL Create]** then select **[!UICONTROL Email]**.
1. Choose an **[!UICONTROL Email type]** then enter your email's properties.
1. To target recipient enrolled in the loyalty program, drag and drop the **[!UICONTROL Profiles (attributes)]** activity.
1. Select your previously created field from the **[!UICONTROL Field]** drop-down.

   ![](assets/custom_profile_16.png)

1. Select your **[!UICONTROL Filter conditions]**. 这里，我们希望定位属于三个忠诚度计划级别之一的收件人。

   ![](assets/custom_profile_17.png)

1. Click **[!UICONTROL Confirm]** then when done filtering, click **[!UICONTROL Next]**.
1. 定义和个性化消息内容、发送者姓名和主题。For more information on email creation refer to this [page](../../designing/using/about-email-content-design.md#about-the-email-designer).

   Then, click **[!UICONTROL Create]**.

1. 准备就绪后，您可以预览并发送消息。For more information on how to prepare and send your message, refer to this [page](../../sending/using/preparing-the-send.md).

将电子邮件正确发送给选定收件人后，您可以开始筛选数据并通过报告跟踪交付成功与否。

## Step 4: Create a dynamic report to filter recipients with the custom profile dimension {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

After sending your delivery, you can breakdown reports using your custom profile dimension from the **[!UICONTROL Profile]** table.

1. From the **[!UICONTROL Reports]** tab, select an out-of-the-box report or click the **[!UICONTROL Create]** button to start one from scratch.

   ![](assets/custom_profile_18.png)

1. **[!UICONTROL Dimensions]** 在该类别中，单击将 **[!UICONTROL Profile]** 自定义 **忠诚度计划** 个人资料维度拖放到自由表格中。

   ![](assets/custom_profile_19.png)

1. Drag and drop the **[!UICONTROL Processed/Sent]** and **[!UICONTROL Open]** metrics to start filtering your data.

   ![](assets/custom_profile_20.png)

1. 根据需要在工作区中拖放可视化。

   ![](assets/custom_profile_21.png)

