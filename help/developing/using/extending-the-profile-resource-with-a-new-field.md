---
title: 使用新字段扩展用户档案资源
description: 了解如何扩展配置文件资源。
page-status-flag: 从未激活
uuid: 9b99e95c-93ff-4187-90f7-db0baf5369ad
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 开发
content-type: 参考
topic-tags: use-cases-extending-resources
discoiquuid: 1e0f8945-fc3c-46a9-a8e5-b181a1f5ffcb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 使用新字段扩展用户档案资源{#extending-the-profile-resource-with-a-new-field}

## 关于扩展配置文件 {#about-extending-profiles}

此用例详细说明了如何使用专用字段扩展配置文件和测试配置文件。

在此，我们希望使用登录页面使用新字段更新我们的配置文件，然后使用特定于他们兴趣的新闻稿定位配置文件。

为此，请按照以下步骤操作：

* [第1步：扩展配置文件资源](#step-1--extend-the-profile-resource)
* [第2步：扩展测试配置文件](#step-2--extend-the-test-profile)
* [第3步：发布自定义资源](#step-3--publish-your-custom-resource)
* [第4步：使用工作流更新和定位配置文件](#step-4--update-and-target-profiles-with-a-workflow)

然后，以下字段将添加到我们的配置文件中，并可以定位到分发中：

![](assets/schema_extension_uc20.png)

相关主题：

* [关于自定义资源](../../developing/using/data-model-concepts.md)
* [管理用户档案](../../audiences/using/about-profiles.md)
* [管理测试配置文件](../../sending/using/managing-test-profiles-and-sending-proofs.md#managing-test-profiles)

## 第1步：扩展配置文件资源 {#step-1--extend-the-profile-resource}

要为我们的配 **置文件创建** “兴趣”字段，您首先需要扩展现成的资 **[!UICONTROL Profiles (profile)]** 源。

1. 从高级菜单中，通过Adobe Campaign徽标，选择 **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]**，然后 **[!UICONTROL Custom resources]**。
1. 如果尚未扩展该资 **[!UICONTROL Profiles]** 源，请单击 **[!UICONTROL Create]**。
1. 选择选 **[!UICONTROL Extend an existing resource]** 项。
1. 选择资 **[!UICONTROL Profile (profile)]** 源。
1. Click **[!UICONTROL Create]**.

   ![](assets/schema_extension_uc5.png)

1. 在选 **[!UICONTROL Fields]** 项卡的类 **[!UICONTROL Data structure]** 别中，单击 **[!UICONTROL Create element]**。

   >[!NOTE]
   >
   >请注意，如果您已经将资源 **[!UICONTROL Profile]** 扩展到以前的用途，则可以通过单击开始执行此步骤 **[!UICONTROL Add field]**。

   ![](assets/schema_extension_uc6.png)

1. 添加 **[!UICONTROL Label]** 和 **[!UICONTROL ID]**。 选择类 **[!UICONTROL Text]** 型并单击 **[!UICONTROL Add]**。

   ![](assets/schema_extension_uc9.png)

1. To configure your field, in the **[!UICONTROL Data structure]** tab under the **[!UICONTROL Fields]** drop-down, click ![](assets/schema_extension_uc8.png) then ![](assets/schema_extension_uc7.png) from your previously created field.
1. 在此示例中，我们要添加特定值，要这样做，请单击 **[!UICONTROL Specify a list of authorized values]**。

   ![](assets/schema_extension_uc10.png)

1. 单 **[!UICONTROL Add an element]** 击，然后添加所需数量的值，方法是添加 **[!UICONTROL Label]** 和并 **[!UICONTROL ID]** 单击 **[!UICONTROL Add]**。

   在此，我们将为配置文件创建“书籍”、“展览”、“电影”和“无”值，以便在这些选项之间进行选择。

   ![](assets/schema_extension_uc11.png)

1. 要在屏幕中添加此字 **[!UICONTROL Profile]** 段，请单击选 **[!UICONTROL Screen definition]** 项卡。
1. 在下拉 **[!UICONTROL Detail screen configuration]** 列表中，单击并 **[!UICONTROL Add a personalized fields section]** 单击 **[!UICONTROL Create element]**。

   ![](assets/schema_extension_uc12.png)

1. 选择 **[!UICONTROL Type]**。 在此，我们要添加一个输入字段。 然后，选择您之前创建的字段并单击 **[!UICONTROL Add]**。

   ![](assets/schema_extension_uc2.png)

1. 要添加分隔符以更好地组织您的配置文件窗 **[!UICONTROL Create an element]** 口，请单 **[!UICONTROL Separator]** 击并从下 **[!UICONTROL Type]** 拉菜单中选择。

   ![](assets/schema_extension_uc19.png)

您的字段现已配置。 我们现在需要将其扩展到测试配置文件。

>[!NOTE]
>
>如果您不需要扩展测试配置文件资源，可以跳到发布步骤。

## 第2步：扩展测试配置文件 {#step-2--extend-the-test-profile}

要测试新创建的字段是否正确配置，您可以通过将交付内容发送到测试配置文件来测试它。 首先，新字段也需要对测试配置文件进行。

1. 从高级菜单中，通过Adobe Campaign徽标，选择 **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]**，然后 **[!UICONTROL Custom resources]**。
1. 如果尚未扩展该资 **[!UICONTROL Profiles]** 源，请单击 **[!UICONTROL Create]**。
1. 选择选 **[!UICONTROL Extend an existing resource]** 项。
1. 选择资 **[!UICONTROL Test profile (seedMember)]** 源。
1. Click **[!UICONTROL Create]**.

   ![](assets/schema_extension_uc13.png)

1. 在选项卡 **[!UICONTROL Data structure]** 中，单击 **[!UICONTROL Create element]**。

   ![](assets/schema_extension_uc15.png)

1. 选择您之前创建的资源字段，然后单击 **[!UICONTROL Add]**。

   ![](assets/schema_extension_uc16.png)

1. 执行从步骤11到步骤13的相同步骤，如上面扩展配置文件演练，在屏幕中添加此字 **[!UICONTROL Test profile]** 段。
1. Click **[!UICONTROL Save]**.

现在，配置文件和测试配置文件都将提供新字段。 要正确配置该资源，您需要发布自定义资源。

## 第3步：发布自定义资源 {#step-3--publish-your-custom-resource}

要应用对资源所做的更改并能够使用它，您必须执行数据库更新。

1. 从高级菜单中，选择“管 **理** ”&gt;“ **开发**” **，然后选择“**&#x200B;发布”。
1. 默认情况下，选 **[!UICONTROL Determine modifications since the last publication]** 中此选项，这意味着将仅应用自上次更新以来执行的更改。

   ![](assets/schema_extension_uc14.png)

1. 单 **[!UICONTROL Prepare publication]** 击以启动将更新数据库的分析。
1. 执行发布后，单击“发 **布** ”按钮以应用新配置。

   ![](assets/schema_extension_uc17.png)

1. 发布后，每个资 **源的** “摘要”窗格会指示状态现在为“已发 **布** ”，并指定上次发布的日期。

   ![](assets/schema_extension_uc18.png)

1. 选择选 **[!UICONTROL Profiles]** 项卡并单 **[!UICONTROL New]** 击，查看更改是否已正确实现。

   ![](assets/schema_extension_uc20.png)

例如，您的新资源字段现已准备好在分发中使用和定位。

## 第4步：使用工作流更新和定位配置文件 {#step-4--update-and-target-profiles-with-a-workflow}

要使用新自定义字段的数据更新配置文件，您可以使用模板创建登陆 **[!UICONTROL Profile acquisition]** 页面。 有关登录页面的详细信息，请参阅此 [页面](../../channels/using/about-landing-pages.md)。

此处，我们希望定位未填写此字段的工作流配置文件。 他们将收到一封电子邮件，要求他们更新个人资料以接收个性化的新闻稿和优惠信息。 然后，每个档案都将根据其选择的兴趣收到个性化的新闻稿。

首先，我们需要创建一个登录页面，以更新目标配置 **文件的** “兴趣”字段：

1. 在中，单 **[!UICONTROL Marketing activities]**&#x200B;击，然 **[!UICONTROL Create]** 后选择 **[!UICONTROL Landing page]**。
1. 选择登陆页面类型。 在此，由于我们要更新我们的配置文件，请选择 **[!UICONTROL Profile acquisition]**。
1. Click **[!UICONTROL Create]**.
1. 单击该 **[!UICONTROL Content]** 块以开始编辑登录页面的内容。

   ![](assets/schema_extension_uc21.png)

1. 根据需要自定义登录页面。
1. 单击为您的配置文件配置的字段，以选择“兴趣”。 在左窗格中，选择您之前创建的 **Interest** 自定义资源。

   ![](assets/schema_extension_uc22.png)

1. 保存登陆页面并对其进行测试，以检查您的字段是否已正确配置。
1. 登 **[!UICONTROL Publish]** 录页面准备就绪后单击。

您的登录页面现已准备就绪。 要更新配置文件，您可以创建一个工作流，然后根据所选兴趣发送特价优惠。

1. 在选项卡 **[!UICONTROL Marketing activities]** 中，单击， **[!UICONTROL Create]** 然后选择 **[!UICONTROL Workflow]**。
1. 拖放活动以 **[!UICONTROL Query]** 定位所需的档案或受众。
1. 拖放活动以开 **[!UICONTROL Email delivery]** 始配置将包含登录页面链接的电子邮件。 选择 **[!UICONTROL Add an outbound transition with the population]**。

   ![](assets/schema_extension_uc3.png)

1. 根据需要创建和设计电子邮件。 有关电子邮件个性化的详细信息，请参阅此 [页](../../designing/using/quick-start.md)。
1. 在电子邮件中添加一个按钮，该按钮会将配置文件重定向到您的登录页面。
1. 选择添加的按钮，然 ![](assets/schema_extension_uc7.png) 后单击左 **[!UICONTROL Link]** 窗格中的部分。

   ![](assets/schema_extension_uc23.png)

1. 在窗 **[!UICONTROL Insert link]** 口中，从下拉 **[!UICONTROL Landing page]** 菜单中 **[!UICONTROL Link type]** 选择，然后选择之前创建的登录页面。

   ![](assets/schema_extension_uc24.png)

1. Click **[!UICONTROL Save]**. 您的电子邮件现已准备就绪，您可以返回工作流程。
1. 添加一 **[!UICONTROL Wait]** 个活动，让您的配置文件有一段时间填充登录页面。
1. 添加一 **[!UICONTROL Segmentation]** 个活动以根据其兴趣拆分出站转 **移**。
1. 为每个Interest创建出站 **区段**。

   ![](assets/schema_extension_uc4.png)

1. 在每次转 **[!UICONTROL Email delivery]** 换后添加活动，并根据所选兴趣创建个性化的 **电子邮件**。
1. 完成配置后启动工作流。

   ![](assets/schema_extension_uc25.png)

配置文件现在将收到电子邮件，要求他们填写此“兴趣”字段，然后根据选定的值发送个性化电子邮件。
