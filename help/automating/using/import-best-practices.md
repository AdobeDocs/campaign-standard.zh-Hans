---
title: 导入最佳实践
description: 进一步了解将数据导入数据库时要遵循的最佳实践。
page-status-flag: never-activated
uuid: d909d26a-cf50-46af-ae09-f0fd7258ca27
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 75b83165-dcbd-4bb7-b703-ed769f489b16
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 0%

---


# 导入最佳实践 {#import-best-practices}

谨慎并遵循下面详述的几个简单规则将有助于确保数据库内数据的一致性，避免在数据库更新或数据导出过程中出现常见错误。

## 使用导入模板 {#using-import-templates}

大多数导入工作流应包含以下活动: **[!UICONTROL Load file]**、 **[!UICONTROL Reconciliation]**、 **[!UICONTROL Segmentation]**、 **[!UICONTROL Deduplication]**、 **[!UICONTROL Update data]**。

使用导入模板可以非常方便地准备类似的导入并确保数据库中的数据一致性。

在许多项目中，导入是无 **[!UICONTROL Deduplication]** 活动构建的，因为项目中使用的文件没有重复。 重复有时会从导入其他文件时显示。 因此，重复数据消除很困难。 因此，外部重复数据删除步骤是所有进口工作流的良好预防措施。

切勿假定传入数据是一致、正确的，或由IT部门或Adobe Campaign主管负责处理。 在项目过程中，请牢记数据清理。 在导入数据时，消除重复、协调和维护一致性。

为导入数据而设计的通用工作流模板的示例在示例中 [可用： “导入工作流模板](#example--import-workflow-template) ”部分。

>[!NOTE]
>
>您还可以使用 [导入模板](../../automating/using/importing-data-with-import-templates.md)。 它们是由管理员定义的工作流模板，一旦激活，管理员只会优惠指定包含要导入数据的文件的可能性。

**相关主题：**

* [加载文件活动](../../automating/using/load-file.md)
* [对帐活动](../../automating/using/reconciliation.md)
* [细分活动](../../automating/using/segmentation.md)
* [外部重复数据删除活动](../../automating/using/deduplication.md)
* [更新数据活动](../../automating/using/update-data.md)

## 使用平面文件格式 {#using-flat-file-formats}

导入的最有效格式是平面文件。 平面文件可以在数据库级别以批量模式导入。

例如：

* 分隔符： 制表符或分号
* 带标题的第一行
* 无字符串分隔符
* 日期格式： YYYY/MM/DD HH:mm:SS

要导入的文件示例：

```
lastname;firstname;birthdate;email;crmID
Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
Mars;Daniel;17/11/1987;dannymars@example.com;123545
Smith;Clara;08/02/1989;hayden.smith@example.com;124567
Durance;Allison;15/12/1978;allison.durance@example.com;120987
```

## 使用压缩 {#using-compression}

尽可能使用压缩文件进行导入和导出。 默认支持GZIP。 您可以分别在导入文件时添加预处理，在提取数据时添加后处理，在工作流活动 **[!UICONTROL Load file]** 和工作流 **[!UICONTROL Extract file]** 中添加。

**相关主题：**

* [加载文件活动](../../automating/using/load-file.md)
* [提取文件活动](../../automating/using/extract-file.md)

## 在增量模式下导入 {#importing-in-delta-mode}

常规导入必须在增量模式下完成。 这意味着每次只向Adobe Campaign发送修改或新数据，而不是向整个表发送。

完全导入应仅用于初始加载。

## 维护一致性 {#maintaining-consistency}

要在Adobe Campaign库中保持数据一致性，请遵循以下原则：

* 如果导入的数据与Adobe Campaign中的引用表匹配，则应将其与工作流中的该表协调。 不匹配的记录应被拒绝。
* 确保导入的数据始终“ **标准化** ”（电子邮件、电话号码、直接邮件地址），并且此标准化是可靠的，并且多年内不会更改。 如果不是这样，某些重复可能会出现在Adobe Campaign库中，而由于不提供进行“模糊”匹配的工具，因此很难管理和删除这些数据。
* 事务数据应具有合并关键项并与现有数据协调，以避免创建重复。
* **按顺序导入相关文件**。 如果导入由多个相互依赖的文件组成，则工作流应确保以正确的顺序导入文件。 文件失败时，不导入其他文件。
* **在导入**&#x200B;数据时，消除重复、协调并维护一致性。
