---
solution: Campaign Standard
product: campaign
title: 使用复合标识关键码调用资源
description: 了解如何使用复合标识密钥调用资源
feature: 数据模型
role: 开发人员
level: 富有经验
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 7%

---


# 使用复合标识关键码调用资源{#calling-a-resource-using-a-composite-identification-key}

在某些情况下，您可能需要为资源定义由两个字段组成的标识密钥。 配置标识密钥后，您需要配置过滤器定义，以便能够从Campaign Standard接口或API中使用此标识密钥调用资源。

在此用例中，**用户档案**&#x200B;资源已扩展为自定义&#x200B;**&quot;CRM ID&quot;**&#x200B;和&#x200B;**&quot;类别&quot;**&#x200B;字段。 我们将为用户档案资源创建一个标识密钥，由这两个字段组成。 然后，我们将配置过滤器定义，以便我们能够使用标识密钥访问用户档案资源。

此用例的主要步骤是：

1. 根据这两个字段配置用户档案资源的标识密钥。
1. 配置用户档案定义，以便能够使用其标识密钥调用筛选器资源。
1. 从接口或APi调用用户档案资源。

相关主题：

* [创建或扩展资源](../../developing/using/creating-or-extending-the-resource.md)
* [定义标识键](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [Campaign StandardREST API](../../api/using/get-started-apis.md)

## 第1步：配置标识密钥{#step-1-configure-the-identification-key}

>[!NOTE]
> 配置标识键时的全局概念在[本节](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)中有详细介绍。

1. 在配置标识密钥之前，请确保资源已扩展到所需的字段并且已发布。 如需详细信息，请参阅[此部分](../../developing/using/creating-or-extending-the-resource.md)。

1. 转到&#x200B;**[!UICONTROL Administration]** / **[!UICONTROL Development]** / **[!UICONTROL Custom resources]**&#x200B;菜单，然后打开&#x200B;**[!UICONTROL Profile]**&#x200B;资源。

   ![](assets/uc_idkey1.png)

1. 在&#x200B;**[!UICONTROL Identification keys]**&#x200B;部分，单击&#x200B;**[!UICONTROL Create element]**&#x200B;按钮。

   ![](assets/uc_idkey2.png)

1. 添加两个自定义“CRM ID”和“类别”字段，然后单击&#x200B;**[!UICONTROL Confirm]**。

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > 如果要在用户档案的接口中显示两个自定义字段，请配置&#x200B;**[!UICONTROL Screen definition]**&#x200B;选项卡。 如需详细信息，请参阅[此部分](../../developing/using/configuring-the-screen-definition.md)。

1. 您现在可以配置筛选器定义，以便能够使用其标识键调用资源。

## 第2步：配置筛选器定义{#step-2-configure-the-filter-definition}

>[!NOTE]
> 配置筛选器定义时的全局概念在[本节](../../developing/using/configuring-filter-definition.md)中有详细介绍。

1. 在&#x200B;**[!UICONTROL Filter definition]**&#x200B;选项卡中，单击&#x200B;**[!UICONTROL Add an element]**，然后输入筛选器定义的标签和ID。

1. 编辑筛选器定义的属性以配置其规则。

   ![](assets/uc_idkey4.png)

1. 将包含在标识键中使用的字段的表拖放到工作区中。

   ![](assets/uc_idkey5.png)

1. 选择标识键(“CRM ID”)中使用的第一个字段，然后激活&#x200B;**[!UICONTROL Switch to parameters]**&#x200B;选项。

   ![](assets/uc_idkey6.png)

1. 在&#x200B;**[!UICONTROL Filter conditions]**&#x200B;部分，保留&#x200B;**[!UICONTROL Equal]**&#x200B;运算符，然后定义参数的名称并单击加号创建它。

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > 单击&#x200B;**+**&#x200B;按钮后，将自动生成参数的名称。 请注意此信息，因为您需要它才能使用API中的筛选器。

1. 对构成标识键的所有字段重复上述步骤(“类别”)，然后保存更改。

   ![](assets/uc_idkey8.png)

1. 现在已配置筛选器定义。 您可以发布资源，以使过滤器可用。

## 第3步：根据资源的标识密钥{#step-3-call-the-resource-based-on-its-identification-key}调用资源

配置标识密钥及其筛选器定义后，您可以使用它们从活动标准接口或REST API调用资源。

要使用接口中的筛选器定义，请在工作流中使用&#x200B;**[!UICONTROL Query]**&#x200B;活动（请参阅[本节](../../automating/using/query.md)）。 然后，左窗格中会显示该过滤器。

![](assets/uc_idkey9.png)

要使用Campaign Standard REST API中的过滤器定义，请使用以下语法：

```
GET /profileAndServicesExt/<resourceName>/by<filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

>[!NOTE]
>要调用自定义筛选器，请使用“by”前缀，后跟在[步骤2](../../developing/using/uc-calling-resource-id-key.md#step-2-configure-the-filter-definition)中配置筛选器定义时定义的筛选器名称。

在本例中，用于从“spring”用户档案检索带有“123456”CRM ID的类别的语法为：

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byidentification_key?category_parameter=spring&crm_id_parameter=123456
```

有关详细信息，请参阅[Campaign StandardREST API文档](../../api/using/filtering.md)。