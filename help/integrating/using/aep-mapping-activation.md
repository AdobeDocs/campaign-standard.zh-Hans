---
title: 映射激活
description: 了解如何激活数据映射
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: d7ca0de6-7f7b-4e31-877c-909d962c5f53
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%

---

# 映射激活 {#mapping-activation}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector目前处于测试阶段，可能会频繁更新，恕不另行通知。 需要在Azure上托管客户（目前仅适用于北美地区的测试版）才能访问这些功能。 如果您希望访问，请联系Adobe客户关怀团队。

完成映射定义后，您可以发布映射。 在部署步骤后，将自动启动Campaign Standard与Adobe Experience Platform之间的数据复制。 您可以随时通过单击 **[!UICONTROL Stop]** 按钮。

根据您的映射修改，您可以选择将所有记录重新发送到Adobe Experience Platform。

![](assets/aep_publishmapping.png)

从部署拼贴中，您可以访问发布日志并导出日志。

![](assets/aep_publog.png)

在 **[!UICONTROL Export jobs]** 选项卡，则可以监视已发布映射的导出作业。

![](assets/aep_jobstatus.png)

如果要监视所有数据导出作业，请转到 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]** 菜单。

![](assets/aep_statusmapping.png)

数据摄取作业状态包括：

* **[!UICONTROL Created]**:将创建数据摄取作业，并且正在进行数据摄取。
* **[!UICONTROL Failed]**:数据摄取作业失败。 原因字段描述失败的原因。 故障可以是暂时的或永久的。 如果出现临时故障，则会在配置的间隔后创建新的摄取作业。 作为故障排除的第一步，用户可以检查失败的原因字段。 如果原因将用户重定向到Adobe Experience Platform UI，则用户可以登录Adobe Experience Platform，并可以检查数据集中的批处理状态以确定确切失败原因。
* **[!UICONTROL Uploaded]**:首先在Adobe Experience Platform中创建批处理，然后将数据摄取到该批处理。 “批次ID”字段显示Adobe Experience Platform中批的批次ID。 Adobe Experience Platform还会对批执行后验证。 在Adobe Experience Platform完成帖子验证步骤之前，该批次首先标记为已上传。 上传后，作业会持续轮询Adobe Experience Platform的批处理状态。 在Adobe Experience Platform中，批处理可以处于失败状态或处于成功状态后验证。
* **[!UICONTROL Success]**:将批量上传到Adobe Experience Platform后，会在配置的间隔后检查作业的状态（平台中的后验证）。 状态“成功”可识别是否在Adobe Experience Platform中成功摄取数据。

在某些情况下，您可能会在发布映射时收到下面的验证错误。

![](assets/aep_datamapping_ccpa.png)

当您使用的XDM架构未更新与隐私管理相关的最新XDM字段，并且仍包含已弃用的“ccpa”XDM字段时，会发生这种情况。

要更新XDM架构，请执行以下步骤：

1. 使用XDM映射页面上存在的链接，转到Adobe Experience Platform上的数据集。

1. 导航到XDM架构。

1. 添加 **[!UICONTROL Profile Privacy]** 混合到架构中。

   ![](assets/aep_datamapping_privacyfield.png)

1. 保存架构，然后重试发布映射。 此时应会通过发布。

   ![](assets/aep_save_mapping.png)
