---
title: 使用复合标识关键码调用资源
description: 了解如何使用复合标识键值调用资源
feature: Data Model
role: Developer
level: Experienced
exl-id: c7aca0c3-525d-4195-8c04-2fad32ca43b7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 7%

---

# 使用复合标识关键码调用资源{#calling-a-resource-using-a-composite-identification-key}

在某些情况下，您可能需要为资源定义一个由两个字段组成的标识键。 配置标识键后，您需要配置过滤器定义，以便能够通过Campaign Standard接口或API使用此标识键调用资源。

在此用例中， **用户档案** 使用自定义扩展资源 **&quot;CRM ID&quot;** 和 **&quot;category&quot;** 字段。 我们将为用户档案资源创建标识键，该标识键将由这两个字段组成。 然后，我们将配置过滤器定义，以便我们可以使用标识键访问用户档案资源。

此用例的主要步骤是：

1. 根据这两个字段配置用户档案资源的标识键。
1. 配置过滤器定义，以便能够使用其标识键调用用户档案资源。
1. 从界面或AP中调用用户档案资源。

相关主题：

* [创建或扩展资源](../../developing/using/creating-or-extending-the-resource.md)
* [定义标识键](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [Campaign StandardREST API](../../api/using/get-started-apis.md)

## 步骤1:配置标识键{#step-1-configure-the-identification-key}

>[!NOTE]
> 有关配置标识键时的全局概念，请参阅 [此部分](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).

1. 在配置标识键之前，请确保已使用所需字段扩展资源，并且该资源已发布。 如需详细信息，请参阅[此部分](../../developing/using/creating-or-extending-the-resource.md)。

1. 转到 **[!UICONTROL Administration]** / **[!UICONTROL Development]** / **[!UICONTROL Custom resources]** ，然后打开 **[!UICONTROL Profile]** 资源。

   ![](assets/uc_idkey1.png)

1. 在 **[!UICONTROL Identification keys]** ，单击 **[!UICONTROL Create element]** 按钮。

   ![](assets/uc_idkey2.png)

1. 添加两个自定义“CRM ID”和“类别”字段，然后单击 **[!UICONTROL Confirm]**.

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > 如果要在用户档案的界面中显示两个自定义字段，请配置 **[!UICONTROL Screen definition]** 选项卡。 如需详细信息，请参阅[此部分](../../developing/using/configuring-the-screen-definition.md)。

1. 您现在可以将过滤器定义配置为能够使用其标识键调用资源。

## 步骤2:配置过滤器定义{#step-2-configure-the-filter-definition}

>[!NOTE]
> 有关配置过滤器定义时的全局概念的详细信息，请参阅 [此部分](../../developing/using/configuring-filter-definition.md).

1. 在 **[!UICONTROL Filter definition]** ，单击 **[!UICONTROL Add an element]**，然后输入过滤器定义的标签和ID。

1. 编辑过滤器定义的属性以配置其规则。

   ![](assets/uc_idkey4.png)

1. 将包含标识键中所用字段的表拖放到工作区中。

   ![](assets/uc_idkey5.png)

1. 选择标识键值(“CRM ID”)中使用的第一个字段，然后激活 **[!UICONTROL Switch to parameters]** 选项。

   ![](assets/uc_idkey6.png)

1. 在 **[!UICONTROL Filter conditions]** 部分，保留 **[!UICONTROL Equal]** 运算符，然后定义参数的名称并单击加号以创建该参数。

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > 单击 **+** 按钮，则会自动生成参数的名称。 请注意此信息，因为您需要它才能使用API中的过滤器。

1. 对构成标识键（“类别”）的所有字段重复上述步骤，然后保存更改。

   ![](assets/uc_idkey8.png)

1. 过滤器定义现已配置完成。 您可以发布资源，以使过滤器可用。

## 步骤3:根据资源的标识键调用资源{#step-3-call-the-resource-based-on-its-identification-key}

配置标识键及其过滤器定义后，您可以使用它们从Campaign标准界面或REST API调用资源。

要从界面中使用过滤器定义，请使用 **[!UICONTROL Query]** 活动(请参阅 [此部分](../../automating/using/query.md))。 然后，该过滤器将在左窗格中可用。

![](assets/uc_idkey9.png)

要使用Campaign StandardREST API中的过滤器定义，请使用以下语法：

```
GET /profileAndServicesExt/<resourceName>/by<filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

>[!NOTE]
>要调用自定义过滤器，请使用“by”前缀，后跟在中配置过滤器定义时定义的过滤器名称 [步骤2](../../developing/using/uc-calling-resource-id-key.md#step-2-configure-the-filter-definition).

在本例中，用于使用“123456” CRM ID从“spring”类别中检索用户档案的语法为：

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byidentification_key?category_parameter=spring&crm_id_parameter=123456
```

有关更多详细信息，请参阅 [Campaign StandardREST API文档](../../api/using/filtering.md).
