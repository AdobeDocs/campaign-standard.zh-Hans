---
title: 动态报告快速入门
description: 通过动态报告，将变量和维度拖放到自由格式环境中，并分析促销活动是否成功。
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Beginner
exl-id: fc3b28f3-63f6-4edc-923d-c7eb7925d1b7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 5%

---

# 动态报告快速入门 {#about-dynamic-reports}

动态报告提供完全可自定义的实时报告。 它增加了对用户档案数据的访问权限，从而除了功能电子邮件促销活动数据（如打开数和点击数）之外，还允许按用户档案维度（如性别、城市和年龄）进行人口统计分析。 通过拖放界面，您可以浏览数据，确定电子邮件活动针对最重要的客户细分执行情况，并衡量其对收件人的影响。

>[!NOTE]
>
>仅具有管理权限或将组织单位设置为 **全部** 可以创建或保存新报表。 有关更多信息，请参阅此](../../administration/using/users-management.md)章节[。

## 访问动态报告 {#accessing-dynamic-reports}

可以访问报表：

* 通过选择 **[!UICONTROL Reports]** 的 **[!UICONTROL Reports]** 卡以访问所有投放的报告。

   ![](assets/campaign_reports_access.png)

* 在每个项目、营销策划和消息中， **报表** 按钮 **动态报告** 以仅查看特定于投放的报表。

   ![](assets/campaign_reports_description.png)

某些报表在投放后无法立即可用，具体取决于收集和处理信息所花费的时间。

动态报告分为两类：

* **模板**，可通过使用 **另存为** 选项(**项目>另存为……**)。
* **自定义报表** （以蓝色标识），可通过单击 **创建新项目** 按钮 **报表** 主页。

>[!NOTE]
>
>数据会根据您的组织单位进行过滤。

![](assets/dynamic_report_overview.png)

## 动态报告使用协议 {#dynamic-reporting-usage-agreement}

动态报告使用协议的目的是作为数据处理的弹出式同意。 默认情况下，协议仅可见，且只有分配了管理权限的用户才能接受或拒绝协议。

提供了以下三个选项：

* **[!UICONTROL Ask me later]**:通过单击 **晚点问我**，则窗口将在24小时内停止显示。 在您接受或拒绝协议之前，配置文件维度将不会显示在您的报表中，并且也不会收集或发送您客户的个人身份信息。
* **[!UICONTROL Accept]**:接受本协议后，您将授权Adobe Campaign收集客户的个人身份信息，并将其传输到报表或数据中心。
* **[!UICONTROL Decline]**:拒绝协议后，用户档案维度将不会显示在您的报表中，并且也不会收集或发送客户的个人身份信息。 请注意，在这种情况下，仍将收集并使用externalID来标识最终用户。

下表显示了接受此协议后，根据您所在的地区所发生的情况。

|  | 动态报告 | Microsoft Dynamics 365连接器 |
|---|---|---|
| 美洲和亚太地区（亚太地区） | **可用功能**. <br>开箱即用（例如，城市、国家/地区、州、性别和年龄段）以及推送到美国报告中心的自定义用户档案信息。 有关用户档案维度的更多信息，请参阅此 [页面](../../reporting/using/list-of-components-.md) | **可用功能**. <br>所有现成和自定义的用户档案字段和Adobe Campaign Standard事件字段均在美国数据中心进行处理。 |
| EMEA（欧洲中东和非洲） | **可用功能**. <br>开箱即用（即按年龄划分的城市、国家/地区、州、性别和区段）以及推送到EMEA报告中心的自定义用户档案信息。 有关用户档案维度的更多信息，请参阅此 [页面](../../reporting/using/list-of-components-.md) | **功能可用。** <br>在EMEA数据中心处理的所有现成和自定义用户档案字段和Adobe Campaign Standard事件字段。 <br>**[!UICONTROL Control data]**其中包含Adobe I/O注册数据和在美国数据中心发送和存储的客户最终用户事件的ID。 |

下表显示了拒绝此协议后将发生的情况，具体取决于您所在的地区。 请注意，即使您拒绝此协议，仍将提供有关投放和Microsoft Dynamics 365集成的报告。

| 地区 | 动态报告 | Microsoft Dynamics 365连接器 |
|---|---|---|
| 美洲和亚太地区（亚太地区） | **可用功能**. <br> 除ExternalID外，没有现成的和自定义的用户档案信息被推送到美国报表中心。 | **可用功能**. <br>除外部ID和收件人ID外，不会向美国数据中心发送现成的或自定义用户档案字段。 <br>除镜像页面ID外，美国数据中心中处理的所有Adobe Campaign Standard事件字段。 <br>有关Microsoft Dynamics 365集成的更多信息，请参阅此 [页面](../../integrating/using/d365-acs-get-started.md). |
| EMEA（欧洲中东和非洲） | **可用功能**. <br>除ExternalID外，没有现成的和自定义的用户档案信息推送到EMEA报告中心。 | **功能可用。** <br>除外部ID和收件人ID外，不会向EMEA数据中心发送现成的或自定义用户档案字段。 <br>除镜像页面ID外，EMEA数据中心处理的所有Adobe Campaign Standard事件字段。  <br>**[!UICONTROL Control data]**其中包含Adobe I/O注册数据和在美国数据中心发送和存储的客户最终用户事件的ID。<br>有关Microsoft Dynamics 365集成的更多信息，请参阅此 [页面](../../integrating/using/d365-acs-get-started.md). |

此选项不是最终选项，您始终可以通过选择 **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]** in **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**.

值可随时更改。 值1对应于 **[!UICONTROL Ask me later]**, 2 **[!UICONTROL Decline]** 和3 **[!UICONTROL Accept]**.

![](assets/pii_window_2.png)
