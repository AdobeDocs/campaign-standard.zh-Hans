---
solution: Campaign Standard
product: campaign
title: 动态报告快速入门
description: 利用动态报表，将变量和维度拖放到自由形式环境中，并分析活动的成功。
audience: reporting
content-type: reference
topic-tags: about-reporting
translation-type: tm+mt
source-git-commit: b471fddd49037770e33a113374afd60c2e79e69b
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 5%

---


# 动态报告快速入门 {#about-dynamic-reports}

动态报告提供完全可自定义的实时报告。 它增加了对用户档案数据的访问，除了功能性电子邮件分析数据（如打开和点击）之外，还通过性别、城市和年龄等用户档案维度实现人口统计活动。 通过拖放界面，您可以浏览数据，确定电子邮件活动针对最重要的客户细分执行情况，并衡量其对收件人的影响。

>[!NOTE]
>
>只有具有管理权限或将组织单位设置为&#x200B;**All**&#x200B;的用户才能创建或保存新报告。 有关更多信息，请参阅此](../../administration/using/users-management.md)章节[。

## 访问动态报告{#accessing-dynamic-reports}

可以访问报告：

* 在主页中，选择顶部栏或&#x200B;**[!UICONTROL Reports]**&#x200B;卡中的&#x200B;**[!UICONTROL Reports]**&#x200B;选项卡以访问所有投放的报告。

   ![](assets/campaign_reports_access.png)

* 在每个项目、活动和消息中，从&#x200B;**Reports**&#x200B;按钮单击&#x200B;**Dynamic Reports**，以仅视图特定于投放的报表。

   ![](assets/campaign_reports_description.png)

某些报表在投放后不能立即可用，具体取决于收集和处理信息所花费的时间。

动态报表分为两个类别:

* **模板**，可通过使用“另存为”选项(“项目”>“另存 **为”** )复制模&#x200B;**板来对其进行修改。**)。
* **自定义报表** （以蓝色标识），可通过单击“报表”页面上的“创 **建新** 项目”按钮直接 **** 创建。

>[!NOTE]
>
>数据会根据您的组织单位进行过滤。

![](assets/dynamic_report_overview.png)

## 动态报告使用协议{#dynamic-reporting-usage-agreement}

动态报告使用协议的目的是作为数据处理的弹出式同意。 默认情况下，协议仅可见，且只能由分配有管理权限的用户接受或拒绝。

有三个选项可用：

* **[!UICONTROL Ask me later]**:单击“ **稍后询问**”，窗口将在24小时内停止显示。在您接受或拒绝协议之前，用户档案维度不会显示在您的报表中，也不会收集或发送您客户的个人身份信息。
* **[!UICONTROL Accept]**:接受本协议后，即表示您授权Adobe Campaign收集客户的个人身份信息并将其传输到报告或数据中心。
* **[!UICONTROL Decline]**:拒绝协议后，用户档案维度将不会显示在报表中，也不会收集或发送客户的个人身份信息。请注意，在这种情况下，仍将收集externalID并用于标识最终用户。

下表显示接受本协议后会发生的情况，具体取决于您所在的地区。

|  | 动态报告 | Microsoft Dynamics 365连接器 |
|---|---|---|
| 美洲和亚太地区（亚太地区） | **功能可用**。<br>开箱即用（即根据年龄划分的城市、国家/地区、州、性别和细分）和定制用户档案信息推送到美国报告中心。有关用户档案维度的详细信息，请参阅此[页面](../../reporting/using/list-of-components-.md) | **功能可用**。<br>所有现成和自定义用户档案字段和Adobe Campaign Standard事件字段均在美国数据中心进行处理。 |
| EMEA（欧洲中东和非洲） | **功能可用**。<br>开箱即用（即，城市、国家/地区、州、性别和按年龄划分的细分）和定制用户档案信息推送到EMEA报告中心。有关用户档案维度的详细信息，请参阅此[页面](../../reporting/using/list-of-components-.md) | **功能可用。** <br>所有现成和自定义用户档案字段和Adobe Campaign Standard事件字段均在EMEA数据中心处理。<br>**[!UICONTROL Control data]**它包含Adobe I/O注册数据和在美国数据中心发送和存储的客户最终用户事件的ID。 |

下表显示拒绝此协议后发生的情况，具体取决于您所在的地区。 请注意，即使您拒绝此协议，投放和Microsoft Dynamics 365集成的报告仍将可用。

| 地区 | 动态报告 | Microsoft Dynamics 365连接器 |
|---|---|---|
| 美洲和亚太地区（亚太地区） | **功能可用**。<br> 除ExternalID外，没有将现成的和自定义用户档案信息推送到美国报告中心。 | **功能可用**。<br>除外部ID和用户档案ID外，没有发送到美国数据中心的现成或自定义收件人字段。<br>除了Adobe Campaign Standard ID外，所有在美国数据中心处理的镜像页面事件字段。<br>有关Microsoft Dynamics 365集成的详细信息，请参阅此 [页](../../integrating/using/d365-acs-get-started.md)。 |
| EMEA（欧洲中东和非洲） | **功能可用**。<br>除ExternalID外，没有将现成的和自定义用户档案信息推送到EMEA报告中心。 | **功能可用。** <br>除外部ID和用户档案ID外，没有现成的或自定义收件人字段发送到EMEA数据中心。<br>除了Adobe Campaign Standard ID外，所有在EMEA事件中心处理的镜像页面字段。<br>**[!UICONTROL Control data]**它包含Adobe I/O注册数据和在美国数据中心发送和存储的客户最终用户事件的ID。<br>有关Microsoft Dynamics 365集成的详细信息，请参阅此 [页](../../integrating/using/d365-acs-get-started.md)。 |

此选项不是最终选项，您始终可以通过选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**&#x200B;中的&#x200B;**[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]**&#x200B;来更改它。

该值可随时更改。 值1对应于&#x200B;**[!UICONTROL Ask me later]**、2 **[!UICONTROL Decline]**&#x200B;和3 **[!UICONTROL Accept]**。

![](assets/pii_window_2.png)
