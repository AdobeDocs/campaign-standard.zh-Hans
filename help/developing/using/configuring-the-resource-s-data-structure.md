---
title: 配置资源的数据结构
seo-title: 配置资源的数据结构
description: 配置资源的数据结构
seo-description: 了解如何配置数据结构。
page-status-flag: 从未激活
uuid: 60fe80c0-9df6-4808-a432-60a1977216 a
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 4f22ee35-1d5f-4c75-95b4-3e38b85e28e
context-tags: CusResource，main
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 888cf4cd7bfa7f82bfe70c408f8c2785c51c36e2

---


# 配置资源的数据结构{#configuring-the-resource-s-data-structure}

创建新的自定义资源后，必须配置数据结构。

编辑资源时， **[!UICONTROL Data structure]** 在选项卡中，您可以添加：

* [Fields](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource)
* [标识键](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [索引](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes)
* [链接](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources)
* [发送日志](../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension)

## 将字段添加到资源 {#adding-fields-to-a-resource}

您可以向资源添加新字段，以存储不属于现成数据模型之外的数据。

1. 使用 **[!UICONTROL Create element]** 按钮创建字段。
1. 指定标签、ID、字段类型并定义为此字段授权的最大长度。

   字段为 **[!UICONTROL ID]** 必填字段，对于添加的每个字段都必须是唯一的。

   >[!NOTE]
   >
   >如果将 **[!UICONTROL Label]** 字段留空，将从ID自动完成该字段。
   >建议使用30个字符最大值。

   ![](assets/schema_extension_4.png)

1. 要修改其中一个字段，请选中 **[!UICONTROL Edit Properties]** 按钮。

   ![](assets/schema_extension_24.png)

1. **[!UICONTROL Field definition]** 在屏幕中，您可以定义用于受众和定位的类别，甚至添加描述。

   ![](assets/schema_extension_5.png)

1. 如果您需要定义将向用户提供的值(枚举值)，请选中 **[!UICONTROL Specify a list of authorized values]** 此选项。

   然后，单击 **[!UICONTROL Create element]** 并指定一个 **[!UICONTROL Label]** 和 **[!UICONTROL Value]**。根据需要添加任意数量的值。

1. 添加字段后，请选中 **[!UICONTROL Add audit fields]** 相应的框，以包括创建日期的字段、创建资源的用户、日期以及上次修改的作者。
1. 选中 **[!UICONTROL Add access authorization management fields]** 此复选框，以包含指示谁有权访问该特定资源的字段。

   这些字段显示在数据和元数据中，这些字段在执行数据库更新后可显示。有关此操作的详细信息，请参阅 [更新数据库结构](../../developing/using/updating-the-database-structure.md) 部分。

1. 选中 **[!UICONTROL Add automatic ID]** 此字段可自动生成ID。请注意，现有实体将保留为空。
1. 要修改资源元素名称将在列表和创建步骤中显示的方式，请选中 **[!UICONTROL Personalize the resource title]** 框。从为此资源创建的字段中选择一个字段。

   ![](assets/schema_extension_18.png)

此时将定义资源的字段。

## 定义标识密钥 {#defining-identification-keys}

每个资源必须至少具有一个唯一密钥。例如，您可以指定一个密钥，以便两个产品在购买表中没有相同的ID。

1. 如果您希望自动和递增生成技术密钥，请在 **[!UICONTROL Automatic primary key]** 部分中指定存储大小。

   ![](assets/schema_extension_6.png)

1. 使用 **[!UICONTROL Create element]** 按钮创建键。

   默认情况下，这些字段 **[!UICONTROL Label]** 和 **[!UICONTROL ID]** 字段已完成，但您可以编辑它们。

   >[!NOTE]
   >
   >建议使用30个字符最大值。

1. 要定义组成此键的元素，请单击 **[!UICONTROL Create element]** 并选择您为此资源创建的字段。

   ![](assets/schema_extension_7.png)

   创建的键将显示在 **[!UICONTROL Custom keys]** 章节中。

此时会创建资源的标识密钥。

## 定义索引 {#defining-indexes}

索引可引用一个或多个资源字段。索引允许数据库对记录进行排序，以便更轻松地恢复它们。它们优化SQL查询的性能。

建议定义索引，但不是强制定义索引。

1. 使用 **[!UICONTROL Create element]** 按钮创建索引。

   ![](assets/schema_extension_26.png)

1. 默认情况下，这些字段 **[!UICONTROL Label]** 和 **[!UICONTROL ID]** 字段已完成，但您可以编辑它们。

   >[!NOTE]
   >
   >建议使用30个字符最大值。

1. 要定义构成此索引的元素，请从为该资源创建的字段中选择字段。

   ![](assets/schema_extension_27.png)

1. Click **[!UICONTROL Confirm]**.

创建的索引将显示在 **[!UICONTROL Index]** 该部分的列表中。

## 定义与其他资源的链接 {#defining-links-with-other-resources}

链接详细说明了一个表与其他表的关联情况。

1. 使用 **[!UICONTROL Create element]** 按钮创建指向目标资源的链接。
1. Click **[!UICONTROL Select a target resource]**.

   ![](assets/schema_extension_28.png)

1. 资源以字母顺序显示，并且可以按名称筛选。他们的技术名称将显示在括号中。

   从列表中选择一个元素，然后单击 **[!UICONTROL Confirm]**。

   ![](assets/schema_extension_9.png)

1. 根据 **[!UICONTROL Link type]** 基数选择。根据所选基数类型，如果记录被删除或重复，则行为可能会有所不同。

   各种链接类型如下所示：

   * **[!UICONTROL 1 cardinality simple link]**：源表的一个出现最多可能有目标表的相应出现。
   * **[!UICONTROL N cardinality collection link]**：源表的一个出现可能有多个对应的目标表发生情况，但目标表的一个出现可能会有源表的最多一个相应的实例。
   * **[!UICONTROL 0 or 1 cardinality simple link]**：源表的一个出现可能具有目标表或无的大多数对应的出现。请注意，这种类型 **[!UICONTROL Link type]** 可能会导致性能问题。
   ![](assets/schema_extension_29.png)

1. **[!UICONTROL New link]** 在屏幕中，默认 **[!UICONTROL Label]** 情况下，这些和 **[!UICONTROL ID]** 字段是完成的，但是您可以编辑它们。

   >[!NOTE]
   >
   >建议使用30个字符最大值。

   >[!CAUTION]
   >
   >创建后重命名链接不可能。要重命名链接，必须将其删除并重新创建。

1. **[!UICONTROL Category for the audience and targeting]** 该列表允许您将此链接分配给类别，使其在查询编辑器工具中更可见。
1. 如果需要， **[!UICONTROL Reverse link definition]** 该部分允许您在目标资源中显示资源的标签和ID。
1. 定义 **[!UICONTROL Behavior if deleted/duplicated]** 部分中链接引用的记录的行为。

   默认情况下，链接不再引用目标记录后，将删除目标记录。

   ![](assets/schema_extension_16.png)

1. **[!UICONTROL Join definition]** 在该部分中，选择了默认 **[!UICONTROL Use the primary keys to make the join]** 选项，但您可以在以下两个选项之间进行选择：

   * **[!UICONTROL Use the primary key to make the join]**：此加入定义允许您使用配置文件主要密钥与购买的主要密钥协调。
   * **[!UICONTROL Define specific join conditions]**：此加入定义允许您手动选择将加入两个资源的字段。请注意，如果数据未正确配置， **则不会显示购买** 记录。
   ![](assets/schema_extension_17.png)

创建的链接将显示在 **[!UICONTROL Links]** 该部分的列表中。

**示例：将创建的资源与“配置文件”资源链接**

在此示例中，我们希望将新的资源 **购买** 与 **配置文件** 自定义资源相链接：

1. 创建新 **的购买** 资源。
1. 要将其与 **配置文件** 自定义资源链接，请取消选择选项卡中的 **[!UICONTROL Links]****[!UICONTROL Data structure]** 章节并单击 **[!UICONTROL Create element]**。
1. 在此处选择目标资源 **[!UICONTROL Profiles (profile)]**。
1. 在此示例中，保持选中 **[!UICONTROL 1 cardinality simple link]** 的链接类型。

   ![](assets/custom_resource_link_to_profile_2.png)

1. 选择加入定义，此处保留默认 **[!UICONTROL Use the primary key to make the join]**&#x200B;值。

   ![](assets/custom_resource_link_to_profile_3.png)

1. 如果需要，您可以定义详细信息屏幕，以编辑 **购买并** 将其链接到配置文件。

   取消设置 **[!UICONTROL Detail screen configuration]** 该部分并检查用于 **[!UICONTROL Define a detail screen]** 配置与资源每个元素对应的屏幕的屏幕。如果不选中此框，则无法访问此资源元素的详细信息视图。

1. Click **[!UICONTROL Create element]**.
1. 选择链接的资源，然后单击 **[!UICONTROL Add]**。

   您的新资源随后将通过选择 **[!UICONTROL Client data]** &gt; **[!UICONTROL Purchase]**&#x200B;在高级菜单中可用。

   ![](assets/custom_resource_link_to_profile_4.png)

1. 配置完成后，单击 **[!UICONTROL Confirm]**。

   您现在可以发布新资源。

通过添加此链接， **将** 从 **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Profiles]** 菜单中将购买选项卡添加到配置文件详细信息屏幕。请注意，这是 **[!UICONTROL Profile]** 特定于资源的。

![](assets/custom_resource_link_to_profile.png)

## 定义发送日志扩展 {#defining-sending-logs-extension}

发送日志扩展允许您：

* 通过 **添加配置文件自定义字段来扩展动态报告功能**
* 用 **区段代码和配置文件数据扩展发送日志数据**

**使用区段代码扩展**

用户可以使用来自工作流引擎的区段代码扩展日志。

必须将区段代码定义为工作流。

要激活此扩展，请选中此选项 **[!UICONTROL Add segment code]**。

![](assets/sendinglogsextension_1.png)

有关区段代码的详细信息，请参阅 [分段](../../automating/using/segmentation.md) 部分。

**扩展配置文件字段**

>[!NOTE]
>
>管理员应使用自定义字段扩展配置文件资源。

![](assets/sendinglogsextension_2.png)

单击 **[!UICONTROL Add field]** 并从配置文件资源中选择任意自定义字段。

要生成链接到配置文件维度的新子维度，请选中 **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** 该选项。

![](assets/sendinglogsextension_3.png)

通过动态报告，您可以将自定义字段维度拖放到自由表单中。

有关动态报告的详细信息，请参阅组件 [列表](../../reporting/using/list-of-components-.md)。

>[!CAUTION]
>
>发送到动态报告的字段数量仅限20个。

## 编辑资源属性 {#editing-resource-properties}

在自定义资源屏幕中 **[!UICONTROL Summary]** ，窗格指示新创建的资源的状态。您可以管理其访问权限及其常规属性。

![](assets/schema_extension_3.png)

1. 单击 **[!UICONTROL Edit properties]** 按钮添加描述。

   ![](assets/schema_extension_30.png)

1. 如果需要，修改资源的标签和ID。

   >[!NOTE]
   >
   >建议使用30个字符最大值。

1. 如果您需要将对此资源的访问权限限制为某些组织单位，请在此处指定它们。只有授权单位的用户才能在应用程序中使用此资源。
1. 保存修改。

将保存您的修改。您需要再次发布资源以应用这些资源。

## 为配置文件和自定义资源生成唯一ID {#generating-a-unique-id-for-profiles-and-custom-resources}

默认情况下，配置文件和自定义资源在创建时没有任何商业ID。您可以启用在创建元素时自动生成唯一ID的选项。此ID可用于：

* 在外部工具中轻松识别导出的记录。
* 导入其他应用程序中处理的更新数据时，协调记录。

只能为配置文件和自定义资源启用它。

1. 为配置文件资源创建扩展或创建新资源。
1. 在数据结构定义中，选中该 **[!UICONTROL Add automatic ID field]** 选项(在 **[!UICONTROL Fields]** 部分下)。
1. 保存并发布对资源所做的修改。如果您希望此机制应用通过API创建的元素，请选中扩展API的选项。

**[!UICONTROL ACS ID]** 现在，当手动创建新元素、从API手动创建新元素或从导入工作流插入新元素时，该字段便会自动填充。ACS ID字段是一个UUID字段，并且是索引的。

导出配置文件或自定义资源时，如果已经为该资源启用 **[!UICONTROL ACS ID]** 了列，您现在可以添加该列。您可以在外部工具中重复使用此ID来标识记录。

![](assets/export_id_field.png)

重新导入在其他应用程序(例如CRM)中处理/更新的数据时，您可以使用此唯一ID轻松调整它。

>[!NOTE]
>
>在激活选项之前， **[!UICONTROL ACS ID]** 不会更新创建的配置文件或元素的字段。只有新记录将具有ACS ID。此字段处于只读模式。您无法修改它。

