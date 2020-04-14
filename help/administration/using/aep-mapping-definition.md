---
title: 映射定义
description: 了解如何使用体验数据模型(XDM)字段映射Campaign Standard字段。
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 57b87896281efa7dd1e6a612926f59061a0fdcb8

---


# 映射定义 {#mapping-definition}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector目前处于测试阶段，可能会在不另行通知的情况下频繁进行更新。 客户必须托管在Azure上（目前仅针对北美）才能访问这些功能。 如果您希望访问，请联系Adobe客户关怀。

在本节中，您将了解如何将Campaign Standard字段与体验数据模型(XDM)字段进行映射。

要执行此任务，先决条件是：

* 通过接口或使用与XDM关联的REST API定义XDM模式
* 基于XDM模式定义的数据集创建

1. 转到 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** 并选择 **[!UICONTROL Data mappings]** 条目。

1. 单击以 **[!UICONTROL Create]** 开始新的XDM映射。

   ![](assets/aep_createmapping.png)

1. 填写必填字段，然后选择：

   * a **定位维度**:这是Campaign Standard模式
   * 数据 **集**:这是与Adobe Experience Platform中的XDM模式关联的数据包。

>[!NOTE]
>
>要将批量引入实时客户用户档案或标识服务，必须为实时客 [户用户档案启用数据集](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/intro/get-started.html)。
>
>如果您选择的数据集已在现有数据映射中使用，则会显示一条警告，通知您的数据可能会被Adobe Experience Platform覆盖。 当使用同一数据集的数据映射中存在一些常见收件人时，可能会发生这种情况。

以下屏幕显示了一 **[!UICONTROL Field mappings]** 节，您可以在该节中为Campaign Standard模式中的每个字段创建新映射。

![](assets/aep_fieldmappings.png)

通过 **[!UICONTROL Create new field mapping]** 该按钮，您可以在XDMCampaign Standard中选择表达式字段和相应的字段路径模式。

如果找不到Campaign Standard字段，则可以使用搜索字段搜索该字段。 当前，搜索仅适用于在层次结构中打开的字段。

![](assets/aep_mapfield.png)

在Campaign Standard中定义的扩展资源被映射为对所有本机字段的赞同。 它们定义为XDM中的_customer/default扩展。

![](assets/aep_fieldscusmapping.png)

您可以通过API自定义XDM扩展，并定义自己的扩展，以便更好地控制映射。

有关XDM [API的更多详细信息](https://docs.adobe.com/content/help/en/experience-platform/xdm/api/getting-started.html) ，请参阅模式注册表API教程。

要映射明细列表字段，您需要使用表达式编辑器来定义与XDM值对应的每个明细列表值。 例如，postalAdressfield需要定义为：

![](assets/aep_enummapping.png)

如果XDM值在XDM模式中定义为明细列表，则可以使用将自动替换lif语法的本机EXDM函 **数** 。

![](assets/aep_enummappingexdm.png)

要编辑XDM映射，请打开它，修改所需的信息，然后保存它。

![](assets/aep_editmapping.png)

>[!IMPORTANT]
>
>目前，如果您在部分中编辑一个值，然后在字段外部单 **[!UICONTROL Field mappings]** 击，则在单击按钮之前，您所做的更改不会显示在界面 **[!UICONTROL Save]** 中。 此行为仅在页面上的编辑是第 **[!UICONTROL Field Mappings]** 一次编辑时发生一次。
