---
solution: Campaign Standard
product: campaign
title: 管理 Adobe Experience Platform 受众
description: 了解如何在Campaign Standard内管理Adobe Experience Platform。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 3%

---


# 管理 Adobe Experience Platform 受众 {#about-audiences}

>[!IMPORTANT]
>
>受众目标服务目前处于测试阶段，可能会在不通知的情况下频繁进行更新。 客户必须托管在Azure上（目前仅限北美的beta版），才能访问这些功能。 如果您想要访问，请联系Adobe客户服务中心。

## 访问Adobe Experience Platform受众

要访问Adobe Experience Platform区段构建器，请导航到Campaign Standard主页上的&#x200B;**[!UICONTROL Audiences]**&#x200B;卡（或标题中的&#x200B;**[!UICONTROL Audiences]**&#x200B;链接），然后选择&#x200B;**[!UICONTROL Adobe Experience Platform]**&#x200B;环境。

![](assets/aep_audiences_access.png)

您首先将转到Adobe Experience Platform区段列表页，在该页可访问现有的Adobe Experience Platform区段以进一步编辑。

搜索栏和筛选器可帮助您找到所需的Adobe Experience Platform区段。

![](assets/aep_audiences_list.png)

## 创建Adobe Experience Platform受众

要直接在Campaign Standard中创建Adobe Experience Platform受众，请执行以下步骤：

1. 在Adobe Experience Platform区段列表页中，单击右角的&#x200B;**[!UICONTROL New audience]**&#x200B;按钮。

   ![](assets/aep_audiences_creation_create.png)

1. 区段生成器现在应显示在工作区中。 它允许您使用Adobe Experience Platform的数据构建细分，最终用于创建受众。

1. 在右侧窗格中命名区段并输入说明（可选）。

   ![](assets/aep_audiences_creation_edit_name.png)

1. 要成功创建区段，您必须选择与此区段的营销目的相符的&#x200B;**合并策略**。

   在“设置”窗格中，将选择“平台默认合并策略”。 有关合并策略的详细信息，请参阅[Segment Builder用户指南](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html)中的专用部分。

   ![](assets/aep_audiences_mergepolicy.png)

1. 定义用于标识要在您的用户档案中检索的受众的规则。

   为此，请将所需的属性和／或事件从左窗格拖动到工作区中，定义相应的规则，然后单击&#x200B;**[!UICONTROL Create segment]**&#x200B;按钮以保存区段（请参阅[使用区段生成器](../../audiences/using/aep-using-segment-builder.md)）。

   ![](assets/aep_audiences_creation_query.png)

该受众现在已准备好激活，您可以将其用作活动的目标(请参阅[定位Adobe Experience Platform受众](../../automating/using/aep-targeting-audiences.md))。

## 编辑受众

要编辑受众，请打开它并根据需要在Segment Builder界面中修改规则（请参阅[使用Segment Builder](../../audiences/using/aep-using-segment-builder.md)）。

完成更改后，单击&#x200B;**[!UICONTROL Save segment]**&#x200B;按钮以更新您的受众。

![](assets/aep_audiences_editing.png)
