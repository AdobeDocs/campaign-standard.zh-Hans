---
solution: Campaign Standard
product: campaign
title: 映射定义
description: 了解如何使用体验Campaign Standard模型(XDM)字段映射体验字段。
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 2%

---


# 映射定义 {#mapping-definition}

>[!IMPORTANT]
>
>Adobe Experience Platform数据连接器目前处于测试阶段，可能会在不通知的情况下频繁进行更新。 客户必须托管在Azure上（目前仅限北美的beta版），才能访问这些功能。 如果您想要访问，请联系Adobe客户服务中心。

在本节中，您将了解如何使用体验数据模型(XDM)字段映射Campaign Standard字段。

要执行此任务，必须满足以下条件：

* 通过接口或使用与XDM关联的REST API定义XDM模式
* 基于XDM模式定义的数据集创建

1. 转到> **[!UICONTROL Administration]** > **[!UICONTROL Development]** 并 **[!UICONTROL Platform]** 选择条 **[!UICONTROL Data mappings]** 目。

1. 单击以 **[!UICONTROL Create]** 开始新的XDM映射。

   ![](assets/aep_createmapping.png)

1. 填写必填字段并选择：

   * **定位维度**:这是Campaign Standard模式
   * 数据 **集**:这是与Adobe Experience Platform的XDM模式关联的数据包。

>[!NOTE]
>
>要将批量引入实时客户用户档案或身份服务，必须启用 [实时客户用户档案数据集](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/intro/get-started.html)。
>
>如果您选择的数据集已在现有数据映射中使用，则会显示一条警告，通知您的数据可能会在Adobe Experience Platform被覆盖。 当使用同一数据集的数据映射中存在一些常见收件人时，可能会发生这种情况。

以下屏幕显示 **[!UICONTROL Field mappings]** 了一节，您可以在该节中为Campaign Standard模式中的每个字段创建新映射。

![](assets/aep_fieldmappings.png)

按 **[!UICONTROL Create new field mapping]** 钮允许您在XDMCampaign Standard中选择表达式字段和相应的字段路径模式。

如果找不到Campaign Standard字段，则可以使用搜索字段搜索该字段。 当前，搜索仅适用于在层次结构中打开的字段。

![](assets/aep_mapfield.png)

Campaign Standard中定义的扩展资源被映射为所有本机字段的样式。 在XDM中，它们被定义为_customer/default扩展。

![](assets/aep_fieldscusmapping.png)

您可以通过API自定义XDM扩展并定义您自己的扩展，从而更好地控制映射。

有关 [XDM API的更多详细信息](https://docs.adobe.com/content/help/zh-Hans/experience-platform/xdm/api/getting-started.html) ，请参阅模式注册表API教程。

要映射明细列表字段，您需要使用表达式编辑器定义与XDM值对应的每个明细列表值。 例如，postalAdressfield需要定义为：

![](assets/aep_enummapping.png)

如果XDM值在XDM模式中定义为明细列表，则可以使用将自动替换lif语法的本机EXDM **函数** 。

![](assets/aep_enummappingexdm.png)

要编辑XDM映射，请打开它，修改所需信息，然后保存它。

![](assets/aep_editmapping.png)

>[!IMPORTANT]
>
>目前，如果您编辑部分中的值， **[!UICONTROL Field mappings]** 然后单击字段外部，则在单击按钮之前，您所做的更改不会显示在界 **[!UICONTROL Save]** 面中。 此行为仅在页面上的第一次 **[!UICONTROL Field Mappings]** 编辑时发生一次。
