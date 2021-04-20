---
solution: Campaign Standard
product: campaign
title: 映射定义
description: 了解如何将Campaign Standard字段与体验数据模型(XDM)字段进行映射。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 2%

---


# 映射定义 {#mapping-definition}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector目前处于测试阶段，可能会在不通知的情况下频繁进行更新。 客户需要托管在Azure上（目前仅针对北美）才能访问这些功能。 如果您希望访问，请联系Adobe客户关怀团队。

在本节中，您将了解如何将Campaign Standard字段与体验数据模型(XDM)字段进行映射。

要执行此任务，必须满足以下条件：

* 通过接口或使用与XDM关联的REST API定义XDM模式
* 基于XDM模式定义的数据集创建

1. 转到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]**&#x200B;并选择&#x200B;**[!UICONTROL Data mappings]**&#x200B;条目。

1. 单击&#x200B;**[!UICONTROL Create]**&#x200B;以开始新的XDM映射。

   ![](assets/aep_createmapping.png)

1. 填写必填字段并选择：

   * a **定位维度**:这是要映射的Campaign Standard模式
   * a **数据集**:这是与Adobe Experience Platform中的XDM模式关联的数据包。

>[!NOTE]
>
>要将批量引入实时客户用户档案或身份服务，必须为实时客户用户档案](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/intro/get-started.html)启用[数据集。
>
>如果您选择的数据集已在现有数据映射中使用，则会显示一条警告，通知您您的数据可能会在Adobe Experience Platform上被覆盖。 当使用同一数据集的数据映射中存在一些常见收件人时，可能会发生这种情况。

下面的屏幕显示&#x200B;**[!UICONTROL Field mappings]**&#x200B;部分，您可以在该部分为Campaign Standard模式中的每个字段创建新映射。

![](assets/aep_fieldmappings.png)

**[!UICONTROL Create new field mapping]**&#x200B;按钮允许您在XDM模式中选择Campaign Standard字段和相应的字段路径表达式。

如果您找不到Adobe Campaign Standard字段，则可以使用搜索字段搜索该字段。 目前，搜索仅适用于在层次结构中打开的字段。

![](assets/aep_mapfield.png)

在Campaign Standard中定义的扩展资源被映射为所有本机字段。 它们定义为XDM中的_customer/default扩展。

![](assets/aep_fieldscusmapping.png)

您可以通过API自定义XDM扩展并定义您自己的扩展，以便更好地控制映射。

有关XDM API的详细信息，请参阅[模式注册表API教程](https://docs.adobe.com/content/help/zh-Hans/experience-platform/xdm/api/getting-started.html)。

要映射明细列表字段，您需要使用表达式编辑器定义与XDM值对应的每个明细列表值。 例如，postalAdresfield需要定义为：

![](assets/aep_enummapping.png)

如果XDM值在XDM模式中定义为明细列表，则可以使用本机EXDM函数，该函数将自动替换&#x200B;**lif**&#x200B;语法。

![](assets/aep_enummappingexdm.png)

要编辑XDM映射，请打开它，修改所需信息，然后保存它。

![](assets/aep_editmapping.png)

>[!IMPORTANT]
>
>目前，如果您编辑&#x200B;**[!UICONTROL Field mappings]**&#x200B;部分中的值，然后单击字段外部，则在单击&#x200B;**[!UICONTROL Save]**&#x200B;按钮之前，您的更改不会显示在界面中。 当&#x200B;**[!UICONTROL Field Mappings]**&#x200B;上的编辑是页面上的第一个编辑时，此行为仅发生一次。
