---
title: 查询范例
description: 本节介绍使用查询活动时的用例。
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d994d85f126951215f1227301599c554c1f12c8
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 0%

---


# 查询范例 {#query-samples}

本节介绍使用活动时的用 **[!UICONTROL Query]** 例。 有关如何使用活动的 **[!UICONTROL Query]** 详细信息，请 [参阅本节](../../automating/using/query.md)。

## 基于简单用户档案属性定位 {#targeting-on-simple-profile-attributes}

以下示例展示了一个查询活动，其配置为居住在伦敦的18至30岁的目标男子。

![](assets/query_sample_1.png)

## 根据电子邮件属性定位 {#targeting-on-email-attributes}

以下示例显示了配置为将查询活动与电子邮件地址域“orange.co.uk”目标用户档案的。

![](assets/query_sample_emaildomain.png)

以下示例显示配置为查询其电子邮件地址已提供的目标用户档案的活动。

![](assets/query_sample_emailnotempty.png)

## 瞄准生日在今天的用户档案 {#targeting-profiles-whose-birthday-is-today}

以下示例显示了一个查询活动，该用户档案配置为目标生日为今天的。

1. 在查询 **[!UICONTROL Birthday]** 中拖动过滤器。

   ![](assets/query_sample_birthday.png)

1. 将设置 **[!UICONTROL Filter type]** 为并 **[!UICONTROL Relative]** 选择 **[!UICONTROL Today]**。

   ![](assets/query_sample_birthday2.png)

## 定位打开特定投放的用户档案 {#targeting-profiles-who-opened-a-specific-delivery}

以下示例显示了一个查询活动，其配置为过滤打开投放并标有“Summer Time”的用户档案。

1. 在查询 **[!UICONTROL Opened]** 中拖动过滤器。

   ![](assets/query_sample_opened.png)

1. 选择投放，然后单击 **[!UICONTROL Confirm]**。

   ![](assets/query_sample_opened2.png)

## 针对因特定原因投放失败的用户档案 {#targeting-profiles-for-whom-deliveries-failed-for-a-specific-reason}

以下示例显示了一个查询活动，其配置为过滤因其邮箱已满而导致投放失败的用户档案。 此查询仅适用于具有管理权限且属于组织单位的 **[!UICONTROL All (all)]** 用户(请参 [阅本节](../../administration/using/organizational-units.md))。

1. 选择资 **[!UICONTROL Delivery logs]** 源，以便直接在投放日志表中进行筛选(请参 [阅使用不同于定位维度的资源](../../automating/using/using-resources-different-from-targeting-dimensions.md))。

   ![](assets/query_sample_failure1.png)

1. 在查询 **[!UICONTROL Nature of failure]** 中拖动过滤器。

   ![](assets/query_sample_failure2.png)

1. 选择要目标的失败类型。 以我们为例 **[!UICONTROL Mailbox full]**。

   ![](assets/query_sample_failure3.png)

## 过去7天内未联系定位用户档案 {#targeting-profiles-not-contacted-during-the-last-7-days}

以下示例显示了一个查询活动，其配置为过滤过去7天内未联系到的用户档案。

1. 在查询 **[!UICONTROL Delivery logs (logs)]** 中拖动过滤器。

   ![](assets/query_sample_7days.png)

   在 **[!UICONTROL Does not exist]** 下拉列表中选择，然后拖动筛 **[!UICONTROL Delivery]** 选器。

   ![](assets/query_sample_7days1.png)

1. 按如下配置筛选器。

   ![](assets/query_sample_7days2.png)

## 定位单击特定链接的用户档案 {#targeting-profiles-who-clicked-a-specific-link-}

1. 在查询 **[!UICONTROL Tracking logs (tracking)]** 中拖动过滤器。

   ![](assets/query_sample_trackinglogs.png)

1. 拖动滤 **[!UICONTROL Label (urlLabel)]** 镜。

   ![](assets/query_sample_trackinglogs2.png)

1. 在字 **[!UICONTROL Value]** 段中，键入在投放中插入链接时定义的标签，然后进行确认。

   ![](assets/query_sample_trackinglogs3.png)
