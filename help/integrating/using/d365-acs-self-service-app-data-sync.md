---
title: 在活动和Microsoft Dynamics之间同步数据
description: 在活动和Dynamics之间同步数据
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: efa30d7ed4a0caf929da6f485681078318849cda
workflow-type: tm+mt
source-wordcount: '1795'
ht-degree: 0%

---


# 同步数据

您可以将表从Microsoft Dynamics 365同步到活动和活动营销量度到Microsoft Dynamics 365。 同步通过三个专用技术工作流执行：**[!UICONTROL Microsoft Dynamics 365 to Campaign]**、**[!UICONTROL Campaign to Microsoft Dynamics 365]**、**[!UICONTROL Opt-In/Out]**。 请参阅本节[了解更多](../../integrating/using/d365-acs-self-service-app-workflows.md)。

>[!IMPORTANT]
>您需要停止/开始&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;工作流，以便将您所做的更改考虑在内。 [了解详情](../../integrating/using/d365-acs-self-service-app-workflows.md)


## 将表从Microsoft Dynamics 365映射到活动

**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;页显示Microsoft Dynamics 365中的实体列表，以及将与之同步的Adobe Campaign中的自定义资源。 您可以添加新映射、编辑或删除现有映射。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top.png)

下面是此表中各列的说明：

* **[!UICONTROL MICROSOFT DYNAMICS 365 TABLE]**:此列标识Microsoft Dynamics 365中的哪个实体将是映射的数据源。

* **[!UICONTROL CAMPAIGN TABLE]**:此列标识Adobe Campaign中的哪个资源将是映射的数据目标。

* **[!UICONTROL ACTIONS]**:以下列出了可能的操作：

   * 单击&#x200B;**[!UICONTROL Edit]**&#x200B;图标以编辑此映射。

   * 使用&#x200B;**[!UICONTROL Delete]**&#x200B;图标删除表映射。

   * 单击&#x200B;**[!UICONTROL Replay Data]**&#x200B;图标以重新同步Microsoft Dynamics 365表中的所有数据。 通常，集成应用程序只同步Microsoft Dynamics 365中最近更改的数据。  但是，在某些情况下（例如，您做出了更改或犯了错误），您可能希望所有数据重新同步。  在这些情况下，您可以单击此按钮，下次停止/开始&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;工作流时，您的数据将开始同步。

      如果单击&#x200B;**[!UICONTROL Replay Data]**&#x200B;按钮并且检查成功，则图标将被禁用：它指示此表映射对的数据将与下次执行&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;工作流时重新同步。

      当以下情况为true时，无法选择重放数据：

      * 如果“积压”量度中有2,000,000（或更多）项与&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;工作流关联（显示在&#x200B;**[!UICONTROL Workflows]**&#x200B;页中）
      * 如果Microsoft Dynamics 365表中有2,000,000或更多记录

      需要重新同步的记录数会有所不同。 如果您有大量记录，则可能需要一些时间才能完成同步过程。 当集成应用程序完成同步过程时，请参阅&#x200B;**[!UICONTROL Workflows]**&#x200B;页中的&#x200B;**[!UICONTROL Backlog]**&#x200B;量度。

      >[!IMPORTANT]
      >
      > 强烈建议您在发布对Adobe Campaign Standard或Microsoft Dynamics 365的更改时停止集成工作流。 适用的更改包括：对资源/实体（及其关联字段）、链接、标识符列等的更新 当前正由集成使用。




## 创建新映射{#add-a-new-mapping}

要创建新映射，请执行以下步骤：

1. 在&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;页面中，单击&#x200B;**[!UICONTROL Add New Mapping]**&#x200B;按钮。

1. 使用下拉列表选择要映射的Microsoft Dynamics 365和活动表。
页面上的大多数其他输入将取决于您选择的表。

   ![](assets/do-not-localize/d365-to-acs-ui-page-ingress-choose-tables.png)

   >[!NOTE]
   >不能多次映射每个表。 因此，您将注意到下拉列表选择将不包括已映射的表。

1. 单击&#x200B;**[!UICONTROL OK]**&#x200B;确认：应用程序需要一个简短的时间来阅读与选定表关联的字段信息。

然后，您可以继续进行映射配置。 [了解详情](#new-mapping-settings)

>[!IMPORTANT]
>
>只有在首次添加映射时，才能选择此页中的表。 在单击&#x200B;**[!UICONTROL Save]**&#x200B;按钮之前，请确保选择了正确的表：保存后，表选择字段将为&#x200B;**只读**。

### 编辑现有映射

如果编辑现有映射，则表选择将不可编辑。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-table-read-only.png)

这是设计的，因为页面中进一步向下的输入基于与这些表关联的字段。 更改这些表会使与这些表关联的所有字段都无效。  如果要更改要映射到的表，则需要返回到上一页，删除要更改的映射，并添加新映射。

### 配置单个表映射{#new-mapping-settings}

在本节中，您将学习如何将一个Microsoft Dynamics 365表的&#x200B;**单个**&#x200B;映射配置为一个Adobe Campaign表。

您可以定义以下设置：

* **[!UICONTROL Tables]**:此部分列表了Microsoft Dynamics 365表的名称和将要将其映射到的活动表。
* **[!UICONTROL Field Mappings]**:在此部分了解 [更多信息](#field-mappings)
* **[!UICONTROL Field Replacements]**:在此部分了解 [更多信息](#field-replacements)
* **[!UICONTROL Filters]**:在此部分了解 [更多信息](#filters)
* **[!UICONTROL Advanced Settings]**:在此部分了解 [更多信息](#advanced-settings)

### 字段映射{#field-mappings}

#### 主键

在将新的Microsoft Dynamics 365添加到活动表映射时，需要标识ID字段。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-first-key.png)

Microsoft Dynamics 365主键是只读的，因为应用程序将检测到它。

对于活动，您需要选择哪个字段将是唯一键。 它必须配置为[CRM ID自定义资源](../../developing/using/uc-calling-resource-id-key.md)，且不得具有重复。

>[!NOTE]
>
>只有在您选择了&#x200B;**[!UICONTROL Add New Mapping]**&#x200B;后，才能选择表上的ID字段。 如果单击编辑按钮编辑现有表映射，则ID字段将为只读。

主键将始终是&#x200B;**[!UICONTROL Field Mappings]**&#x200B;部分中列出的第一个字段名。 作为提醒，右侧列出了以下图标，以提醒您这些是主键。

![](assets/do-not-localize/d365-to-acs-icon-primary-key.png)

#### 添加其他字段映射

**[!UICONTROL Field Mappings]**&#x200B;部分允许您添加除主键之外的字段映射。 要将字段从Microsoft Dynamics 365新映射到Adobe Campaign，请单击&#x200B;**[!UICONTROL Add new field mapping]**&#x200B;按钮。

在列表中选择Microsoft Dynamics 365和活动字段：

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-new-field-mapping.png)

这些列表包含与Microsoft Dynamics 365关联的字段名称以及您在页面顶部选择的活动表。

**[!UICONTROL Apply updates]**&#x200B;切换器允许您控制是否将对此字段的更新从Microsoft Dynamics 365传播到活动:
* 如果它已打开![](assets/do-not-localize/d365-to-acs-icon-switch-on.png)，则对Microsoft Dynamics 365中值的更新将在更新发生时传播到Adobe Campaign。

* 如果关闭![](assets/do-not-localize/d365-to-acs-icon-switch-off.png)，则该值将在最初加载（或重播）数据时传播，但对Microsoft Dynamics 365中字段的增量更新将不会传播。

>[!NOTE]
>
>单击&#x200B;**[!UICONTROL Apply updates]**&#x200B;列标题可将交换机的&#x200B;**所有**&#x200B;更新为开或关。


选择字段值时，您将看到下拉菜单下方显示的数据类型。   在将值从一个字段映射到另一个字段时，应牢记这一点。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-fields-selected.png)

>[!NOTE]
>
> 不能将多个Microsoft Dynamics 365字段映射到单个活动字段。

### 现场替换{#field-replacements}

使用&#x200B;**[!UICONTROL Add New Field Replacement]**&#x200B;按钮定义新的字段替换。

现场替换允许您识别：

* a Microsoft Dynamics 365字段名称（已在字段映射部分中添加），
* 现有值（存在于Microsoft Dynamics 365中）和
* 写入Adobe Campaign的新值

将为picklist、明细列表和布尔值提供下拉列表列表。 文本框将用于其他字符串和数字类型。

### 过滤器{#filters}

使用&#x200B;**[!UICONTROL Add New Filter]**&#x200B;按钮选择将哪些Microsoft Dynamics 365记录传播到活动。 您可以选择与记录关联的任何字段以添加到过滤器（无需将字段名称添加到字段映射）。

通过填写以下信息来指定过滤器：

* Microsoft Dynamics 365字段名称
* 比较值，
* a值（来自Microsoft Dynamics 365）
如果给定记录的字段名称、比较和值的计算结果为true，则记录将传播到Adobe Campaign。

您可以通过设置标有&#x200B;**[!UICONTROL Choose the filter comparison operator]**&#x200B;的输入来选择如何评估这些过滤器。  如果选择&#x200B;**和**，则所有过滤器都必须为true，记录才能传播到活动。 如果选择&#x200B;**Or**，则如果其中任何记录的计算结果为true，则将传播该记录。

选项&#x200B;**[!UICONTROL Do you want to delete records in Adobe Campaign Standard that will be filtered out from Microsoft Dynamics 365?]**&#x200B;控制是否希望从活动中删除已过滤出的记录。 如果选择&#x200B;**否**，则记录将保留在Adobe Campaign中。 选择&#x200B;**是**，以将其由集成逻辑删除。

>[!NOTE]
>
> 如果未添加任何过滤器，则所有已修改的记录都将传播到Adobe Campaign。


### 高级设置{#advanced-settings}

在配置映射时，您可以设置以下其他选项：

* 如果要将在Microsoft Dynamics 365中发生的删除传播到Adobe Campaign中的相应字段（基于字段名称映射），请将&#x200B;**[!UICONTROL Apply deletes in Microsoft Dynamics 365 to Campaign?]**&#x200B;选项设置为&#x200B;**是**。 选择&#x200B;**否**&#x200B;可忽略Microsoft Dynamics 365中的删除操作。

* 如果要传播以活动与Microsoft Dynamics 365选择列表关联的显示值，请将&#x200B;**[!UICONTROL Use technical values in Microsoft Dynamics 365 picklists?]**&#x200B;选项设置为&#x200B;**否**。 选择&#x200B;**是**&#x200B;以传播技术值。

## 将活动营销事件同步到Microsoft Dynamics 365

通过&#x200B;**[!UICONTROL Campaign to Microsoft Dynamics 365]**&#x200B;页面，可确定将哪些电子邮件营销事件从Adobe Campaign映射到Microsoft Dynamics 365。

您可以控制的四个指标是：**发送**、**单击**、**打开**&#x200B;和&#x200B;**弹回**。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-egress.png)

选择&#x200B;**是**&#x200B;以确认您确实希望该类型的事件流向Microsoft Dynamics 365。

单击[此处](../../integrating/using/d365-acs-self-service-app-workflows.md)可了解有关这些电子邮件事件流的详细信息。

## 选择加入/out workflow {#opt-in-out-wf}

**选择加入/退出**&#x200B;工作流允许您识别Microsoft Dynamics 365和Adobe Campaign之选择加入间的/退出信息流。 这假定数据与Microsoft Dynamics 365实体“联系”和Adobe Campaign资源“用户档案”关联。

了解有关[本节](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out)中退出管理的更多信息。

请记住，您需要单击“保存”以保存您的选择。 还要记住，您必须停止&#x200B;**对Microsoft Dynamics 365**&#x200B;工作流的活动，然后单击“播放”进行集成，以合并您的更改。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-optinout-disabled.png)

### 选择加入

以下是同步数据的可用选项的列表:

* **[!UICONTROL Disabled]**:选择此选项后，在Adobe Campaign选择加入和Microsoft Dynamics 365之间将不移动/移出信息。

* **[!UICONTROL Unidirectional (Microsoft Dynamics 365 to Campaign)]**:此选项用于仅将Microsoft Dynamics 365中的选择加入/退出流至Adobe Campaign。集成应用程序不允许您在此屏幕中配置流；相反，单击&#x200B;**[!UICONTROL Save button]**，然后导航到&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;工作流。 在此工作流中，您可以编辑联系人/用户档案表映射，以确定您希望如何映射选择加入/退出字段。

* **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**:此选项将显示“映射 **** ”部分。这些输入将允许您定义哪些Adobe Campaign字段将数据映射到Microsoft Dynamics 365中的哪些字段。 这意味着，如果您碰巧在Microsoft Dynamics 365中手动更新值，则其值将被Adobe Campaign值覆盖（如果它发生更改）。

* **[!UICONTROL Bidirectional]**:此选项将显示“映射 **** ”部分。这些对将标识Microsoft Dynamics 365和Adobe Campaign中将相互映射哪些字段。 [了解详情](../../integrating/using/d365-acs-notices-and-recommendations.md)。

### 映射

此部分仅在“选择加入/退出同步方向”字段设置为&#x200B;**[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**&#x200B;或&#x200B;**[!UICONTROL Bidirectional]**&#x200B;时适用。 您可以定义Microsoft Dynamics 365中的哪些字段映射到Adobe Campaign中的哪些输入。

Microsoft Dynamics 365字段名称包括所有类型为&#x200B;**boolean**&#x200B;的字段名称。

Adobe Campaign字段名称是特定于选择加入/退出的一组固定值。 Adobe Campaign字段名称是特定于选择加入/退出的一组固定值。 **无法更改此列表中的值集**。
