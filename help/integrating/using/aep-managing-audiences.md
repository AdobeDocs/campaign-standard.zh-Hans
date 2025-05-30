---
title: 管理 Adobe Experience Platform 受众
description: 了解如何在Campaign Standard中管理Adobe Experience Platform。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 2f6c5cc6-0634-4418-a2ee-e1c133d9cbd2
hide: true
hidefromtoc: true
source-git-commit: 110f3ccb5865e70c78e18485b4ff4ba7a648af3f
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 2%

---

# 管理 Adobe Experience Platform 受众 {#about-audiences}

>[!IMPORTANT]
>
>Audience Destinations Service当前为测试版，可能会频繁更新，恕不另行通知。 客户需要在Azure上托管（目前为仅北美测试版）才能访问这些功能。 如果您希望获得访问权限，请联系Adobe客户关怀团队。

## 访问Adobe Experience Platform受众

要访问Adobe Experience Platform区段生成器，请导航到Campaign Standard主页上的&#x200B;**[!UICONTROL Audiences]**&#x200B;信息卡（或标题中的&#x200B;**[!UICONTROL Audiences]**&#x200B;链接），然后选择&#x200B;**[!UICONTROL Adobe Experience Platform]**&#x200B;环境。

![](assets/aep_audiences_access.png)

您将首先转到Adobe Experience Platform区段列表页面，在该页面中，可以访问现有的Adobe Experience Platform区段进行进一步编辑。

可以使用搜索栏和过滤器来帮助您找到所需的Adobe Experience Platform区段。

![](assets/aep_audiences_list.png)

## 创建Adobe Experience Platform受众

要直接在Campaign Standard中创建Adobe Experience Platform受众，请执行以下步骤：

1. 从Adobe Experience Platform区段列表页面，单击右上角的&#x200B;**[!UICONTROL New audience]**&#x200B;按钮。

   ![](assets/aep_audiences_creation_create.png)

1. 区段生成器现在应会显示在您的工作区中。 它允许您使用Adobe Experience Platform中的数据构建区段，这些数据最终将用于创建受众。

1. 在右侧窗格中命名区段并输入说明（可选）。

   ![](assets/aep_audiences_creation_edit_name.png)

1. 为了成功创建区段，您必须选择与此区段的营销目的相匹配的&#x200B;**合并策略**。

   在设置窗格中，选择Platform默认合并策略。 有关合并策略的更多信息，请参阅[区段生成器用户指南](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=zh-Hans)中的专用部分。

   ![](assets/aep_audiences_mergepolicy.png)

1. 定义用于确定要在受众中检索的用户档案的规则。

   为此，请将所需属性和/或事件从左侧窗格拖到工作区中，定义相应的规则，然后单击&#x200B;**[!UICONTROL Create segment]**&#x200B;按钮以保存区段（请参阅[使用区段生成器](../../integrating/using/aep-using-segment-builder.md)）。

   ![](assets/aep_audiences_creation_query.png)

受众现已准备好激活，您可以将其用作营销活动的目标(请参阅[定向Adobe Experience Platform受众](../../integrating/using/aep-targeting-audiences.md))。

## 编辑受众

要编辑受众，请打开该受众，并根据需要在区段生成器界面中修改规则（请参阅[使用区段生成器](../../integrating/using/aep-using-segment-builder.md)）。

完成更改后，单击&#x200B;**[!UICONTROL Save segment]**&#x200B;按钮以更新受众。

![](assets/aep_audiences_editing.png)
