---
solution: Campaign Standard
product: campaign
title: 映射定义
description: 了解如何使用体验Campaign Standard模型(XDM)字段映射体验字段。
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 2729852365a2e74d2a603d95f75285fe54313e71
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

1. 转到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]**&#x200B;并选择&#x200B;**[!UICONTROL Data mappings]**&#x200B;条目。

1. 单击&#x200B;**[!UICONTROL Create]**&#x200B;以开始新的XDM映射。

   ![](assets/aep_createmapping.png)

1. 填写必填字段并选择：

   * a **定位维度**:这是Campaign Standard模式
   * a **数据集**:这是与Adobe Experience Platform的XDM模式关联的数据包。

>[!NOTE]
>
>要将批量引入实时客户用户档案或身份服务，数据集必须[启用实时客户用户档案](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/intro/get-started.html)。
>
>如果您选择的数据集已在现有数据映射中使用，则会显示一条警告，通知您的数据可能会在Adobe Experience Platform被覆盖。 当使用同一数据集的数据映射中存在一些常见收件人时，可能会发生这种情况。

以下屏幕显示&#x200B;**[!UICONTROL Field mappings]**&#x200B;部分，您可以在该部分为Campaign Standard模式中的每个字段创建新映射。

![](assets/aep_fieldmappings.png)

**[!UICONTROL Create new field mapping]**&#x200B;按钮允许您在XDMCampaign Standard中选择表达式字段和相应的字段路径。

如果找不到Adobe Campaign Standard字段，则可以使用搜索字段搜索该字段。 当前，搜索仅适用于在层次结构中打开的字段。

![](assets/aep_mapfield.png)

Campaign Standard中定义的扩展资源被映射为所有本机字段的样式。 在XDM中，它们被定义为_customer/default扩展。

![](assets/aep_fieldscusmapping.png)

您可以通过API自定义XDM扩展并定义您自己的扩展，从而更好地控制映射。

有关XDM API的详细信息，请参阅[模式注册表API教程](https://docs.adobe.com/content/help/zh-Hans/experience-platform/xdm/api/getting-started.html)。

要映射明细列表字段，您需要使用表达式编辑器定义与XDM值对应的每个明细列表值。 例如，postalAdressfield需要定义为：

![](assets/aep_enummapping.png)

如果XDM值在XDM模式中定义为明细列表，则可以使用本机EXDM函数，该函数将自动替换&#x200B;**lif**&#x200B;语法。

![](assets/aep_enummappingexdm.png)

要编辑XDM映射，请打开它，修改所需信息，然后保存它。

![](assets/aep_editmapping.png)

>[!IMPORTANT]
>
>目前，如果您编辑&#x200B;**[!UICONTROL Field mappings]**&#x200B;部分中的值，然后单击字段外部，则在单击&#x200B;**[!UICONTROL Save]**&#x200B;按钮之前，您所做的更改不会显示在界面中。 当&#x200B;**[!UICONTROL Field Mappings]**&#x200B;上的编辑是页面上的第一个编辑时，此行为只发生一次。
