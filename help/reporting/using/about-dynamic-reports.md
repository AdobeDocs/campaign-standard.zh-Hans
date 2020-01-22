---
title: 关于动态报告
description: 利用动态报告，将变量和维度拖放到自由形式环境中，并分析营销活动的成功。
page-status-flag: never-activated
uuid: a84a18bd-4e33-466e-a6ce-d7008fe12746
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: about-reporting
discoiquuid: bbb41c38-12c1-4625-85d5-69627e2f4b39
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a3efdc4bbd594e0dc39c94a47fd7491617cb6a2f

---


# 关于动态报告{#about-dynamic-reports}

>[!NOTE]
>
>只有具有管理权限或组织单位设置为“全部” **的用户** ，才能创建或保存新报告。 For more on this, refer to this [section](../../administration/using/users-management.md).

![](assets/dynamic_report_intro.png)

动态报告提供完全可自定义的实时报告。 它增加了对个人资料数据的访问，除了功能性电子邮件营销活动数据（如打开次数和点击次数）之外，还支持按个人资料维度（如性别、城市和年龄）进行人口统计分析。 通过拖放界面，您可以浏览数据、确定电子邮件营销活动如何针对最重要的客户细分执行以及衡量其对收件人的影响。

借助拖放菜单和可自定义的可视化功能，动态报表功能允许您将维度、指标和时间范围组合到任何组合中，并进行无限的细分和比较。


**相关主题：**

* [报告列表](../../reporting/using/defining-the-report-period.md)
* [组织单位](../../administration/using/organizational-units.md)
* [“动态报告](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/reporting/creating-a-dynamic-report.html) ”视频

## 访问动态报告 {#accessing-dynamic-reports}

可以访问报告：

* 在主页中，选择顶栏或 **[!UICONTROL Reports]**卡片中的选项卡，以访**[!UICONTROL Reports]** 问所有分发的报告。

   ![](assets/campaign_reports_access.png)

* 在每个计划、营销活动和消息中，通过单击 **Dynamic Reports** （动态报表）按钮， **** 从Reports（报表）按钮仅查看特定于分发的报表。

   ![](assets/campaign_reports_description.png)

根据收集和处理信息所花费的时间，某些报告在发送后不能立即可用。

动态报表分为两类：

* **模板**，可通过使用“另存为”选项(“项目” **>“另存为** ..”)复制模板来修&#x200B;**改这些模板。**)。
* **自定义报告** （以蓝色标识），可通过单击“报告”主页上的“创 **建新项目** ”按钮直 **接创建** 。

>[!NOTE]
>
>数据会根据您的组织单位进行筛选。

![](assets/dynamic_report_overview.png)

## 动态报告使用协议 {#dynamic-reporting-usage-agreement}

动态报告使用协议的目的是作为数据处理的弹出同意。 默认情况下，协议仅可见，且只有分配有管理权限的用户才能接受或拒绝。

有三个选项可用：

* **[!UICONTROL Ask me later]**:单击“**&#x200B;稍后询问&#x200B;**”，窗口将在24小时内停止显示。 在您接受或拒绝协议之前，配置文件维度不会显示在您的报表中，也不会收集或发送客户的个人身份信息。
* **[!UICONTROL Accept]**:接受本协议后，即授权Adobe Campaign收集客户的个人身份信息并将其传输到报告或数据中心。
* **[!UICONTROL Decline]**:拒绝协议后，您的报表中不会显示配置文件维度，也不会收集或发送客户的个人身份信息。 请注意，在这种情况下，仍将收集externalID并用于标识最终用户。

下表显示接受本协议后会发生的情况，具体取决于您所在的地区。

|  | 动态报告 | Microsoft Dynamics 365连接器 |
|---|---|---|
| 美洲和亚太地区（亚太地区） | **功能可用**。 <br>开箱即用（即，城市、国家／地区、州、性别和年龄段）以及将自定义档案信息推送到美国报告中心。 有关配置文件维的详细信息，请参阅本 [页](../../reporting/using/list-of-components-.md) | **功能可用**。 <br>所有现成和自定义配置文件字段以及Adobe Campaign Standard事件字段均在美国数据中心进行处理。 |
| EMEA（欧洲中东和非洲） | **功能可用**。 <br>开箱即用（即，城市、国家／地区、州、性别和年龄段）以及将自定义档案信息推送到EMEA报告中心。 有关配置文件维的详细信息，请参阅本 [页](../../reporting/using/list-of-components-.md) | **功能可用。** 在 <br>EMEA数据中心内处理的所有现成和自定义配置文件字段以及Adobe Campaign Standard活动字段。 <br>**[!UICONTROL Control data]** 它包含Adobe I/O注册数据和在美国数据中心发送和存储的客户最终用户活动的ID。 |

下表根据您所在的地区显示拒绝本协议后会发生什么情况。 请注意，即使您拒绝本协议，仍可报告交付情况和Microsoft Dynamics 365集成。

| 地区 | 动态报告 | Microsoft Dynamics 365连接器 |
|---|---|---|
| 美洲和亚太地区（亚太地区） | **功能可用**。 <br> 除ExternalID外，没有将现成的和自定义配置文件信息推送到美国报告中心。 | **功能可用**。 <br>除外部ID和收件人ID外，没有现成的或自定义配置文件字段发送到美国数据中心。 <br>除镜像页面ID外，所有在美国数据中心处理的Adobe Campaign standard事件字段。 <br>有关Microsoft Dynamics 365集成的详细信息，请参阅此 [页](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html)。 |
| EMEA（欧洲中东和非洲） | **功能可用**。 <br>除ExternalID外，没有将现成的和自定义配置文件信息推送到EMEA报告中心。 | **功能可用。** 除 <br>外部ID和收件人ID外，没有现成的或自定义配置文件字段发送到EMEA数据中心。 <br>除镜像页面ID外，所有在EMEA数据中心处理的Adobe Campaign Standard事件字段。  <br>**[!UICONTROL Control data]** 它包含Adobe I/O注册数据和在美国数据中心发送和存储的客户最终用户活动的ID。<br>有关Microsoft Dynamics 365集成的详细信息，请参阅此 [页](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html)。 |

此选项不是最终选项，您始终可以通过选择 **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]****[!UICONTROL Administration]** > **[!UICONTROL Application Settings]**>来更改**[!UICONTROL Options]**。

可以随时更改该值。 值1对应于 **[!UICONTROL Ask me later]**、2**[!UICONTROL Decline]** 和3 **[!UICONTROL Accept]**。

![](assets/pii_window_2.png)
