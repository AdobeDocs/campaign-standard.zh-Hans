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
source-wordcount: '1795'
ht-degree: 0%

---

# 同步数据

您可以将Microsoft Dynamics 365中的表与Campaign和Campaign营销量度同步到Microsoft Dynamics 365。 同步通过三个专用的技术工作流执行： **[!UICONTROL Microsoft Dynamics 365 to Campaign]**, **[!UICONTROL Campaign to Microsoft Dynamics 365]**, **[!UICONTROL Opt-In/Out]**. 请参阅此章节以 [了解更多](../../integrating/using/d365-acs-self-service-app-workflows.md).

>[!IMPORTANT]
>您需要停止/启动 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 工作流，以便将您的更改考虑在内。 [了解详情](../../integrating/using/d365-acs-self-service-app-workflows.md)

## 将表从Microsoft Dynamics 365映射到Campaign

的 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 页面显示了Microsoft Dynamics 365中的实体列表以及将与之同步的Adobe Campaign中的自定义资源。 您可以添加新映射、编辑或删除现有映射。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top.png)

下面是此表中每个列的说明：

* **[!UICONTROL MICROSOFT DYNAMICS 365 TABLE]**:此列标识Microsoft Dynamics 365中的哪个实体将是映射的数据源。

* **[!UICONTROL CAMPAIGN TABLE]**:此列标识Adobe Campaign中的哪个资源将是映射的数据目标。

* **[!UICONTROL ACTIONS]**:下面列出了可能的操作：

   * 单击 **[!UICONTROL Edit]** 图标以编辑此映射。

   * 使用  **[!UICONTROL Delete]** 图标以删除表映射。

   * 单击 **[!UICONTROL Replay Data]** 图标，以重新同步Microsoft Dynamics 365表中的所有数据。 通常，集成应用程序将仅同步Microsoft Dynamics 365中最近更改的数据。  但是，在某些情况下（例如，您进行了更改或出错），您可能希望所有数据重新同步。  在这些情况下，您可以单击此按钮，并在下次停止/启动 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 工作流中，您的数据将开始同步。

      如果您单击 **[!UICONTROL Replay Data]** 按钮且检查成功，图标将被禁用：它表示此表映射对的数据将与下次执行 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 工作流。

      当满足以下条件时，您无法选择重播数据：

      * 如果“积压”量度中有2,000,000个（或更多）项目与 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 工作流(显示在 **[!UICONTROL Workflows]** page)
      * 如果Microsoft Dynamics 365表中有2,000,000个或更多记录

      需要重新同步的记录数各不相同。 如果您有大量记录，则可能需要一些时间才能完成同步过程。 请参阅 **[!UICONTROL Backlog]** 量度 **[!UICONTROL Workflows]** 页面，因为集成应用程序会完成同步过程。

      >[!IMPORTANT]
      >
      > 强烈建议您在发布对Adobe Campaign Standard或Microsoft Dynamics 365的更改时停止集成工作流。 适用的更改包括：资源/实体（及其关联字段）、链接、标识符列等的更新。 集成当前正在使用的ID。


## 创建新映射 {#add-a-new-mapping}

要创建新映射，请执行以下步骤：

1. 在 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 页面，单击 **[!UICONTROL Add New Mapping]** 按钮。

1. 使用下拉列表选择要映射的Microsoft Dynamics 365和Campaign表。
页面上的大多数其他输入将取决于您选择的表。

   ![](assets/do-not-localize/d365-to-acs-ui-page-ingress-choose-tables.png)

   >[!NOTE]
   >不能多次映射每个表。 因此，您会注意到下拉列表选择将不包含已映射的表。

1. 单击 **[!UICONTROL OK]** 确认：该应用程序需要一个简短的时间来阅读与所选表关联的字段信息。

然后，您可以继续映射配置。 [了解详情](#new-mapping-settings)

>[!IMPORTANT]
>
>只有在首次添加映射时，才能选择此页中的表。 在单击 **[!UICONTROL Save]** 按钮：保存后，将显示表格选择字段 **只读**.

### 编辑现有映射

如果编辑现有映射，您将看到表选项不可编辑。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-table-read-only.png)

这是特意设计的，因为页面中的进一步输入基于与这些表关联的字段。 更改表会使与这些表关联的所有字段都无效。  如果要将表更改为映射，则需要返回到上一页，删除要更改的映射，然后添加新映射。

### 配置单个表映射 {#new-mapping-settings}

在此部分中，您将学习如何配置 **单个** 将一个Microsoft Dynamics 365表映射到一个Adobe Campaign表。

您可以定义以下设置：

* **[!UICONTROL Tables]**:此部分列出Microsoft Dynamics 365表的名称以及该表将映射到的Campaign表。
* **[!UICONTROL Field Mappings]**:了解详情 [此部分](#field-mappings)
* **[!UICONTROL Field Replacements]**:了解详情 [此部分](#field-replacements)
* **[!UICONTROL Filters]**:了解详情 [此部分](#filters)
* **[!UICONTROL Advanced Settings]**:了解详情 [此部分](#advanced-settings)

### 字段映射 {#field-mappings}

#### 主键

在向Campaign表映射中添加新的Microsoft Dynamics 365时，您需要标识ID字段。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-first-key.png)

Microsoft Dynamics 365主密钥为只读，因为应用程序将检测到该密钥。

对于Campaign，您需要选择哪个字段将是唯一键。 必须将其配置为 [CRM ID自定义资源](../../developing/using/uc-calling-resource-id-key.md) 和不得有重复项。

>[!NOTE]
>
>只有在您选择了 **[!UICONTROL Add New Mapping]**. 如果单击编辑按钮以编辑现有表映射，则ID字段将为只读字段。

主键将始终是 **[!UICONTROL Field Mappings]** 中。 请注意，右侧列出了以下图标，提醒您这些是主键。

![](assets/do-not-localize/d365-to-acs-icon-primary-key.png)

#### 添加其他字段映射

的 **[!UICONTROL Field Mappings]** 部分，用于添加除主键值之外的字段映射。 要将字段从Microsoft Dynamics 365添加到Adobe Campaign的新映射，请单击 **[!UICONTROL Add new field mapping]** 按钮。

在列表中选择Microsoft Dynamics 365和Campaign字段：

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-new-field-mapping.png)

这些列表包含与您在页面顶部选择的Microsoft Dynamics 365和Campaign表关联的字段名称。

的 **[!UICONTROL Apply updates]** 切换器允许您控制是否将此字段的更新从Microsoft Dynamics 365传播到Campaign:
* 如果已打开 ![](assets/do-not-localize/d365-to-acs-icon-switch-on.png)，对Microsoft Dynamics 365中值的更新将在发生更新时传播到Adobe Campaign。

* 如果你关掉了 ![](assets/do-not-localize/d365-to-acs-icon-switch-off.png)，该值将在首次加载（或重播）数据时传播，但对Microsoft Dynamics 365中字段的增量更新将不会传播。

>[!NOTE]
>
>单击 **[!UICONTROL Apply updates]** 列标题以更新 **全部** 开关或关闭。

选择字段值后，您将看到下拉菜单下方显示的数据类型。   在将值从一个字段映射到另一个字段时，请记住这一点。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-fields-selected.png)

>[!NOTE]
>
> 您无法将多个Microsoft Dynamics 365字段映射到单个Campaign字段。

### 现场替换 {#field-replacements}

使用 **[!UICONTROL Add New Field Replacement]** 按钮来定义新字段替换。

利用字段替换，可识别：

* a Microsoft Dynamics 365字段名称（已在上面的字段映射部分中添加），
* 现有值(存在于Microsoft Dynamics 365中)，以及
* 写给Adobe Campaign的新价值

将为picklist、枚举和布尔值提供下拉列表。 文本框将用于其他字符串类型和数字类型。

### 过滤器 {#filters}

使用 **[!UICONTROL Add New Filter]** 按钮，选择将哪些Microsoft Dynamics 365记录传播到Campaign。 您可以选择任何与记录关联的字段以添加到过滤器（无需将字段名称添加到字段映射）。

您可以通过填写以下信息来指定过滤器：

* Microsoft Dynamics 365字段名称
* 比较值和
* a值(来自Microsoft Dynamics 365)如果给定记录的字段名称、比较和值的计算结果为true，则该记录将会传播到Adobe Campaign。

您可以通过设置标记为的输入来选择如何评估这些过滤器 **[!UICONTROL Choose the filter comparison operator]**.  如果您选择 **和**，则所有过滤器必须为true，记录才能被传播到Campaign。 如果您选择 **或**，则当其中任何记录的评估为true时，该记录将被传播。

选项 **[!UICONTROL Do you want to delete records in Adobe Campaign Standard that will be filtered out from Microsoft Dynamics 365?]** 控制您是否希望从Campaign中删除已过滤的记录。 如果您选择 **否** 那记录将保留在Adobe Campaign。 选择 **是** 以便被集成逻辑删除。

>[!NOTE]
>
> 如果未添加过滤器，则所有已修改的记录都将传播到Adobe Campaign。

### 高级设置 {#advanced-settings}

在配置映射时，您可以设置以下其他选项：

* 设置 **[!UICONTROL Apply deletes in Microsoft Dynamics 365 to Campaign?]** 选项 **是**，如果要将在Microsoft Dynamics 365中发生的删除活动传播到Adobe Campaign中的相应字段（基于字段名称映射）。 选择 **否** 忽略在Microsoft Dynamics 365中的删除。

* 设置 **[!UICONTROL Use technical values in Microsoft Dynamics 365 picklists?]** 选项 **否** 如果要将与Microsoft Dynamics 365选取列表关联的显示值传播到Campaign。 选择 **是** 传播技术价值。

## 将促销活动营销事件同步到Microsoft Dynamics 365

的 **[!UICONTROL Campaign to Microsoft Dynamics 365]** 页面可让您识别将哪些电子邮件营销事件从Adobe Campaign映射到Microsoft Dynamics 365。

您可以控制的四个量度是： **发送**, **点击次数**, **打开**&#x200B;和 **跳出次数**.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-egress.png)

选择 **是** 以确认您确实希望此类型的事件流向Microsoft Dynamics 365。

单击 [此处](../../integrating/using/d365-acs-self-service-app-workflows.md) 以了解有关这些电子邮件事件流的更多信息。

## 选择加入/退出工作流程 {#opt-in-out-wf}

的 **选择启用/禁用** 工作流允许您识别Microsoft Dynamics 365与Adobe Campaign之间的选择启用/禁用信息的流程。 这假定数据与Microsoft Dynamics 365实体“联系人”和Adobe Campaign资源“用户档案”关联。

进一步了解 [此部分](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out).

请记住，您需要单击“保存”以保存您的选择。 另请记住，您必须停止 **Campaign到Microsoft Dynamics 365** 工作流，然后单击“播放”进行集成以合并您所做的更改。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-optinout-disabled.png)

### 选择加入/退出同步方向

以下是用于同步数据的可用选项列表：

* **[!UICONTROL Disabled]**:选择此选项后，在Adobe Campaign和Microsoft Dynamics 365之间将不会移动任何选择启用/禁用信息。

* **[!UICONTROL Unidirectional (Microsoft Dynamics 365 to Campaign)]**:此选项仅用于将选择加入/退出从Microsoft Dynamics 365流向Adobe Campaign。 集成应用程序不允许您在此屏幕中配置流程；而是单击 **[!UICONTROL Save button]**，然后导航到 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 工作流。 在此工作流中，您可以编辑联系人/配置文件表映射，以确定您希望选择加入/退出字段映射的方式。

* **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**:此选项将显示 **映射** 中。 这些输入将允许您定义哪些Adobe Campaign字段将数据映射到Microsoft Dynamics 365中的哪些字段。 这意味着如果您碰巧在Microsoft Dynamics 365中手动更新值，那么如果发生更改，则其值将被Adobe Campaign值覆盖。

* **[!UICONTROL Bidirectional]**:此选项将显示 **映射** 中。 这些对将标识Microsoft Dynamics 365和Adobe Campaign中将相互映射的字段。 [了解详情](../../integrating/using/d365-acs-notices-and-recommendations.md)。

### 映射

此部分仅在选择加入/退出同步方向字段设置为 **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** 或 **[!UICONTROL Bidirectional]**. 您可以定义Microsoft Dynamics 365中的哪些字段映射到Adobe Campaign中的哪些输入。

Microsoft Dynamics 365字段名称包含所有类型的字段名称 **布尔**.

Adobe Campaign字段名称是一组特定于选择启用/禁用的固定值。 Adobe Campaign字段名称是一组特定于选择启用/禁用的固定值。 **此列表中的值集无法更改**.
