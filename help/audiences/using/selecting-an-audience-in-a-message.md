---
title: 在信息中选择受众
seo-title: 在信息中选择受众
description: 在信息中选择受众
seo-description: “通过分步步骤选择电子邮件的受众：主要目标人群和测试档案”。
page-status-flag: 从未激活
uuid: 7d8f8446-f2 e0-49c1-83f6-9667b29 bc228
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 受众
content-type: reference
topic-tags: 管理受众
discoiquuid: 158da6ff-8899-4e7b-b925-8a42 c3 de46 a1
context-tags: DeliquyCreate，向导；交付，受众，返回
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: c9e33f51ab497b8bd111dfc307670f2fde5d804f

---


# Selecting an audience in a message{#selecting-an-audience-in-a-message}

通过Adobe Campaign，您可以在消息的受众中配置多个配置文件类型。

如果消息已经创建，则可以通过创建向导或消息仪表板中的消息来定义受众。

>[!NOTE]
>
>如果受众已经在工作流程中构建并丰富了额外数据，您将无法使用这些数据个性化单独交付。它们只能用于在工作流中执行的分发。

1. 从仪表板中，转到受众块开始。

   ![](assets/delivery_audience_definition_1.png)

   随后将打开用于定义受众的屏幕。它有两个选项卡，允许您单独定义将收到消息的每种类型的受众：

   * Target
   * 测试配置文件
   ![](assets/delivery_audience_definition_2.png)

1. Define the main **[!UICONTROL Target]** of the email. 这是电子邮件的常规目标受众。

   The target is defined in the **[!UICONTROL Target]** tab and is made up of identified profiles from your database.

   You can establish your main target using the [query editor](../../automating/using/editing-queries.md#creating-queries) functionalities.

   In this tab, the **[!UICONTROL Shortcuts]** palette only contains predefined filters and the audiences that have been defined in the identified profiles. **[!UICONTROL Explorer]** 选项卡允许您访问其他配置。

   因此，您可以重新使用和合并现有受众，为他们应用额外的过滤器等。

1. Define the **[!UICONTROL Test profiles]** you want to use for the email. 测试配置文件将在发送到主目标之前先发送校样，以测试电子邮件。

   For more information on configuring test profiles, refer to the [Test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md) section.

随后将更新受众块，并显示已为相关电子邮件选择目标和测试配置文件。

![](assets/delivery_audience_definition_3.png)

