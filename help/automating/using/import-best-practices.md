---
title: 导入最佳实践
description: 详细了解将数据导入数据库时应遵循的最佳实践。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
exl-id: bb651b91-145f-4e87-92dd-a8b04662e380
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 2%

---

# 导入最佳实践 {#import-best-practices}

>[!CAUTION]
>
>使用此功能时，请记住Adobe Campaign合同规定的SFTP存储、DB存储和活动配置文件限制。

谨慎并遵循下面详述的少数简单规则，将有助于确保数据库内的数据一致性，并避免在数据库更新或数据导出期间出现常见错误。

## 使用导入模板 {#using-import-templates}

大多数导入工作流应包含以下活动： **[!UICONTROL Load file]**， **[!UICONTROL Reconciliation]**， **[!UICONTROL Segmentation]**， **[!UICONTROL Deduplication]**， **[!UICONTROL Update data]**.

使用导入模板，可以非常方便地准备类似的导入并确保数据库中的数据一致性。

在许多项目中，导入是在没有 **[!UICONTROL Deduplication]** 活动，因为项目中使用的文件没有重复项。 导入不同文件时有时会出现重复项。 然后，重复数据消除就变得很困难。 因此，在所有导入工作流中，重复数据删除步骤都是很好的预防措施。

请不要假定传入的数据是一致和正确的，或者由IT部门或Adobe Campaign主管来处理。 在项目进行期间，请牢记数据清理。 在导入数据时执行重复数据删除、协调操作并保持一致性。

有关为导入数据而设计的通用工作流模板的示例，请参阅 [示例：导入工作流模板](../../automating/using/creating-import-workflow-templates.md) 部分。

>[!NOTE]
>
>您还可以使用 [导入模板](../../automating/using/importing-data-with-import-templates.md). 它们是管理员定义的工作流模板，激活后只能指定包含导入数据的文件。

**相关主题：**

* [加载文件活动](../../automating/using/load-file.md)
* [协调活动](../../automating/using/reconciliation.md)
* [分段活动](../../automating/using/segmentation.md)
* [重复数据删除活动](../../automating/using/deduplication.md)
* [更新数据活动](../../automating/using/update-data.md)

## 使用平面文件格式 {#using-flat-file-formats}

对于导入，最有效的格式是平面文件。 可以在数据库级别以批量模式导入平面文件。

例如：

* 分隔符：制表符或分号
* 带有标题的第一行
* 无字符串分隔符
* 日期格式：YYYY/MM/DD HH:mm:SS

要导入的文件示例：

```
lastname;firstname;birthdate;email;crmID
Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
Mars;Daniel;17/11/1987;dannymars@example.com;123545
Smith;Clara;08/02/1989;hayden.smith@example.com;124567
Durance;Allison;15/12/1978;allison.durance@example.com;120987
```

## 使用压缩 {#using-compression}

尽可能将压缩文件用于导入和导出。 默认支持GZIP。 在导入文件时可添加预处理，在提取数据时可添加后处理，这分别位于 **[!UICONTROL Load file]** 和 **[!UICONTROL Extract file]** 工作流活动。

**相关主题：**

* [加载文件活动](../../automating/using/load-file.md)
* [提取文件活动](../../automating/using/extract-file.md)

## 在Delta模式下导入 {#importing-in-delta-mode}

常规导入必须在增量模式下完成。 这意味着只向Adobe Campaign发送修改的数据或新数据，而不是每次都发送整个表。

完全导入只能用于初始加载。

## 保持一致性 {#maintaining-consistency}

要维护Adobe Campaign数据库中的数据一致性，请遵循以下原则：

* 如果导入的数据与Adobe Campaign中的引用表匹配，则应将其与工作流中的该表进行协调。 应拒绝不匹配的记录。
* 确保导入的数据始终为 **&quot;normalized&quot;** （电子邮件、电话号码、直邮地址），并且此标准化是可靠的，不会随着时间而改变。 如果不是这种情况，数据库中可能会出现一些重复项，并且由于Adobe Campaign不提供进行“模糊”匹配的工具，因此将很难管理和删除它们。
* 事务型数据应具有协调键值，并与现有数据进行协调，以避免创建重复项。
* **按顺序导入相关文件**. 如果导入由多个相互依赖的文件组成，则工作流应确保这些文件按正确的顺序导入。 当文件失败时，不会导入其他文件。
* **删除重复项**，在导入数据时协调并保持一致性。
