---
title: 选择消息的受众
description: “选择电子邮件受众的分步操作步骤：主要目标群体和测试用户档案。”
page-status-flag: never-activated
uuid: 7d8f8446-f2e0-49c1-83f6-9667b29bc228
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 158da6ff-8899-4e7b-b925-8a42c3de46a1
context-tags: deliveryCreation,wizard;delivery,audience,back
internal: n
snippet: y
translation-type: ht
source-git-commit: 07d68b5bf8d800ebd95919f491e98f1b7a015705
workflow-type: ht
source-wordcount: '294'
ht-degree: 100%

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

   目标在 **[!UICONTROL Target]** 选项卡中定义，由数据库中已标识的用户档案组成。

   您可以使用[查询编辑器](../../automating/using/editing-queries.md#creating-queries)功能构建主目标。

   在此选项卡中，**[!UICONTROL Shortcuts]** 面板仅包含预定义过滤器和已标识档案中已定义的受众。利用 **[!UICONTROL Explorer]** 选项卡，可访问其他配置。

   这样，您就可以重复利用和组合现有受众，并进行对其应用附加过滤器等操作。

1. 定义您想要用于电子邮件的 **[!UICONTROL Test profiles]**。测试用户档案将收到您之前发送的校样，以在将电子邮件发送到主目标之前对其进行测试。

   有关配置测试用户档案的更多信息，请参阅[测试用户档案](../../audiences/using/managing-test-profiles.md)一节。

随后将更新受众块，并显示已为相关电子邮件选择的目标和测试用户档案。

![](assets/delivery_audience_definition_3.png)

