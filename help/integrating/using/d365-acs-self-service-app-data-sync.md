---
title: 在Campaign和Microsoft Dynamics之间同步数据
description: 在Campaign和Dynamics之间同步数据
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 66623c76-96aa-45cd-9637-19d8a9732c04
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '1839'
ht-degree: 0%

---

# 同步数据

您可以将Microsoft Dynamics 365中的表与Campaign同步，将Campaign营销指标与Microsoft Dynamics 365同步。 同步通过三个专门的技术工作流执行： **[!UICONTROL Microsoft Dynamics 365 to Campaign]**， **[!UICONTROL Campaign to Microsoft Dynamics 365]**， **[!UICONTROL Opt-In/Out]**. 请参阅此部分，以了解 [了解详情](../../integrating/using/d365-acs-self-service-app-workflows.md).

>[!IMPORTANT]
>您需要停止/启动 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 工作流，以将您的更改考虑在内。 [了解详情](../../integrating/using/d365-acs-self-service-app-workflows.md)
>

## 将表从Microsoft Dynamics 365映射到Campaign

此 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 此页显示了Microsoft Dynamics 365中的实体列表，以及这些实体将与之同步的Adobe Campaign中的自定义资源。 您可以添加新映射，编辑或删除现有映射。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top.png)

以下是此表中每一列的说明：

* **[!UICONTROL MICROSOFT DYNAMICS 365 TABLE]**：此列标识Microsoft Dynamics 365中的哪个实体将成为映射的数据源。

* **[!UICONTROL CAMPAIGN TABLE]**：此列标识Adobe Campaign中的哪个资源将成为映射的数据目标。

* **[!UICONTROL ACTIONS]**：下面列出了可能的操作：

   * 单击 **[!UICONTROL Edit]** 图标以编辑此映射。

   * 使用  **[!UICONTROL Delete]** 图标以删除表映射。

   * 单击 **[!UICONTROL Replay Data]** 图标以重新同步Microsoft Dynamics 365表中的所有数据。 通常，集成应用程序将仅同步Microsoft Dynamics 365中最近更改的数据。  但是，在某些情况下（例如，您进行了更改或犯了错误），您可能希望重新同步所有数据。  在这些情况下，您可以单击此按钮，在下次停止/启动 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 工作流，您的数据将开始同步。

     如果您单击 **[!UICONTROL Replay Data]** 按钮和检查成功，图标将变为禁用：它指示此表映射对的数据将在下次执行 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 工作流。

     当满足以下条件时，不能选择重播数据：

      * 如果积压事项量度中有2,000,000个（或更多）项目与 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 工作流(显示在 **[!UICONTROL Workflows]** page)
      * 如果Microsoft Dynamics 365表中有2,000,000条或更多记录

     需要重新同步的记录数各不相同。 如果您有大量记录，则可能需要一些时间来完成同步过程。 请参阅 **[!UICONTROL Backlog]** 中的量度 **[!UICONTROL Workflows]** 页面。

     >[!IMPORTANT]
     >
     > 强烈建议在向Adobe Campaign Standard或Microsoft Dynamics 365发布更改时停止集成工作流程。 适用的更改包括：更新了资源/实体（及其关联字段）、链接、标识符列等。 集成当前正在使用的区段。
     >

## 创建新映射 {#add-a-new-mapping}

要创建新映射，请执行以下步骤：

1. 在 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 页面上，单击 **[!UICONTROL Add New Mapping]** 按钮。

1. 使用下拉列表选择要映射的Microsoft Dynamics 365和Campaign表。
页面上的大多数其他输入将取决于您选择的表。

   ![](assets/do-not-localize/d365-to-acs-ui-page-ingress-choose-tables.png)

   >[!NOTE]
   >不能多次映射每个表。 因此，您会注意到下拉选择将不包含已映射的表。

1. 单击 **[!UICONTROL OK]** 确认：应用程序需要一段时间来读取与所选表关联的字段信息。

然后，您可以继续映射配置。 [了解详情](#new-mapping-settings)

>[!IMPORTANT]
>
>只有在首次添加映射时才能在此页中选择表。 在单击 **[!UICONTROL Save]** 按钮：保存后，表选择字段将为 **只读**.

### 编辑现有映射

如果编辑现有映射，您将看到表选定内容不可编辑。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-table-read-only.png)

这是特意设计的，因为页面中更靠下方的输入基于与这些表关联的字段。 更改这些表将使与这些表关联的所有字段无效。  如果要更改要映射到的表，则需要返回到上一页，删除要更改的映射，然后添加新映射。

### 配置单个表映射 {#new-mapping-settings}

在本节中，您将了解如何配置 **单身** 将一个Microsoft Dynamics 365表映射到一个Adobe Campaign表。

您可以定义以下设置：

* **[!UICONTROL Tables]**：此部分列出了Microsoft Dynamics 365表的名称及其将映射到的Campaign表的名称。
* **[!UICONTROL Field Mappings]**：了解详情，请参阅 [本节](#field-mappings)
* **[!UICONTROL Field Replacements]**：了解详情，请参阅 [本节](#field-replacements)
* **[!UICONTROL Filters]**：了解详情，请参阅 [本节](#filters)
* **[!UICONTROL Advanced Settings]**：了解详情，请参阅 [本节](#advanced-settings)

### 字段映射 {#field-mappings}

#### 主键

将新的Microsoft Dynamics 365添加到Campaign表映射时，您需要标识ID字段。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-first-key.png)

Microsoft Dynamics 365主键是只读的，因为应用程序将检测到它。

对于Campaign，您需要选择哪个字段将是唯一键。 必须将其配置为 [CRM ID自定义资源](../../developing/using/uc-calling-resource-id-key.md) 并且不能有重复项。

>[!NOTE]
>
>只有在选择后，您才能在表上选择ID字段 **[!UICONTROL Add New Mapping]**. 如果单击编辑按钮编辑现有表映射，则ID字段将为只读。

主键始终是中列出的第一个字段名称 **[!UICONTROL Field Mappings]** 部分。 提醒一下，右侧列出了以下图标，以提醒您这些是主键。

![](assets/do-not-localize/d365-to-acs-icon-primary-key.png)

#### 添加其他字段映射

此 **[!UICONTROL Field Mappings]** 部分允许您添加主键以外的字段映射。 要添加从Microsoft Dynamics 365到Adobe Campaign的字段的新映射，请单击 **[!UICONTROL Add new field mapping]** 按钮。

在列表中选择Microsoft Dynamics 365和Campaign字段：

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-new-field-mapping.png)

这些列表包含与您在页面顶部选择的Microsoft Dynamics 365和Campaign表关联的字段名称。

此 **[!UICONTROL Apply updates]** 切换器允许您控制是否将此字段的更新从Microsoft Dynamics 365传播到Campaign：
* 如果它打开 ![](assets/do-not-localize/d365-to-acs-icon-switch-on.png)，对Microsoft Dynamics 365中值的更新将在更新时传播到Adobe Campaign。

* 如果您关闭了 ![](assets/do-not-localize/d365-to-acs-icon-switch-off.png)，该值将在初始加载（或重播）数据时传播，但不会传播对Microsoft Dynamics 365中的字段的增量更新。

>[!NOTE]
>
>单击 **[!UICONTROL Apply updates]** 要更新的列标题 **所有** 的开关的开或关。
>

选择字段值后，您会看到数据类型显示在下拉菜单下方。   将值从一个字段映射到另一个字段时，请牢记这一点。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-fields-selected.png)

>[!NOTE]
>
> 您无法将多个Microsoft Dynamics 365字段映射到单个Campaign字段。

### 字段替换 {#field-replacements}

使用 **[!UICONTROL Add New Field Replacement]** 按钮来定义新的字段替换。

字段替换允许您识别：

* Microsoft Dynamics 365字段名称（已在以上字段映射部分添加），
* 现有值(存在于Microsoft Dynamics 365中)，以及
* 要写入Adobe Campaign的新值

将为选取列表、枚举和布尔值提供一个下拉列表。 文本框将用于其他字符串和数字类型。

### 过滤器 {#filters}

使用 **[!UICONTROL Add New Filter]** 按钮选择将传播到Campaign的Microsoft Dynamics 365记录。 您可以选择与记录关联的任何字段以添加到过滤器（字段名称不需要添加到字段映射）。

通过填写以下信息指定过滤器：

* Microsoft Dynamics 365字段名称
* 比较值，以及
* 值(来自Microsoft Dynamics 365)如果给定记录的字段名称、比较和值的计算结果为true，则该记录将传播到Adobe Campaign。

您可以通过设置标记为的输入来选择评估这些过滤器的方式 **[!UICONTROL Choose the filter comparison operator]**.  如果您选择 **和**，对于要传播到Campaign的记录，所有过滤器都必须为true。 如果您选择 **或**，则当其中任何一项评估为true时，该记录将被传播。

选项 **[!UICONTROL Do you want to delete records in Adobe Campaign Standard that will be filtered out from Microsoft Dynamics 365?]** 控制是否要从Campaign中删除已过滤的记录。 如果您选择 **否** 然后，记录将保留在Adobe Campaign中。 选择 **是** 以使其被集成逻辑删除。

>[!NOTE]
>
> 如果未添加过滤器，则所有已修改的记录都将传播到Adobe Campaign。
>

### 高级设置 {#advanced-settings}

配置映射时，可以设置以下附加选项：

* 设置 **[!UICONTROL Apply deletes in Microsoft Dynamics 365 to Campaign?]** 选项至 **是**，适用于要将Microsoft Dynamics 365中发生的删除传播到Adobe Campaign中的相应字段（基于字段名称映射）的情况。 选择 **否** 忽略Microsoft Dynamics 365中的删除操作。

* 设置 **[!UICONTROL Use technical values in Microsoft Dynamics 365 picklists?]** 选项至 **否** 如果要将与Microsoft Dynamics 365选取列表关联的显示值传播到Campaign。 选择 **是** 以传播技术价值。

## 将Campaign营销事件同步到Microsoft Dynamics 365

此 **[!UICONTROL Campaign to Microsoft Dynamics 365]** 页面允许您标识将从Adobe Campaign映射到Microsoft Dynamics 365的电子邮件营销事件。

您可以控制的四个指标包括： **发送**， **点击次数**， **打开次数**、和 **跳出次数**.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-egress.png)

选择 **是** 以确认您确实希望将该类型的事件流入Microsoft Dynamics 365。

单击 [此处](../../integrating/using/d365-acs-self-service-app-workflows.md) 以了解有关这些电子邮件事件流的详细信息。

## 选择启用/禁用工作流 {#opt-in-out-wf}

此 **选择启用/禁用** 通过工作流，可识别Microsoft Dynamics 365和Adobe Campaign之间选择启用/禁用信息的流程。 这假定数据与Microsoft Dynamics 365实体“联系人”和Adobe Campaign资源“配置文件”相关联。

了解有关中选择退出管理的更多信息 [本节](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out).

请记住，您需要单击“保存”以保存您的选择。 另请记住，您必须停止 **营销活动到Microsoft Dynamics 365** 工作流，然后单击“播放”以便该集成合并您所做的更改。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-optinout-disabled.png)

### 选择启用/禁用同步方向

以下是同步数据的可用选项列表：

* **[!UICONTROL Disabled]**：如果选择此选项，则不会在Adobe Campaign和Microsoft Dynamics 365之间移动选择启用/禁用信息。

* **[!UICONTROL Unidirectional (Microsoft Dynamics 365 to Campaign)]**：此选项仅用于将Microsoft Dynamics 365中的选择加入/退出信息流向Adobe Campaign。 集成应用程序不允许您在此屏幕中配置流；请改为单击 **[!UICONTROL Save button]**，然后导航到 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 工作流。 在此工作流中，您可以编辑联系人/配置文件表映射，以确定您希望如何映射选择启用/禁用字段。

* **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**：此选项将使 **映射** 部分。 这些输入将允许您定义哪些Adobe Campaign字段会将数据映射到Microsoft Dynamics 365中的哪些字段。 这意味着，如果您碰巧在Microsoft Dynamics 365中手动更新某个值，那么如果该值发生更改，其值将被Adobe Campaign值覆盖。

* **[!UICONTROL Bidirectional]**：此选项将使 **映射** 部分。 这些对将标识Microsoft Dynamics 365和Adobe Campaign中的哪些字段将相互映射。 [了解详情](../../integrating/using/d365-acs-notices-and-recommendations.md)。

### 映射

仅当选择启用/禁用同步方向字段设置为时，此部分才适用 **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** 或 **[!UICONTROL Bidirectional]**. 您可以定义Microsoft Dynamics 365中的哪些字段映射到Adobe Campaign中的输入内容。

Microsoft Dynamics 365字段名称包括所有类型的字段名称 **布尔型**.

Adobe Campaign字段名称是特定于选择启用/禁用的一组固定值。 Adobe Campaign字段名称是特定于选择启用/禁用的一组固定值。 **无法更改此列表中的值集**.
