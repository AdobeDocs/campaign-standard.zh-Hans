---
title: 动态报告快速入门
description: 使用动态报告，将变量和维度拖放到自由格式环境中，并分析营销活动成功与否。
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Beginner
exl-id: fc3b28f3-63f6-4edc-923d-c7eb7925d1b7
TQID: https://experienceleague.adobe.com/L392oFEzYUkSajzO3Gi7gjWLmDrpbOhW24k1OXFmoRc
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
  - id: c309ee4e-82e4-4f7e-b608-ef345678c34e
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
subfeature_v2:
  - id: ca3c1dd6-bdd2-41a9-bc5a-e35f5cca9e63
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 831
ht-degree: 10%

---

# 动态报告快速入门 {#about-dynamic-reports}

动态报告提供完全可自定义的实时报告。 它增加了对轮廓数据的访问，除打开数和点击数等功能性电子邮件营销活动数据外，还支持按轮廓维度（如性别、城市和年龄）进行人口统计分析。 通过拖放界面，您可以浏览数据，确定电子邮件活动针对最重要的客户细分执行情况，并衡量其对收件人的影响。

>[!NOTE]
>
>只有具有管理权限或组织单位设置为&#x200B;**全部**&#x200B;的用户才能创建或保存新报告。 有关更多信息，请参阅此[&#128279;](../../administration/using/users-management.md)章节。

## 访问动态报告 {#accessing-dynamic-reports}

报告可以访问：

* 从主页中，选择顶部栏中的&#x200B;**[!UICONTROL Reports]**&#x200B;选项卡或&#x200B;**[!UICONTROL Reports]**&#x200B;卡以访问所有投放的报告。

  ![](assets/campaign_reports_access.png)

* 在每个项目、营销策划和消息中，通过单击&#x200B;**动态报告**，从&#x200B;**报告**&#x200B;按钮中查看特定于投放的报告。

  ![](assets/campaign_reports_description.png)

某些报表在投放后无法立即可用，具体取决于收集和处理信息所花费的时间。

动态报告分为两类：

* **模板**，可通过使用&#x200B;**另存为**&#x200B;选项（**项目>另存为……**）复制这些模板来对其进行修改 在模板中。
* **自定义报告** （以蓝色标识），可通过单击&#x200B;**报告**&#x200B;主页上的&#x200B;**新建项目**&#x200B;按钮直接创建。

>[!NOTE]
>
>数据会根据您的组织单位进行过滤。

![](assets/dynamic_report_overview.png)

## 动态报告使用协议 {#dynamic-reporting-usage-agreement}

动态报告使用协议的目的是作为数据处理的弹出窗口同意。 默认情况下，协议仅可见，并且只有分配了管理权限的用户才能接受或拒绝协议。

提供了三个选项：

* **[!UICONTROL Ask me later]**：单击&#x200B;**稍后再询问**&#x200B;后，该窗口将停止显示24小时。 在您接受或拒绝协议之前，用户档案维度将不会显示在您的报表中，并且不会收集或发送客户的个人身份信息。
* **[!UICONTROL Accept]**：接受此协议，即表示您授权Adobe Campaign收集客户的个人身份信息并将其传输到报表或数据中心。
* **[!UICONTROL Decline]**：如果拒绝协议，配置文件维度将不会显示在您的报表中，也不会收集或发送客户的个人身份信息。 请注意，在这种情况下，仍会收集externalID并将其用于识别最终用户。

下表显示接受此协议后发生的情况，具体取决于您所在的区域。

|  | 动态报告 | Microsoft Dynamics 365连接器 |
|---|---|---|
| 美洲和APAC （亚太） | **功能可用**。 <br>所有现成（即城市、国家/地区、州/省、性别和年龄段）和自定义用户档案信息均推送到美国报告中心。 有关配置文件维度的详细信息，请参阅此[页面](../../reporting/using/list-of-components.md) | **功能可用**。 <br>所有现成的用户档案和自定义用户档案字段以及Adobe Campaign Standard事件字段都在美国数据中心进行处理。 |
| EMEA（欧洲、中东和非洲） | **功能可用**。 <br>所有现成（即城市、国家/地区、州、性别和年龄段）和推送到EMEA报告中心的自定义配置文件信息。 有关配置文件维度的详细信息，请参阅此[页面](../../reporting/using/list-of-components.md) | **功能可用。** 在EMEA数据中心中处理了<br>所有现成的用户档案和自定义用户档案字段以及Adobe Campaign Standard事件字段。 <br>**[!UICONTROL Control data]**，其中包含在美国数据中心发送并存储的Adobe I/O注册数据和客户最终用户事件的ID。 |

下表根据您所在的地区显示拒绝此协议后发生的情况。 请注意，即使您拒绝此协议，仍可以使用有关投放和Microsoft Dynamics 365集成的报告。

| 区域 | 动态报告 | Microsoft Dynamics 365连接器 |
|---|---|---|
| 美洲和APAC （亚太） | **功能可用**。<br> 除ExternalID外，没有现成的用户档案和自定义用户档案信息推送至美国报表中心。 | **功能可用**。 <br>除外部ID和收件人ID外，没有现成或自定义的配置文件字段发送到美国数据中心。 <br>所有在美国数据中心处理的Adobe Campaign Standard事件字段，但镜像页面ID除外。 <br>有关Microsoft Dynamics 365集成的更多信息，请参阅此[页面](../../integrating/using/d365-acs-get-started.md)。 |
| EMEA（欧洲、中东和非洲） | **功能可用**。 <br>除ExternalID外，没有现成的用户档案和自定义用户档案信息推送到EMEA报告中心。 | **功能可用。** <br>除外部ID和收件人ID外，没有现成或自定义的配置文件字段发送到EMEA数据中心。 <br>在EMEA数据中心中处理的所有Adobe Campaign Standard事件字段，但镜像页面ID除外。<br>**[!UICONTROL Control data]**&#x200B;包含Adobe I/O注册数据和在美国数据中心发送和存储的客户最终用户事件的ID。<br>有关Microsoft Dynamics 365集成的更多信息，请参阅此[页面](../../integrating/using/d365-acs-get-started.md)。 |

此选择不是最终选择，您始终可以通过在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**&#x200B;中选择&#x200B;**[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]**&#x200B;来更改它。

此值可随时更改。 值1对应于&#x200B;**[!UICONTROL Ask me later]**、2 **[!UICONTROL Decline]**&#x200B;和3 **[!UICONTROL Accept]**。

![](assets/pii_window_2.png)
