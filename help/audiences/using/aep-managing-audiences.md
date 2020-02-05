---
title: 管理Adobe Experience platform受众
description: 了解如何在Campaign standard中管理Adobe Experience Platform。
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2ef524d1d276abb1ff0a7149462452cafe8e5cd3

---


# 管理Adobe Experience platform受众 {#about-audiences}

>[!IMPORTANT]
>
>受众目标服务目前处于测试阶段，可能会在不另行通知的情况下频繁进行更新。 客户必须托管在Azure上（目前仅针对北美）才能访问这些功能。 如果您希望访问，请联系Adobe客户关怀。

## 访问Adobe Experience platform受众

要访问Adobe Experience platform区段构建器，请导航到Campaign standard主页上的 **[!UICONTROL Audiences]**卡片（或标题中的链接），然**[!UICONTROL Audiences]** 后选择环 **[!UICONTROL Adobe Experience Platform]**境。

![](assets/aep_audiences_access.png)

您首先将转到Adobe Experience platform区段列表页面，在该页面中可以访问现有的Adobe Experience platform区段以进一步编辑。

搜索栏和筛选器可帮助您找到所需的Adobe Experience Platform区段。

![](assets/aep_audiences_list.png)

## 创建Adobe Experience platform受众

要直接在Campaign standard中创建Adobe Experience platform受众，请执行以下步骤：

1. 从Adobe Experience platform区段列表页面，单 **[!UICONTROL New audience]**击右角的按钮。

   ![](assets/aep_audiences_creation_create.png)

1. 统一的区段生成器现在应显示在工作区中。 它允许您使用Adobe Experience Platform中的数据构建细分，最终用于创建受众。

1. 在右侧窗格中命名区段并输入说明（可选）。

   ![](assets/aep_audiences_creation_edit_name.png)

1. 要成功创建区段，您必须选择与此区段的 **营销目的匹配** 的合并策略。

   在设置窗格中，将选择平台默认合并策略。 有关合并策略的详细信息，请参阅“区段生成器”用户指 [南中的专用部分](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)。

   ![](assets/aep_audiences_mergepolicy.png)

1. 定义用于标识要在受众中检索的档案的规则。

   为此，请将所需的属性和／或事件从左侧窗格拖入工作区，定义相应的规则，然后单击按钮以保存区段(请参阅使 **[!UICONTROL Create segment]**用统一的区段生成器[](../../audiences/using/aep-using-segment-builder.md))。

   ![](assets/aep_audiences_creation_query.png)

受众现在可以激活，您可以将其用作营销活动的目标(请参阅定 [位Adobe Experience platform受众](../../automating/using/aep-targeting-audiences.md))。

## 编辑受众

要编辑受众，请在“统一区段生成器”界面中根据需要打开受众并修改规则(请参 [阅使用统一区段生成器](../../audiences/using/aep-using-segment-builder.md))。

完成更改后，单击按 **[!UICONTROL Save segment]**钮以更新受众。

![](assets/aep_audiences_editing.png)
