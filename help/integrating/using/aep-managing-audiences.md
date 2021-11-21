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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 3%

---

# 管理 Adobe Experience Platform 受众 {#about-audiences}

>[!IMPORTANT]
>
>Audience Destinations服务目前处于测试阶段，可能会频繁更新，恕不另行通知。 需要在Azure上托管客户（目前仅适用于北美地区的测试版）才能访问这些功能。 如果您希望访问，请联系Adobe客户关怀团队。

## 访问Adobe Experience Platform受众

要访问Adobe Experience Platform区段生成器，请导航到 **[!UICONTROL Audiences]** Campaign Standard主页上的卡片(或 **[!UICONTROL Audiences]** 链接)，然后选择 **[!UICONTROL Adobe Experience Platform]** 环境。

![](assets/aep_audiences_access.png)

首先，会将您定向到Adobe Experience Platform区段列表页面，在该页面中，可以访问已有的Adobe Experience Platform区段以进一步编辑。

搜索栏和过滤器可帮助您找到所需的Adobe Experience Platform区段。

![](assets/aep_audiences_list.png)

## 创建Adobe Experience Platform受众

要直接在Campaign Standard中创建Adobe Experience Platform受众，请执行以下步骤：

1. 在Adobe Experience Platform区段列表页面中，单击 **[!UICONTROL New audience]** 按钮。

   ![](assets/aep_audiences_creation_create.png)

1. 现在，区段生成器应会显示在您的工作区中。 利用此功能，可使用Adobe Experience Platform中的数据构建区段，最终将用于创建受众。

1. 在右侧窗格中命名区段并输入描述（可选）。

   ![](assets/aep_audiences_creation_edit_name.png)

1. 要成功创建区段，您必须选择 **合并策略** 与此区段的营销目的相匹配。

   在设置窗格中，选择平台默认合并策略。 有关合并策略的更多信息，请参阅 [区段生成器用户指南](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html).

   ![](assets/aep_audiences_mergepolicy.png)

1. 定义规则以标识要在受众中检索的用户档案。

   要实现此目的，请将所需的属性和/或事件从左侧窗格拖入工作区中，定义相应的规则，然后单击 **[!UICONTROL Create segment]** 按钮以保存区段(请参阅 [使用区段生成器](../../integrating/using/aep-using-segment-builder.md))。

   ![](assets/aep_audiences_creation_query.png)

受众现已准备就绪，可将其用作营销活动的目标(请参阅 [定位Adobe Experience Platform受众](../../integrating/using/aep-targeting-audiences.md))。

## 编辑受众

要编辑受众，请根据需要在区段生成器界面中打开并修改规则(请参阅 [使用区段生成器](../../integrating/using/aep-using-segment-builder.md))。

完成更改后，单击 **[!UICONTROL Save segment]** 按钮来更新受众。

![](assets/aep_audiences_editing.png)
