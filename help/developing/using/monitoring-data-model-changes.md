---
title: 监视数据模型的变化
description: 了解如何诊断Adobe Campaign数据模型。
audience: developing
content-type: reference
topic-tags: about-custom-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: ced9a897-47e9-4128-84fb-35660c553cd4
source-git-commit: 5fef74296a4790102c75e609c270e52d5ead1d58
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 8%

---

# 监视数据模型的变化{#monitoring-data-model-changes}

从 **[!UICONTROL Diagnosis]** 菜单下，您可以查看应用程序生成的技术对象，以便对其进行分析。

>[!NOTE]
>
>此菜单中的屏幕为只读。

![](assets/diagnostic.png)

您可以查看以下类型的对象：

* 数据模式
* 网页
* 筛选器
* 导航
* 组件
* 批处理作业

您可以更改列表配置：

* 您可以添加和删除列。
* 您可以定义列名。
* 您可以定义列表中列的显示顺序。
* 您可以选择列表中值的排序顺序。

您可以筛选列表：

* 您可以包含或排除本机数据架构、网页、筛选器和导航对象。
* 您可以按对象名称搜索对象。
* 您可以根据批处理作业的状态、开始日期和结束日期对其进行筛选。

您可以以TXT格式下载显示的列表，该文件具有逗号分隔值。

您可以查看所选对象的详细信息。

例如，您可以使用此功能查看现成过滤器的过滤条件。 此示例显示了为现成过滤器的过滤条件显示的代码：

```xml
<where displayFilter="Has clicked an offer">
  <condition boolOperator="AND" enabledIf="$(offer) != ''" expr="trackingLog" internalId="1" setOperator="EXISTS">
    <condition boolOperator="AND" expr="[url/offer] = $RestKey(offer)" internalId="2"/>
    <condition boolOperator="AND" expr="[@url-id] != 1" internalId="3"/>
  </condition>
</where>
```

![](assets/diagnosis_filter_criteria.png)