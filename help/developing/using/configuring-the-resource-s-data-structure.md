---
title: 配置资源的数据结构
description: 了解如何配置数据结构。
page-status-flag: never-activated
uuid: 60fe80c0-9df6-4808-a432-60a1977216ea
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 4f22ee35-1d5f-4c75-95b4-3e38b85de26e
context-tags: cusResource,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bd83bb520a9822ffa9669076f90e6dc3397c6480

---


# 配置资源的数据结构{#configuring-the-resource-s-data-structure}

创建新的自定义资源后，必须配置数据结构。

编辑资源时，您可以在选 **[!UICONTROL Data structure]** 项卡中添加：

* [字段](#adding-fields-to-a-resource)
* [标识键](#defining-identification-keys)
* [索引](#defining-indexes)
* [链接](#defining-links-with-other-resources)
* [发送日志](#defining-sending-logs-extension)

## 向资源添加字段 {#adding-fields-to-a-resource}

可以向资源中添加新字段以存储非现成数据模型的一部分的数据。

1. 使用 **[!UICONTROL Create element]** 按钮创建字段。
1. 指定标签、ID、字段类型，并定义此字段授权的最大长度。

   该字 **[!UICONTROL ID]** 段是必填字段，且对于添加的每个字段必须是唯一的。

   >[!NOTE]
   >
   >最多使用30个字符。

   ![](assets/schema_extension_4.png)

1. 要修改其中一个字段，请选中该 **[!UICONTROL Edit Properties]** 按钮。

   ![](assets/schema_extension_24.png)

1. 在屏幕 **[!UICONTROL Field definition]** 中，您可以定义将用于受众和定位的类别，甚至可以添加描述。

   ![](assets/schema_extension_5.png)

1. 如果需 **[!UICONTROL Specify a list of authorized values]** 要定义将提供给用户的值（枚举值），请选中此选项。

   然后，单 **[!UICONTROL Create element]** 击并指定 **[!UICONTROL Label]** 和 **[!UICONTROL Value]**。 根据需要添加任意数量的值。

1. 添加字段后，选中该框 **[!UICONTROL Add audit fields]** 以包含详细说明创建日期、创建资源的用户、日期和上次修改的作者的字段。
1. 选中该 **[!UICONTROL Add access authorization management fields]** 框以包含说明谁对该特定资源具有访问权限的字段。

   这些字段显示在执行数据库更新后可显示的数据和元数据中。 有关详细信息，请参阅更新数 [据库结构一节](../../developing/using/updating-the-database-structure.md) 。

1. 选中该 **[!UICONTROL Add automatic ID]** 字段可自动生成ID。 请注意，现有实体将保持为空。 有关详细信息，请参阅为配 [置文件和自定义资源生成唯一ID](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)。
1. 要修改资源元素名称在列表和创建步骤中的显示方式，请选中该 **[!UICONTROL Customize the title of the resource elements]** 框。 从您为此资源创建的字段中选择一个字段。

   ![](assets/schema_extension_18.png)

   >[!NOTE]
   >
   >如果不选中此选项，则在列出此表中的所有实体时，将使用自动主键（每次将实体添加到表时自动创建）。

现在可以定义资源的字段。

## 定义标识键 {#defining-identification-keys}

每个资源必须至少有一个唯一的密钥。 例如，您可以指定一个键，这样两个产品在购买表中就不能具有相同的ID。

1. 如果希望自动 **[!UICONTROL Automatic primary key]** 且以增量方式生成技术密钥，请在部分中指定存储的大小。

   ![](assets/schema_extension_6.png)

1. 使用 **[!UICONTROL Create element]** 按钮创建键。

   默认情 **[!UICONTROL Label]** 况下 **[!UICONTROL ID]** ，这些和字段已完成，但您可以编辑它们。

   >[!NOTE]
   >
   >最多使用30个字符。

1. 要定义构成此键的元素，请单 **[!UICONTROL Create element]** 击并选择您为此资源创建的字段。

   ![](assets/schema_extension_7.png)

   创建的键显示在部 **[!UICONTROL Custom keys]** 分中。

此时将创建资源的标识密钥。

>[!NOTE]
>
>要了解创建标识键时的最佳实践，请参阅此 [部分](../../developing/using/data-model-best-practices.md#keys)。

## 定义索引 {#defining-indexes}

索引可以引用一个或多个资源字段。 索引允许数据库对记录进行排序，以便更轻松地恢复记录。 它们优化了SQL查询的性能。

建议定义索引，但不是强制性的。

1. 使用 **[!UICONTROL Create element]** 按钮创建索引。

   ![](assets/schema_extension_26.png)

1. 默认情 **[!UICONTROL Label]** 况下 **[!UICONTROL ID]** ，和字段将完成，但您可以编辑它们。

   >[!NOTE]
   >
   >最多使用30个字符。

1. 要定义构成此索引的元素，请从您为此资源创建的字段中选择字段。

   ![](assets/schema_extension_27.png)

1. 单击 **[!UICONTROL Confirm]**.

创建的索引显示在部分中的列表 **[!UICONTROL Index]** 中。

>[!NOTE]
>
>要了解创建索引时的最佳实践，请参阅此 [部分](../../developing/using/data-model-best-practices.md#indexes)。

## 定义与其他资源的链接 {#defining-links-with-other-resources}

链接详细说明了一个表与其他表的关联。

1. 使用 **[!UICONTROL Create element]** 按钮可创建指向目标资源的链接。
1. 单击 **[!UICONTROL Select a target resource]**.

   ![](assets/schema_extension_28.png)

1. 资源按字母顺序显示，并可按名称筛选。 他们的技术名称显示在括号中。

   从列表中选择元素，然后单击 **[!UICONTROL Confirm]**。

   ![](assets/schema_extension_9.png)

1. 根据基数 **[!UICONTROL Link type]** 选择该选项。 根据所选基数类型，删除或复制记录时的行为可能会有所不同。

   各种链接类型如下：

   * **[!UICONTROL 1 cardinality simple link]**:源表的一个出现最多可以具有目标表的一个对应出现。
   * **[!UICONTROL N cardinality collection link]**:源表的一个出现可以具有目标表的多个对应出现，但目标表的一个出现最多可以具有源表的一个对应出现。
   * **[!UICONTROL 0 or 1 cardinality simple link]**:源表的一个实例最多可以具有目标表的一个对应实例或无。 请注意，这种类型可 **[!UICONTROL Link type]** 能导致性能问题。
   ![](assets/schema_extension_29.png)

1. 在屏幕 **[!UICONTROL New link]** 中，默认情况下 **[!UICONTROL Label]** ，会 **[!UICONTROL ID]** 完成这些字段和字段，但您可以编辑它们。

   >[!NOTE]
   >
   >最多使用30个字符。

   >[!CAUTION]
   >
   >创建后无法重命名链接。 要重命名链接，必须删除该链接并重新创建它。

1. 该列 **[!UICONTROL Category for the audience and targeting]** 表允许您将此链接分配到某个类别，使其在查询编辑器工具中更加可见。
1. 如果需要， **[!UICONTROL Reverse link definition]** 该部分允许您在目标资源中显示资源的标签和ID。
1. 定义部分中链接引用的记录的行 **[!UICONTROL Behavior if deleted/duplicated]** 为。

   默认情况下，目标记录在链接不再引用后即被删除。

   ![](assets/schema_extension_16.png)

1. 在部分 **[!UICONTROL Join definition]** 中，默认选项被选 **[!UICONTROL Use the primary keys to make the join]** 中，但您可以选择以下两个选项：

   * **[!UICONTROL Use the primary key to make the join]**:此连接定义允许您使用配置文件的主要密钥来协调购买的主要密钥。
   * **[!UICONTROL Define specific join conditions]**:此连接定义允许您手动选择将连接两个资源的字段。 请注意，如果数据配置不正确，则 **Purchase** record将不可见。
   ![](assets/schema_extension_17.png)

创建的链接将显示在部分的列表 **[!UICONTROL Links]** 中。

>[!NOTE]
>
>要了解创建索引时的最佳实践，请参阅此 [部分](../../developing/using/data-model-best-practices.md#links)。

**示例：将创建的资源与“配置文件”资源关联**

在此示例中，我们要将新资源Purchase与 **Profiles** 自定义资 **源关联** :

1. 创建新的 **购买** 资源。
1. 要将其与Profiles自定义资 **源关联** ，请展开选 **[!UICONTROL Links]** 项卡中的部 **[!UICONTROL Data structure]** 分并单击 **[!UICONTROL Create element]**。
1. 在此处选择目标资源 **[!UICONTROL Profiles (profile)]**。
1. 在此示例中，保持默认的“链 **[!UICONTROL 1 cardinality simple link]** 接”类型处于选中状态。

   ![](assets/custom_resource_link_to_profile_2.png)

1. 选择连接定义，此处保留默认值 **[!UICONTROL Use the primary key to make the join]**。

   ![](assets/custom_resource_link_to_profile_3.png)

1. 如果需要，您可以定义一个详细信息屏幕，以便能够编辑 **Purchase** ，并将其链接到配置文件。

   展开 **[!UICONTROL Detail screen configuration]** 部分并检查以 **[!UICONTROL Define a detail screen]** 配置与资源的每个元素对应的屏幕。 如果不选中此框，将无法访问此资源的元素的详细信息视图。

1. 单击 **[!UICONTROL Create element]**.
1. 选择您的链接资源，然后单击 **[!UICONTROL Add]**。

   然后，您的新资源将显示在高级菜单中，方法是选择 **[!UICONTROL Client data]** > **[!UICONTROL Purchase]**。

   ![](assets/custom_resource_link_to_profile_4.png)

1. 完成配置后，单击 **[!UICONTROL Confirm]**。

   您现在可以发布新资源。

通过添加此链接，“购 **买** ”选项卡会从“>”菜单添加到配置文件详细信息 **[!UICONTROL Profiles & audiences]** 屏幕 **[!UICONTROL Profiles]** 中。 请注意，这是特定于资源的 **[!UICONTROL Profile]** 操作。

![](assets/custom_resource_link_to_profile.png)

## 定义发送日志扩展 {#defining-sending-logs-extension}

发送日志扩展允许您：

* 通过添加配置文件自定义字段来扩 **展动态报告功能**
* 使用细分代码和配置文件数 **据扩展发送日志数据**

**使用细分代码扩展**

用户可以使用来自工作流引擎的区段代码扩展日志。

区段代码必须定义到工作流中。

要激活此扩展，请选中该选项 **[!UICONTROL Add segment code]**。

![](assets/sendinglogsextension_1.png)

有关区段代码的详细信息，请参阅“ [分段](../../automating/using/segmentation.md) ”部分。

**使用配置文件字段扩展**

>[!NOTE]
>
>管理员应已使用自定义字段扩展配置文件资源。

![](assets/sendinglogsextension_2.png)

单击 **[!UICONTROL Add field]** 并从配置文件资源中选择任何自定义字段。

要生成链接到“配置文件”(Profile)维的新子维，请选中该 **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** 选项。

![](assets/sendinglogsextension_3.png)

从动态报表中，可以将自定义字段维度拖放到自由格式表中。

有关动态报告的详细信息，请参阅 [组件列表](../../reporting/using/list-of-components-.md)。

>[!CAUTION]
>
>发送到Dynamic Reporting的字段数限制为20个。

## 编辑资源属性 {#editing-resource-properties}

在自定义资源屏幕中，窗 **[!UICONTROL Summary]** 格指示新创建的资源的状态。 您可以管理其访问权限及其常规属性。

![](assets/schema_extension_3.png)

1. 单击该 **[!UICONTROL Edit properties]** 按钮可添加说明。

   ![](assets/schema_extension_30.png)

1. 如果需要，请修改资源的标签和ID。

   >[!NOTE]
   >
   >最多使用30个字符。

1. 如果需要将对此资源的访问权限限制为某些组织单位，请在此处指定这些单位。 只有授权单位的用户才能在应用程序中使用此资源。
1. 保存修改。

将保存您的修改。 您需要再次发布资源以应用这些资源。

## 为配置文件和自定义资源生成唯一ID {#generating-a-unique-id-for-profiles-and-custom-resources}

默认情况下，配置文件和自定义资源在创建时没有业务ID。 您可以启用一个选项，该选项在创建元素时自动生成唯一ID。 此ID可用于：

* 在外部工具中轻松识别导出的记录。
* 在导入在其他应用程序中处理的更新数据时协调记录。

只能为配置文件和自定义资源启用它。

1. 为配置文件资源创建扩展或创建新资源。
1. 在数据结构定义中，选中部 **[!UICONTROL Add automatic ID field]** 分下的选项 **[!UICONTROL Fields]** 。

   ![](assets/option_id_field.png)

   >[!NOTE]
   >
   >只有新记录才有ACS ID。 对于在 **[!UICONTROL ACS ID]** 激活此选项之前创建的配置文件或元素，该字段将保留为空。

1. 保存并发布对资源所做的修改。 如果希望此机制应用于通过API创建的元素，请选中此选项以扩展API。

现在 **[!UICONTROL ACS ID]** 该字段可用，并在手动、从API或从导入工作流中插入新元素时自动填充。 ACS ID字段是UUID字段，并且已编制索引。

在导出配置文件或自定义资源时，如果已为该 **[!UICONTROL ACS ID]** 资源启用该列，您现在可以添加该列。 您可以在外部工具中重复使用此ID来标识记录。

![](assets/export_id_field.png)

在重新导入已在其他应用程序（例如CRM）中处理／更新的数据时，您可以轻松地将其与此唯一ID进行协调。

>[!NOTE]
>
>在启 **[!UICONTROL ACS ID]** 用该选项之前，不会更新创建的配置文件或元素的字段。 只有新记录才有ACS ID。
>
>此字段处于只读模式。 您无法修改它。
