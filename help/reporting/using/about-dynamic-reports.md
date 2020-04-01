---
title: 关于动态报告
description: 利用动态报表，将变量和维度拖放到自由格式环境中并分析活动的成功。
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
source-git-commit: a1bc9d23163d12517c4501a572fc92aac6aacbc6

---


# 关于动态报告{#about-dynamic-reports}

>[!NOTE]
>
>只有具有管理权限或组织单位设置为“全部” **的用户** ，才能创建或保存新报告。 For more on this, refer to this [section](../../administration/using/users-management.md).

![](assets/dynamic_report_intro.png)

动态报告提供完全可自定义的实时报告。 它增加了对用户档案数据的访问，除了功能性电子邮件分析数据（如打开和点击）之外，还通过用户档案维度（如性别、城市和年龄）实现人口统计活动。 通过拖放界面，您可以浏览数据、确定电子邮件活动对最重要客户细分的执行方式并衡量其对收件人的影响。

借助拖放菜单和可自定义的可视化功能，动态报表功能允许您将维度、指标和时间范围组合到任何组合中，并进行无限的细分和比较。


**相关主题：**

* [报告列表](../../reporting/using/defining-the-report-period.md)
* [组织单位](../../administration/using/organizational-units.md)
* [“动态报告](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/reporting/creating-a-dynamic-report.html) ”视频

## 访问动态报告 {#accessing-dynamic-reports}

可以访问报告：

* 在主页中，选择顶 **[!UICONTROL Reports]** 栏或卡中的选项卡，以访 **[!UICONTROL Reports]** 问所有投放的报告。

   ![](assets/campaign_reports_access.png)

* 在每个项目、活动和消息中，通过单击“ **Reports** ”按钮，从“ **Reports** ”按钮仅视图特定于投放的报表。

   ![](assets/campaign_reports_description.png)

某些报告在投放后不能立即可用，具体取决于收集和处理信息所花费的时间。

动态报表分为两个类别:

* **模板**，可通过使用“另存为”选项(“项目” **>“另存为** ..”)复制模板来修&#x200B;**改这些模板。**)。
* **自定义报表** （以蓝色标识），可通过单击“报表”主页上的“创建 **新项目** ”按钮直接 **创建** 。

>[!NOTE]
>
>数据会根据您的组织单位进行筛选。

![](assets/dynamic_report_overview.png)

## 动态报告使用协议 {#dynamic-reporting-usage-agreement}

动态报告使用协议的目的是作为数据处理的弹出同意。 默认情况下，协议仅可见，且只有分配有管理权限的用户才能接受或拒绝。

有三个选项可用：

* **[!UICONTROL Ask me later]**:单击“ **稍后询问**”，窗口将在24小时内停止显示。 在您接受或拒绝协议之前，用户档案维度不会显示在您的报表中，也不会收集或发送客户的个人身份信息。
* **[!UICONTROL Accept]**:接受本协议后，即表示您授权Adobe Campaign收集客户的个人身份信息并将其传输到报告或数据中心。
* **[!UICONTROL Decline]**:拒绝协议后，用户档案维度将不会显示在报表中，也不会收集或发送客户的个人身份信息。 请注意，在这种情况下，仍将收集externalID并用于标识最终用户。

下表显示接受本协议后会发生的情况，具体取决于您所在的地区。

|  | 动态报告 | Microsoft Dynamics 365连接器 |
|---|---|---|
| 美洲和亚太地区（亚太地区） | **功能可用**。 <br>开箱即用（即，城市、国家／地区、州、性别和按年龄划分的细分）和自定义用户档案信息推送到美国报告中心。 有关用户档案维的详细信息，请参阅本 [页](../../reporting/using/list-of-components-.md) | **功能可用**。 <br>所有现成和自定义用户档案字段和Adobe Campaign标准事件字段均在美国数据中心进行处理。 |
| EMEA（欧洲中东和非洲） | **功能可用**。 <br>开箱即用（即，城市、国家／地区、州、性别和按年龄划分的细分）和自定义用户档案信息推送到EMEA报告中心。 有关用户档案维的详细信息，请参阅本 [页](../../reporting/using/list-of-components-.md) | **功能可用。** 在 <br>EMEA数据中心处理的所有现成和自定义用户档案字段和Adobe Campaign标准事件字段。 <br>**[!UICONTROL Control data]** 它包含Adobe I/O注册数据以及在美国数据中心发送和存储的客户最终用户事件的ID。 |

下表根据您所在的地区显示拒绝本协议后会发生什么情况。 请注意，即使您拒绝本协议，投放和Microsoft Dynamics 365集成的报告仍将可用。

| 地区 | 动态报告 | Microsoft Dynamics 365连接器 |
|---|---|---|
| 美洲和亚太地区（亚太地区） | **功能可用**。 <br> 除ExternalID外，没有将现成的和自定义用户档案信息推送到美国报告中心。 | **功能可用**。 <br>除外部ID和用户档案ID外，没有现成的或自定义收件人字段发送到美国数据中心。 <br>除Adobe CampaignID外，美国数据中心中处理的所有事件标准ID字段均不在此列。 <br>有关Microsoft Dynamics 365集成的详细信息，请参阅此 [页](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)。 |
| EMEA（欧洲中东和非洲） | **功能可用**。 <br>除ExternalID外，没有将现成的和自定义用户档案信息推送到EMEA报告中心。 | **功能可用。** 除 <br>外部ID和用户档案ID外，没有现成的或自定义收件人字段发送到EMEA数据中心。 <br>除Adobe CampaignID外，EMEA数据中心中处理的所有事件标准镜像页面字段。  <br>**[!UICONTROL Control data]** 它包含Adobe I/O注册数据以及在美国数据中心发送和存储的客户最终用户事件的ID。<br>有关Microsoft Dynamics 365集成的详细信息，请参阅此 [页](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)。 |

此选项不是最终选项，您始终可以通过选择 **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]****[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** >来更改 **[!UICONTROL Options]**。

可以随时更改该值。 值1对应于 **[!UICONTROL Ask me later]**、2 **[!UICONTROL Decline]** 和3 **[!UICONTROL Accept]**。

![](assets/pii_window_2.png)
