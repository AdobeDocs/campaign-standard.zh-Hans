---
solution: Campaign Standard
product: campaign
title: 使用复合标识关键码调用资源
description: 了解如何使用组合标识密钥调用资源
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 7%

---


# 使用复合标识关键码调用资源{#calling-a-resource-using-a-composite-identification-key}

在某些情况下，您可能需要为资源定义由两个字段组成的标识密钥。 配置标识密钥后，您需要配置过滤器定义，以便能够从Campaign Standard接口或API调用此标识密钥的资源。

在此用例中， **用户档案** 资源已通过自 **定义** “CRM ID”和“ **类别”字段进** 行扩展。 我们将为用户档案资源创建一个标识密钥，由这两个字段组成。 然后，我们将配置一个筛选器定义，以便我们能够使用标识密钥访问用户档案资源。

此用例的主要步骤是：

1. 根据这两个字段配置用户档案资源的标识密钥。
1. 配置筛选器定义，以便能够使用其标识密钥调用用户档案资源。
1. 从接口或AP调用用户档案资源。

相关主题：

* [创建或扩展资源](../../developing/using/creating-or-extending-the-resource.md)
* [定义标识键](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [Campaign StandardREST API](../../api/using/get-started-apis.md)

## 第1步：配置标识密钥{#step-1-configure-the-identification-key}

>[!NOTE]
> 配置标识密钥时的全局概念在本节中 [有详细介绍](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)。

1. 在配置标识密钥之前，请确保资源已扩展到所需字段，并且已发布。 如需详细信息，请参阅[此部分](../../developing/using/creating-or-extending-the-resource.md)。

1. 转到/ **[!UICONTROL Administration]** / **[!UICONTROL Developement]** 菜单 **[!UICONTROL Custom resources]** ，然后打开 **[!UICONTROL Profile]** 资源。

   ![](assets/uc_idkey1.png)

1. In the **[!UICONTROL Identification keys]** section, click the **[!UICONTROL Create element]** button.

   ![](assets/uc_idkey2.png)

1. 添加两个自定义“CRM ID”和“类别”字段，然后单击 **[!UICONTROL Confirm]**。

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > 如果要在用户档案界面中显示两个自定义字段，请配置选 **[!UICONTROL Screen definition]** 项卡。 如需详细信息，请参阅[此部分](../../developing/using/configuring-the-screen-definition.md)。

1. 您现在可以配置筛选器定义，以便能够使用其标识密钥调用资源。

## 第2步：配置筛选器定义{#step-2-configure-the-filter-definition}

>[!NOTE]
> 配置筛选器定义时的全局概念在本节中 [有详细介绍](../../developing/using/configuring-filter-definition.md)。

1. 在选项卡 **[!UICONTROL Filter definition]** 中，单 **[!UICONTROL Add an element]**&#x200B;击，然后输入筛选器定义的标签和ID。

1. 编辑筛选器定义的属性以配置其规则。

   ![](assets/uc_idkey4.png)

1. 将包含标识键中使用的字段的表拖放到工作区中。

   ![](assets/uc_idkey5.png)

1. 选择标识密钥(“CRM ID”)中使用的第一个字段，然后激活选 **[!UICONTROL Switch to parameters]** 项。

   ![](assets/uc_idkey6.png)

1. 在部 **[!UICONTROL Filter conditions]** 分中，保留运 **[!UICONTROL Equal]** 算符，然后定义参数的名称并单击加号以创建它。

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > 单击+按 **钮** 后，将自动生成参数的名称。 请注意此信息，因为您需要它才能使用API中的筛选器。

1. 对构成标识键的所有字段重复上述步骤(“类别”)，然后保存更改。

   ![](assets/uc_idkey8.png)

1. 现在已配置筛选器定义。 您可以发布资源，以便筛选器可用。

## 第3步：根据资源的标识密钥调用资源{#step-3-call-the-resource-based-on-its-identification-key}

一旦配置了标识密钥及其筛选器定义，您就可以使用它们从活动标准接口或REST API调用资源。

要从界面中使用筛选器定义，请在工 **[!UICONTROL Query]** 作流中使用活动(请 [参阅本节](../../automating/using/query.md))。 过滤器随后在左窗格中可用。

![](assets/uc_idkey9.png)

要使用Campaign StandardREST API中的筛选器定义，请使用以下语法：

```
GET /profileAndServicesExt/<resourceName>/by<filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

>[!NOTE]
>要调用自定义筛选器，请使用“by”前缀，后跟在步骤2中配置筛选器定义时定义的筛 [选器名称](../../developing/using/uc-calling-resource-id-key.md#step-2-configure-the-filter-definition)。

在本例中，用“123456”CRM ID从“spring”用户档案检索类别的语法为：

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byidentification_key?category_parameter=spring&crm_id_parameter=123456
```

有关详细信息，请参阅 [Campaign StandardREST API文档](../../api/using/filtering.md)。