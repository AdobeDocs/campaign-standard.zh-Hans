---
title: 使用复合标识键调用资源
seo-title: 使用复合标识键调用资源
description: 使用复合标识键调用资源
seo-description: 了解如何使用复合标识密钥调用资源
translation-type: tm+mt
source-git-commit: ff9861a2b8a59843cc668cec9f89b9ea76822d66

---


# 使用复合标识键调用资源

在某些情况下，您可能需要为某个资源定义由两个字段组成的标识密钥。配置标识密钥后，您需要配置过滤器定义，以便能够使用此标识密钥从Campaign Standard界面或API调用资源。

在此用例中， **配置文件** 资源已通过自定义 **“CRM ID”** 和 **“category”** 字段扩展。我们将为配置文件资源创建一个标识密钥，该密钥由这两个字段组成。然后，我们将配置过滤器定义，以便我们可以使用标识密钥访问配置文件资源。

此用例的主要步骤有：

1. 根据两个字段配置配置文件资源的标识密钥。
1. 配置过滤器定义，以便能够使用其标识密钥调用配置文件资源。
1. 从界面或API调用配置文件资源。

相关主题：

* [创建或扩展资源](../../developing/using/creating-or-extending-the-resource.md)
* [定义标识密钥](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [Campaign Standard REST API](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)

## 步骤1：配置标识密钥

>[!NOTE]
> 此部分详细介绍了配置标识密钥时的全局 [概念](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)。

1. 在配置标识密钥之前，请确保已使用所需的字段扩展资源，并且已发布该字段。For more on this, refer to [this section](../../developing/using/creating-or-extending-the-resource.md).

1. 转到 **[!UICONTROL Administration]** / **[!UICONTROL Developement]****[!UICONTROL Custom resources]** /菜单，然后打开 **[!UICONTROL Profile]** 资源。

   ![](assets/uc_idkey1.png)

1. **[!UICONTROL Identification keys]** 在部分中，单击 **[!UICONTROL Create element]** 按钮。

   ![](assets/uc_idkey2.png)

1. 添加两个自定义“CRM ID”和“类别”字段，然后单击 **[!UICONTROL Confirm]**。

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > 如果要在配置文件的界面中显示两个自定义字段，请配置 **[!UICONTROL Screen definition]** 该选项卡。For more on this, refer to [this section](../../developing/using/configuring-the-screen-definition.md).

1. 您现在可以配置过滤器定义，以使用其标识密钥调用资源。

## 步骤2：配置过滤器定义

>[!NOTE]
> 此部分详细介绍了配置过滤器定义时的全局 [概念](../../developing/using/configuring-filter-definition.md)。

1. 在 **[!UICONTROL Filter definition]** 选项卡中，单击 **[!UICONTROL Add an element]**，然后输入过滤器定义的标签和ID。

1. 编辑过滤器定义的属性以配置其规则。

   ![](assets/uc_idkey4.png)

1. 拖放到工作区中，该表包含标识键中使用的字段。

   ![](assets/uc_idkey5.png)

1. 选择识别密钥(“CRM ID”)中使用的第一个字段，然后激活 **[!UICONTROL Switch to parameters]** 该选项。

   ![](assets/uc_idkey6.png)

1. **[!UICONTROL Filter conditions]** 在部分中，保留 **[!UICONTROL Equal]** 运算符，然后定义参数的名称并单击加号以创建它。

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > 单击加号按钮后，会自动生成参数的名称。请注意此信息，因为您需要它使用API中的过滤器。

1. 在以上步骤中重复执行识别密钥(“类别”)的所有步骤，然后保存更改。

   ![](assets/uc_idkey8.png)

1. 过滤器定义现已配置。您可以发布资源以使筛选器可用。

## 步骤3：根据其标识密钥调用资源

配置识别密钥及其过滤器定义后，您可以使用营销活动标准界面或REST API调用资源。

要使用界面中的过滤器定义，请使用工作流中的 **[!UICONTROL Query]** 活动(请参阅 [此部分](../../automating/using/query.md))。随后，该过滤器便会在左窗格中可用。

![](assets/uc_idkey9.png)

要使用Campaign Standard REST API中的过滤器定义，请使用以下语法：

```
GET /profileAndServicesExt/<resourceName><filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

在我们的情况下，从“Spring”类别检索配置文件并使用“123456”CRM ID的语法将是：

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/identification_key?category_parameter=spring&crm_id_parameter=123456
```

有关详细信息，请参阅 [Campaign Standard REST API文档](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#filtering)。