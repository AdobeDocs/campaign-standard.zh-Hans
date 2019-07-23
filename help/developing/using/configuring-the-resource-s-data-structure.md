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
source-git-commit: 6b642a58fc88779f88f2f860c133b36934c59d21

---


# Configuring the resource's data structure{#configuring-the-resource-s-data-structure}

创建新的自定义资源后，必须配置数据结构。

When editing the resource, in the **[!UICONTROL Data structure]** tab, you can add:

* [Fields](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource)
* [标识键](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [索引](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes)
* [链接](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources)
* [发送日志](../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension)

## Adding fields to a resource {#adding-fields-to-a-resource}

您可以向资源添加新字段，以存储不属于现成数据模型之外的数据。

1. Use the **[!UICONTROL Create element]** button to create a field.
1. 指定标签、ID、字段类型并定义为此字段授权的最大长度。

   The **[!UICONTROL ID]** field is mandatory and must be unique for each field added.

   >[!NOTE]
   >
   >If you leave the **[!UICONTROL Label]** field empty, it will automatically be completed from the ID.
   >建议使用30个字符最大值。

   ![](assets/schema_extension_4.png)

1. To modify one of the fields, check the **[!UICONTROL Edit Properties]** button.

   ![](assets/schema_extension_24.png)

1. **[!UICONTROL Field definition]** 在屏幕中，您可以定义用于受众和定位的类别，甚至添加描述。

   ![](assets/schema_extension_5.png)

1. Check the **[!UICONTROL Specify a list of authorized values]** option if you need to define values that will be offered to the user (enumeration values).

   Then, click **[!UICONTROL Create element]** and specify a **[!UICONTROL Label]** and **[!UICONTROL Value]**. 根据需要添加任意数量的值。

1. Once you have added your fields, check the **[!UICONTROL Add audit fields]** box to include fields detailing the creation date, the user that created the resource, the date, and the author of the last modification.
1. Check the **[!UICONTROL Add access authorization management fields]** box to include the fields stating who has access rights to that particular resource.

   这些字段显示在数据和元数据中，这些字段在执行数据库更新后可显示。For more on this, refer to the [Updating the database structure](../../developing/using/updating-the-database-structure.md) section.

1. Check the **[!UICONTROL Add automatic ID]** field to automatically generate an ID. 请注意，现有实体将保留为空。
1. To modify the way in which the name of the resource elements will appear in the lists and creation steps, check the **[!UICONTROL Personalize the resource title]** box. 从为此资源创建的字段中选择一个字段。

   ![](assets/schema_extension_18.png)

此时将定义资源的字段。

## Defining identification keys {#defining-identification-keys}

每个资源必须至少具有一个唯一密钥。例如，您可以指定一个密钥，以便两个产品在购买表中没有相同的ID。

1. Specify it in the **[!UICONTROL Automatic primary key]** section the size for the storage if you would like to have a technical key automatically and incrementally generated.

   ![](assets/schema_extension_6.png)

1. Use the **[!UICONTROL Create element]** button to create a key.

   The **[!UICONTROL Label]** and **[!UICONTROL ID]** fields are completed by default but you can edit them.

   >[!NOTE]
   >
   >建议使用30个字符最大值。

1. To define the elements making up this key, click **[!UICONTROL Create element]** and select the fields that you created for this resource.

   ![](assets/schema_extension_7.png)

   Created keys are displayed in the **[!UICONTROL Custom keys]** section.

此时会创建资源的标识密钥。

## Defining indexes {#defining-indexes}

索引可引用一个或多个资源字段。索引允许数据库对记录进行排序，以便更轻松地恢复它们。它们优化SQL查询的性能。

建议定义索引，但不是强制定义索引。

1. Use the **[!UICONTROL Create element]** button to create an index.

   ![](assets/schema_extension_26.png)

1. The **[!UICONTROL Label]** and **[!UICONTROL ID]** fields are completed by default, but you can edit them.

   >[!NOTE]
   >
   >建议使用30个字符最大值。

1. 要定义构成此索引的元素，请从为该资源创建的字段中选择字段。

   ![](assets/schema_extension_27.png)

1. Click **[!UICONTROL Confirm]**.

The indexes that were created appear in the list in the **[!UICONTROL Index]** section.

## Defining links with other resources {#defining-links-with-other-resources}

链接详细说明了一个表与其他表的关联情况。

1. Use the **[!UICONTROL Create element]** button to create a link to a target resource.
1. Click **[!UICONTROL Select a target resource]**.

   ![](assets/schema_extension_28.png)

1. 资源以字母顺序显示，并且可以按名称筛选。他们的技术名称将显示在括号中。

   Select an element from the list and click **[!UICONTROL Confirm]**.

   ![](assets/schema_extension_9.png)

1. Select the **[!UICONTROL Link type]** according to cardinality. 根据所选基数类型，如果记录被删除或重复，则行为可能会有所不同。

   各种链接类型如下所示：

   * **[!UICONTROL 1 cardinality simple link]**：源表的一个出现最多可能有目标表的相应出现。
   * **[!UICONTROL N cardinality collection link]**：源表的一个出现可能有多个对应的目标表发生情况，但目标表的一个出现可能会有源表的最多一个相应的实例。
   * **[!UICONTROL 0 or 1 cardinality simple link]**：源表的一个出现可能具有目标表或无的大多数对应的出现。Note that this kind of **[!UICONTROL Link type]** can cause performance issue.
   ![](assets/schema_extension_29.png)

1. **[!UICONTROL New link]** 在屏幕中，默认 **[!UICONTROL Label]** 情况下，这些和 **[!UICONTROL ID]** 字段是完成的，但是您可以编辑它们。

   >[!NOTE]
   >
   >建议使用30个字符最大值。

   >[!CAUTION]
   >
   >创建后重命名链接不可能。要重命名链接，必须将其删除并重新创建。

1. **[!UICONTROL Category for the audience and targeting]** 该列表允许您将此链接分配给类别，使其在查询编辑器工具中更可见。
1. If needed, the **[!UICONTROL Reverse link definition]** section allows you to display the label and ID of the resource in the targeted resource.
1. Define the behavior of the records referenced by the link in the **[!UICONTROL Behavior if deleted/duplicated]** section.

   默认情况下，链接不再引用目标记录后，将删除目标记录。

   ![](assets/schema_extension_16.png)

1. **[!UICONTROL Join definition]** 在该部分中，选择了默认 **[!UICONTROL Use the primary keys to make the join]** 选项，但您可以在以下两个选项之间进行选择：

   * **[!UICONTROL Use the primary key to make the join]**：此加入定义允许您使用配置文件主要密钥与购买的主要密钥协调。
   * **[!UICONTROL Define specific join conditions]**：此加入定义允许您手动选择将加入两个资源的字段。Please note that if data are not correctly configured, the **Purchase** record will not be visible.
   ![](assets/schema_extension_17.png)

The links created are displayed in the list in the **[!UICONTROL Links]** section.

**示例：将创建的资源与“配置文件”资源链接**

In this example, we want to link a new resource **Purchase** with the **Profiles **custom resource:

1. Create your new **Purchase** resource.
1. To link it with the **Profiles** custom resource, unfold the **[!UICONTROL Links]** section in the **[!UICONTROL Data structure]** tab and click **[!UICONTROL Create element]**.
1. Select the target resource, here **[!UICONTROL Profiles (profile)]**.
1. In this example, keep the default **[!UICONTROL 1 cardinality simple link]** Link type selected.

   ![](assets/custom_resource_link_to_profile_2.png)

1. Choose a join definition, here keep the default **[!UICONTROL Use the primary key to make the join]**.

   ![](assets/custom_resource_link_to_profile_3.png)

1. If needed, you can define a detail screen to be able to edit **Purchase** and link it to a profile.

   Unfold the **[!UICONTROL Detail screen configuration]** section and check the **[!UICONTROL Define a detail screen]** to configure the screen that corresponds to each element of the resource. 如果不选中此框，则无法访问此资源元素的详细信息视图。

1. Click **[!UICONTROL Create element]**.
1. Select your linked resource and click **[!UICONTROL Add]**.

   Your new resource will then be available in the advanced menu by selecting **[!UICONTROL Client data]** &gt; **[!UICONTROL Purchase]**.

   ![](assets/custom_resource_link_to_profile_4.png)

1. Once your configuration is done, click **[!UICONTROL Confirm]**.

   您现在可以发布新资源。

By adding this link, a **Purchase** tab is added to the profiles detail screen from the **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Profiles]** menu. Please note that this is specific to the **[!UICONTROL Profile]** resource.

![](assets/custom_resource_link_to_profile.png)

## Defining sending logs extension {#defining-sending-logs-extension}

发送日志扩展允许您：

* to extend dynamic report capabilities by **adding profile custom fields**
* to extend the sending logs data with **segment code and profile data**

**使用区段代码扩展**

用户可以使用来自工作流引擎的区段代码扩展日志。

必须将区段代码定义为工作流。

To activate this extension, check the option **[!UICONTROL Add segment code]**.

![](assets/sendinglogsextension_1.png)

For more information on segment code, refer to the [Segmentation](../../automating/using/segmentation.md) section.

**扩展配置文件字段**

>[!NOTE]
>
>管理员应使用自定义字段扩展配置文件资源。

![](assets/sendinglogsextension_2.png)

Click **[!UICONTROL Add field]** and select any custom field from the profile resource.

In order to generate a new sub-dimension linked to the Profile dimension, check the **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** option.

![](assets/sendinglogsextension_3.png)

通过动态报告，您可以将自定义字段维度拖放到自由表单中。

For more information on Dynamic Reporting, refer to the [List of components](../../reporting/using/list-of-components-.md).

>[!CAUTION]
>
>发送到动态报告的字段数量仅限20个。

## Editing resource properties {#editing-resource-properties}

In the custom resource screen, the **[!UICONTROL Summary]** pane indicates the status of the newly created resource. 您可以管理其访问权限及其常规属性。

![](assets/schema_extension_3.png)

1. Click the **[!UICONTROL Edit properties]** button to add a description.

   ![](assets/schema_extension_30.png)

1. 如果需要，修改资源的标签和ID。

   >[!NOTE]
   >
   >建议使用30个字符最大值。

1. 如果您需要将对此资源的访问权限限制为某些组织单位，请在此处指定它们。只有授权单位的用户才能在应用程序中使用此资源。
1. 保存修改。

将保存您的修改。您需要再次发布资源以应用这些资源。

## Generating a unique ID for profiles and custom resources {#generating-a-unique-id-for-profiles-and-custom-resources}

默认情况下，配置文件和自定义资源在创建时没有任何商业ID。您可以启用在创建元素时自动生成唯一ID的选项。此ID可用于：

* 在外部工具中轻松识别导出的记录。
* 导入其他应用程序中处理的更新数据时，协调记录。

只能为配置文件和自定义资源启用它。

1. 为配置文件资源创建扩展或创建新资源。
1. In the data structure definition, check the **[!UICONTROL Add automatic ID field]** option, under the **[!UICONTROL Fields]** section.
1. 保存并发布对资源所做的修改。如果您希望此机制应用通过API创建的元素，请选中扩展API的选项。

**[!UICONTROL ACS ID]** 现在，当手动创建新元素、从API手动创建新元素或从导入工作流插入新元素时，该字段便会自动填充。ACS ID字段是一个UUID字段，并且是索引的。

When exporting profiles or custom resources, you can now add the **[!UICONTROL ACS ID]** column if it has been enabled for that resource. 您可以在外部工具中重复使用此ID来标识记录。

![](assets/export_id_field.png)

重新导入在其他应用程序(例如CRM)中处理/更新的数据时，您可以使用此唯一ID轻松调整它。

>[!NOTE]
>
>The **[!UICONTROL ACS ID]** field is not updated for profiles or elements created before activating the option. 只有新记录将具有ACS ID。此字段处于只读模式。您无法修改它。

