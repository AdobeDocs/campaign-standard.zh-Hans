---
title: 在消息中选择受众
description: “选择电子邮件受众的分步过程：主要目标人群和测试档案。”
page-status-flag: 从未激活
uuid: 7d8f8446-f2e0-49c1-83f6-9667b29bc228
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: 参考
topic-tags: 管理受众
discoiquuid: 158da6ff-8899-4e7b-b925-8a42c3de46a1
context-tags: deliveryCreation，向导；交付，受众，返回
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 在消息中选择受众{#selecting-an-audience-in-a-message}

Adobe Campaign允许您在消息的受众中配置多个配置文件类型。

可通过创建向导在创建消息时或在消息功能板（如果消息已创建）中定义受众。

>[!NOTE]
>
>如果受众是在工作流中构建的并且添加了其他数据，则您将无法使用这些数据个性化独立交付。 它们只能从在工作流中执行的分发中使用。

1. 从仪表板中，转到受众块开始。

   ![](assets/delivery_audience_definition_1.png)

   随后将打开定义受众的屏幕。 它有两个选项卡，允许您分别定义将收到消息的每种类型的受众：

   * Target
   * 测试配置文件
   ![](assets/delivery_audience_definition_2.png)

1. 定义电子邮 **[!UICONTROL Target]** 件的主要内容。 这是电子邮件的常规目标受众。

   目标在选项卡中定 **[!UICONTROL Target]** 义，并由数据库中标识的配置文件组成。

   您可以使用查询编辑器功能建立 [主目标](../../automating/using/editing-queries.md#creating-queries) 。

   在此选项卡中，调 **[!UICONTROL Shortcuts]** 色板仅包含预定义的过滤器以及在标识的配置文件中定义的受众。 该选 **[!UICONTROL Explorer]** 项卡允许您访问其他配置。

   因此，您可以重复使用和合并现有受众，对其应用其他筛选器等。

1. 定义 **[!UICONTROL Test profiles]** 要用于电子邮件的内容。 测试配置文件将收到您之前可以发送的校样，以在将电子邮件发送到主目标之前测试该电子邮件。

   有关配置测试配置文件的详细信息，请参阅测 [试配置文件](../../sending/using/managing-test-profiles-and-sending-proofs.md) 。

随后将更新受众块，并显示已为相关电子邮件选择目标和测试配置文件。

![](assets/delivery_audience_definition_3.png)

