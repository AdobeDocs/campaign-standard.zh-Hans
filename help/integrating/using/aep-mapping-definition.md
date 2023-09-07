---
title: 映射定义
description: 了解如何使用Campaign Standard数据模型(XDM)字段映射体验字段。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 6383ddbe-922a-4363-a1da-166cf717b0dd
hide: true
hidefromtoc: true
source-git-commit: 110f3ccb5865e70c78e18485b4ff4ba7a648af3f
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 0%

---

# 映射定义 {#mapping-definition}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector目前处于测试阶段，可能会频繁更新，恕不另行通知。 客户需要在Azure上托管（目前为仅北美测试版）才能访问这些功能。 如果您希望获得访问权限，请联系Adobe客户关怀团队。

在此部分中，您将了解如何使用Experience Data Model (XDM)字段映射Campaign Standard字段。

要执行此任务，必须满足以下条件：

* 通过接口或使用与XDM关联的REST API来定义XDM架构
* 基于XDM模式定义的数据集创建

1. 转到 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** 并选择 **[!UICONTROL Data mappings]** 进入。

1. 单击 **[!UICONTROL Create]** 以启动新的XDM映射。

   ![](assets/aep_createmapping.png)

1. 填写必填字段并选择：

   * a **定位维度**：这是要映射的Campaign Standard架构
   * a **数据集**：这是与Adobe Experience Platform中的XDM架构关联的数据包。

>[!NOTE]
>
>对于要摄取到Real-time Customer Profile或Identity Service的批次，数据集必须是 [启用实时客户资料](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/intro/get-started.html).
>
>如果您选择的数据集已在现有数据映射中使用，则会出现一条警告，通知您可能会在Adobe Experience Platform上覆盖您的数据。 当使用同一数据集的数据映射中存在一些常见收件人时，可能会发生此情况。

以下屏幕显示 **[!UICONTROL Field mappings]** 部分，从中可为Campaign Standard架构中的每个字段创建新映射。

![](assets/aep_fieldmappings.png)

此 **[!UICONTROL Create new field mapping]** 按钮允许您选择XDM架构中的Campaign Standard字段和相应的字段路径表达式。

如果您无法找到Adobe Campaign Standard字段，则可以使用该搜索字段搜索该字段。 目前，搜索仅适用于层次结构中打开的字段。

![](assets/aep_mapfield.png)

在Campaign Standard中定义的扩展资源被映射为喜欢所有本地字段。 它们被定义到XDM中的_customer/default扩展中。

![](assets/aep_fieldscusmapping.png)

您可以通过API自定义XDM扩展，并定义您自己的扩展，以便更好地控制映射。

请参阅 [架构注册表API教程](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html) 了解有关XDM API的更多详细信息。

要映射枚举字段，需要使用表达式编辑器定义与XDM值对应的每个枚举值。 例如，postaladdressfield需要定义为：

![](assets/aep_enummapping.png)

如果XDM值在XDM架构中定义为枚举，则可以使用自动替换 **lif** 语法。

![](assets/aep_enummappingexdm.png)

要编辑XDM映射，请打开它，修改所需信息，然后保存它。

![](assets/aep_editmapping.png)

>[!IMPORTANT]
>
>现在，如果您在 **[!UICONTROL Field mappings]** 部分，然后单击字段外部，则在单击 **[!UICONTROL Save]** 按钮。 此行为仅发生一次，当编辑 **[!UICONTROL Field Mappings]** 是页面上的第一次编辑。
