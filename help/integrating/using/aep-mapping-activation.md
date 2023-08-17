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
>Adobe Experience Platform Data Connector目前处于测试阶段，可能会频繁更新，恕不另行通知。 客户需要在Azure上托管（目前为仅北美测试版）才能访问这些功能。 如果您希望获得访问权限，请联系Adobe客户关怀团队。

完成映射定义后，可以发布映射。 在部署步骤后，Campaign Standard和Adobe Experience Platform之间的数据复制会自动启动。 您可以随时通过单击 **[!UICONTROL Stop]** 按钮。

根据映射修改，您可以选择将所有记录重新发送到Adobe Experience Platform。

![](assets/aep_publishmapping.png)

从部署图块中，您可以访问发布日志和导出日志。

![](assets/aep_publog.png)

在 **[!UICONTROL Export jobs]** 选项卡，可以监视已发布映射的导出作业。

![](assets/aep_jobstatus.png)

如果要监视所有数据导出作业，请转到 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]** 菜单。

![](assets/aep_statusmapping.png)

数据摄取作业状态为：

* **[!UICONTROL Created]**：创建了数据摄取作业，并且正在进行数据摄取。
* **[!UICONTROL Failed]**：数据摄取作业失败。 原因字段描述了失败的原因。 故障可能是暂时的，也可能是永久性的。 如果发生暂时性故障，则会在配置的间隔后创建新的引入作业。 作为疑难解答的第一步，用户可以查看失败的原因字段。 如果原因导致用户重定向到Adobe Experience Platform UI，则用户可以登录到Adobe Experience Platform，并检查数据集中的批次状态以确定确切的失败原因。
* **[!UICONTROL Uploaded]**：首先在Adobe Experience Platform中创建批次，然后将数据摄取到批次中。 “批次ID”字段显示Adobe Experience Platform中批次的批次ID。 Adobe Experience Platform还会对批次执行过帐验证。 该批次首先标记为已上传，直到Adobe Experience Platform完成发布验证步骤。 作业在上传后不断轮询Adobe Experience Platform以查找批次的状态。 在Adobe Experience Platform中，批次可以处于失败或成功状态发布验证。
* **[!UICONTROL Success]**：将批次上传到Adobe Experience Platform后，在配置的间隔后检查作业状态（在Platform中发布验证）。 “成功”状态表示已成功摄取Adobe Experience Platform中的数据。

在某些情况下，发布映射时可能会出现以下验证错误。

![](assets/aep_datamapping_ccpa.png)

当您使用的XDM架构未更新为与隐私管理相关的最新XDM字段，并且仍包含已弃用的“ccpa”XDM字段时，会发生这种情况。

要更新XDM架构，请执行以下步骤：

1. 使用XDM映射页面上存在的链接转到Adobe Experience Platform上的数据集。

1. 导航到您的XDM架构。

1. 添加 **[!UICONTROL Profile Privacy]** mixin到架构。

   ![](assets/aep_datamapping_privacyfield.png)

1. 保存架构，然后重试发布映射。 发布现在应该会通过。

   ![](assets/aep_save_mapping.png)
