---
title: 在Campaign和Microsoft Dynamics之间同步数据
description: 在Campaign和Dynamics之间同步数据
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 66623c76-96aa-45cd-9637-19d8a9732c04
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '1839'
ht-degree: 0%

---

# 同步数据

您可以将Microsoft Dynamics 365中的表与Campaign同步，将Campaign营销指标与Microsoft Dynamics 365同步。 同步通过三个专用的技术工作流执行： **[!UICONTROL Microsoft Dynamics 365 to Campaign]**、**[!UICONTROL Campaign to Microsoft Dynamics 365]**、**[!UICONTROL Opt-In/Out]**。 请参阅此部分以了解[更多信息](../../integrating/using/d365-acs-self-service-app-workflows.md)。

>[!IMPORTANT]
>您需要停止/启动&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;工作流以将您的更改考虑在内。 [了解详情](../../integrating/using/d365-acs-self-service-app-workflows.md)
>

## 将表从Microsoft Dynamics 365映射到Campaign

**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;页显示了Microsoft Dynamics 365中的实体列表以及Adobe Campaign中将与它们同步的自定义资源。 您可以添加新映射，编辑或删除现有映射。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top.png)

以下是此表中每一列的说明：

* **[!UICONTROL MICROSOFT DYNAMICS 365 TABLE]**：此列标识Microsoft Dynamics 365中的哪个实体将成为映射的数据源。

* **[!UICONTROL CAMPAIGN TABLE]**：此列标识Adobe Campaign中的哪个资源将成为映射的数据目标。

* **[!UICONTROL ACTIONS]**：下面列出了可能的操作：

   * 单击&#x200B;**[!UICONTROL Edit]**&#x200B;图标以编辑此映射。

   * 使用&#x200B;**[!UICONTROL Delete]**&#x200B;图标删除表映射。

   * 单击&#x200B;**[!UICONTROL Replay Data]**&#x200B;图标可重新同步Microsoft Dynamics 365表中的所有数据。 通常，集成应用程序将只同步最近更改的Microsoft Dynamics 365中的数据。  但是，在某些情况下（例如，您进行了更改或犯了错误），您可能希望重新同步所有数据。  在这些情况下，您可以单击此按钮，在下次停止/启动&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;工作流时，您的数据将开始同步。

     如果单击“**[!UICONTROL Replay Data]**”按钮且检查成功，则该图标将变为禁用：它表示在下次执行&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;工作流时，此表映射对的数据将重新同步。

     当满足以下条件时，不能选择重播数据：

      * 如果积压工作量度中有与&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;工作流关联的2,000,000个（或更多）项目（显示在&#x200B;**[!UICONTROL Workflows]**&#x200B;页面中）
      * 如果Microsoft Dynamics 365表中有2,000,000条或更多记录

     需要重新同步的记录数各不相同。 如果您有大量记录，则可能需要一些时间来完成同步过程。 在集成应用程序工作完成同步过程时，请参阅&#x200B;**[!UICONTROL Backlog]**&#x200B;页面中的&#x200B;**[!UICONTROL Workflows]**&#x200B;量度。

     >[!IMPORTANT]
     >
     > 强烈建议您在将更改发布到Adobe Campaign Standard或Microsoft Dynamics 365时停止集成工作流程。 适用的更改包括：更新了资源/实体（及其关联字段）、链接、标识符列等。 集成当前正在使用的区段。
     >

## 创建新映射 {#add-a-new-mapping}

要创建新映射，请执行以下步骤：

1. 在&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;页面中，单击&#x200B;**[!UICONTROL Add New Mapping]**&#x200B;按钮。

1. 使用下拉列表选择要映射的Microsoft Dynamics 365和Campaign表。
页面上的大多数其他输入将取决于您选择的表。

   ![](assets/do-not-localize/d365-to-acs-ui-page-ingress-choose-tables.png)

   >[!NOTE]
   >不能多次映射每个表。 因此，您会注意到下拉选择将不包含已映射的表。

1. 单击&#x200B;**[!UICONTROL OK]**&#x200B;以确认：应用程序需要一段时间来读取与所选表关联的字段信息。

然后，您可以继续映射配置。 [了解详情](#new-mapping-settings)

>[!IMPORTANT]
>
>只有在首次添加映射时才能在此页中选择表。 在单击&#x200B;**[!UICONTROL Save]**&#x200B;按钮之前，请确保已选择正确的表：保存后，表选择字段将为&#x200B;**只读**。

### 编辑现有映射

如果编辑现有映射，您将看到表选定内容不可编辑。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-table-read-only.png)

这是特意设计的，因为页面中更靠下方的输入基于与这些表关联的字段。 更改这些表将使与这些表关联的所有字段无效。  如果要更改要映射到的表，则需要返回到上一页，删除要更改的映射，然后添加新映射。

### 配置单个表映射 {#new-mapping-settings}

在本节中，您将了解如何配置一个Microsoft Dynamics 365表到一个Adobe Campaign表的&#x200B;**single**&#x200B;映射。

您可以定义以下设置：

* **[!UICONTROL Tables]**：此部分列出了Microsoft Dynamics 365表的名称及其将映射到的Campaign表。
* **[!UICONTROL Field Mappings]**：在[本节](#field-mappings)中了解详情
* **[!UICONTROL Field Replacements]**：在[本节](#field-replacements)中了解详情
* **[!UICONTROL Filters]**：在[本节](#filters)中了解详情
* **[!UICONTROL Advanced Settings]**：在[本节](#advanced-settings)中了解详情

### 字段映射 {#field-mappings}

#### 主键

将新的Microsoft Dynamics 365添加到Campaign表映射时，您需要识别ID字段。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-first-key.png)

Microsoft Dynamics 365主键是只读的，因为应用程序将检测到它。

对于Campaign，您需要选择哪个字段将是唯一键。 它必须配置为[CRM ID自定义资源](../../developing/using/uc-calling-resource-id-key.md)，并且不能有重复项。

>[!NOTE]
>
>选择&#x200B;**[!UICONTROL Add New Mapping]**&#x200B;后，您只能在表上选择ID字段。 如果单击编辑按钮编辑现有表映射，则ID字段将为只读。

主键将始终是&#x200B;**[!UICONTROL Field Mappings]**&#x200B;部分中列出的第一个字段名称。 提醒一下，右侧列出了以下图标，以提醒您这些是主键。

![](assets/do-not-localize/d365-to-acs-icon-primary-key.png)

#### 添加其他字段映射

**[!UICONTROL Field Mappings]**&#x200B;部分允许您添加主键以外的字段映射。 要添加字段从Microsoft Dynamics 365到Adobe Campaign的新映射，请单击&#x200B;**[!UICONTROL Add new field mapping]**&#x200B;按钮。

在列表中选择Microsoft Dynamics 365和Campaign字段：

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-new-field-mapping.png)

这些列表包含与您在页面顶部选择的Microsoft Dynamics 365和Campaign表关联的字段名称。

**[!UICONTROL Apply updates]**&#x200B;切换器允许您控制是否将此字段的更新从Microsoft Dynamics 365传播到Campaign：
* 如果开启![](assets/do-not-localize/d365-to-acs-icon-switch-on.png)，则对Microsoft Dynamics 365中值的更新将在更新发生时传播到Adobe Campaign。

* 如果关闭![](assets/do-not-localize/d365-to-acs-icon-switch-off.png)，该值将在最初加载（或重播）数据时传播，但不会传播Microsoft Dynamics 365中字段的增量更新。

>[!NOTE]
>
>单击&#x200B;**[!UICONTROL Apply updates]**&#x200B;列标题可将&#x200B;**所有**&#x200B;开关更新为打开或关闭。
>

选择字段值后，您会看到数据类型显示在下拉菜单下方。   将值从一个字段映射到另一个字段时，请牢记这一点。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-fields-selected.png)

>[!NOTE]
>
> 您无法将多个Microsoft Dynamics 365字段映射到单个Campaign字段。

### 字段替换 {#field-replacements}

使用&#x200B;**[!UICONTROL Add New Field Replacement]**&#x200B;按钮定义新的字段替换。

字段替换允许您识别：

* Microsoft Dynamics 365字段名称（已在以上字段映射部分添加），
* 现有值(存在于Microsoft Dynamics 365中)，以及
* 要写入Adobe Campaign的新值

将为选取列表、枚举和布尔值提供一个下拉列表。 文本框将用于其他字符串和数字类型。

### 过滤器 {#filters}

使用&#x200B;**[!UICONTROL Add New Filter]**&#x200B;按钮选择要传播到Campaign的Microsoft Dynamics 365记录。 您可以选择与记录关联的任何字段以添加到过滤器（字段名称不需要添加到字段映射）。

通过填写以下信息指定过滤器：

* Microsoft Dynamics 365字段名称
* 比较值，以及
* 值(来自Microsoft Dynamics 365)
如果字段名称、比较和值的计算结果为给定记录为true，则该记录将传播到Adobe Campaign。

您可以通过设置标记为&#x200B;**[!UICONTROL Choose the filter comparison operator]**&#x200B;的输入来选择评估这些过滤器的方式。  如果选择&#x200B;**And**，则所有筛选器都必须为true，记录才能传播到Campaign。 如果选择&#x200B;**或**，如果其中任何记录的计算结果为true，则将传播该记录。

选项&#x200B;**[!UICONTROL Do you want to delete records in Adobe Campaign Standard that will be filtered out from Microsoft Dynamics 365?]**&#x200B;控制是否希望从Campaign中删除已过滤的记录。 如果选择&#x200B;**否**，则记录将保留在Adobe Campaign中。 选择&#x200B;**是**&#x200B;以让集成逻辑删除它们。

>[!NOTE]
>
> 如果未添加过滤器，则所有已修改的记录都将传播到Adobe Campaign。
>

### 高级设置 {#advanced-settings}

配置映射时，可以设置以下附加选项：

* 如果要将Microsoft Dynamics 365中发生的删除传播到Adobe Campaign中的相应字段（基于字段名称映射），请将&#x200B;**[!UICONTROL Apply deletes in Microsoft Dynamics 365 to Campaign?]**&#x200B;选项设置为&#x200B;**是**。 选择&#x200B;**否**&#x200B;以忽略Microsoft Dynamics 365中的删除操作。

* 如果要将与Microsoft Dynamics 365选取列表关联的显示值传播到Campaign，请将&#x200B;**[!UICONTROL Use technical values in Microsoft Dynamics 365 picklists?]**&#x200B;选项设置为&#x200B;**否**。 选择&#x200B;**是**&#x200B;以传播技术值。

## 将Campaign营销事件同步到Microsoft Dynamics 365

**[!UICONTROL Campaign to Microsoft Dynamics 365]**&#x200B;页面允许您标识将从Adobe Campaign映射到Microsoft Dynamics 365的电子邮件营销事件。

您可以控制的四个量度是：**发送**、**点击**、**打开**&#x200B;和&#x200B;**跳出**。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-egress.png)

选择&#x200B;**是**&#x200B;以确认您希望该类型事件流入Microsoft Dynamics 365。

单击[此处](../../integrating/using/d365-acs-self-service-app-workflows.md)了解有关这些电子邮件事件流的详细信息。

## 选择启用/禁用工作流 {#opt-in-out-wf}

**选择加入/退出**&#x200B;工作流允许您识别Microsoft Dynamics 365和Adobe Campaign之间的选择加入/退出信息流。 这假定数据与Microsoft Dynamics 365实体“联系人”和Adobe Campaign资源“配置文件”相关联。

在[本节](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out)中了解有关选择退出管理的更多信息。

请记住，您需要单击“保存”以保存您的选择。 另请注意，您必须停止&#x200B;**Campaign to Microsoft Dynamics 365**&#x200B;工作流，然后单击“播放”以便该集成合并您所做的更改。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-optinout-disabled.png)

### 选择启用/禁用同步方向

以下是同步数据的可用选项列表：

* **[!UICONTROL Disabled]**：选择此选项时，不会在Adobe Campaign和Microsoft Dynamics 365之间移动选择启用/禁用信息。

* **[!UICONTROL Unidirectional (Microsoft Dynamics 365 to Campaign)]**：此选项用于仅将选择加入/退出从Microsoft Dynamics 365流入Adobe Campaign。 集成应用程序不允许您在此屏幕中配置流；请改为单击&#x200B;**[!UICONTROL Save button]**&#x200B;并导航到&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;工作流。 在此工作流中，您可以编辑联系人/配置文件表映射，以确定您希望如何映射选择启用/禁用字段。

* **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**：此选项将使&#x200B;**映射**&#x200B;部分可见。 这些输入将允许您定义哪些Adobe Campaign字段会将数据映射到Microsoft Dynamics 365中的哪些字段。 这意味着，如果您碰巧在Microsoft Dynamics 365中手动更新某个值，那么如果该值发生更改，其值将被Adobe Campaign值覆盖。

* **[!UICONTROL Bidirectional]**：此选项将使&#x200B;**映射**&#x200B;部分可见。 这些对将标识Microsoft Dynamics 365和Adobe Campaign中的哪些字段将相互映射。 [了解详情](../../integrating/using/d365-acs-notices-and-recommendations.md)。

### 映射

此部分仅在“选择启用/禁用”同步方向字段设置为&#x200B;**[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**&#x200B;或&#x200B;**[!UICONTROL Bidirectional]**&#x200B;时适用。 您可以定义Microsoft Dynamics 365中的哪些字段映射到Adobe Campaign中的输入内容。

Microsoft Dynamics 365字段名称包括所有类型为&#x200B;**布尔值**&#x200B;的字段名称。

Adobe Campaign字段名称是特定于选择启用/禁用的一组固定值。 Adobe Campaign字段名称是特定于选择启用/禁用的一组固定值。 **无法更改此列表中的值集**。
