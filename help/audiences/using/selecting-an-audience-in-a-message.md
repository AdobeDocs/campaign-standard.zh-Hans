---
title: 选择消息的受众
description: “选择电子邮件受众的分步操作步骤：主要目标群体和测试用户档案。”
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: deliveryCreation,wizard;delivery,audience,back
feature: Audiences
role: User
level: Intermediate
exl-id: 239959ad-6386-42bf-a86a-5694cdaecd83
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 74%

---

# 选择消息的受众{#selecting-an-audience-in-a-message}

通过 Adobe Campaign,可在消息的受众中配置多种用户档案类型。

可在创建消息时通过创建向导定义受众，如果消息已创建，则可从消息仪表板定义受众。

>[!NOTE]
>
>如果已在工作流中构建了受众，且使用附加数据进行了扩充，则将无法使用这些数据来个性化独立投放。它们只能用于工作流中执行的投放。

1. 从仪表板，转至受众块以开始进行操作。

   ![](assets/delivery_audience_definition_1.png)

   随即会打开用于定义受众的屏幕。其中包含两个选项卡，分别用于定义接收消息的两种受众类型：

   * 目标
   * 测试用户档案

   ![](assets/delivery_audience_definition_2.png)

1. 定义电子邮件的主 **[!UICONTROL Target]**。这是电子邮件的常规目标受众。

   目标在 **[!UICONTROL Target]** 选项卡中定义，由数据库中已标识的用户档案组成。您可以使用[查询编辑器](../../automating/using/editing-queries.md#creating-queries)功能构建主目标。

   在此选项卡中，**[!UICONTROL Shortcuts]** 面板仅包含预定义过滤器和已标识档案中已定义的受众。利用 **[!UICONTROL Explorer]** 选项卡，可访问其他配置。

   这样，您就可以重复利用和组合现有受众，并进行对其应用附加过滤器等操作。

   >[!NOTE]
   >
   >定位受众时，请注意，未引用受众的定义，但 **已复制** 到查询中。 如果在查询中定位受众后对该受众进行了任何更改，请确保再次配置查询以将新定义考虑在内。

1. 定义您想要用于电子邮件的 **[!UICONTROL Test profiles]**。测试用户档案将收到您之前发送的校样，以在将电子邮件发送到主目标之前对其进行测试。

   有关配置测试用户档案的更多信息，请参阅[测试用户档案](../../audiences/using/managing-test-profiles.md)一节。

1. 如果需要，您可以使用相应的选项卡定义控制组。 这样，您就可以从目标撤销某些用户档案，以便这些用户档案不会收到消息。 有关此内容的更多信息，请参阅 [添加控制组](../../sending/using/control-group.md).

1. 您还可以使用替换地址获取用户档案将收到的消息的确切表示形式。  有关更多信息，请参阅[使用定向用户档案测试电子邮件消息](../../sending/using/testing-messages-using-target.md)。

随后将更新受众块，并显示已为相关电子邮件选择的目标和测试用户档案。

![](assets/delivery_audience_definition_3.png)
