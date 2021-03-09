---
solution: Campaign Standard
product: campaign
title: 映射激活
description: 了解如何激活数据映射
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 35d61efce8d752ea30b7eaad55e6c23d4debd853
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%

---


# 映射激活 {#mapping-activation}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector目前处于测试阶段，可能会在不通知的情况下频繁进行更新。 客户需要托管在Azure上（目前仅针对北美）才能访问这些功能。 如果您希望访问，请联系Adobe客户关怀团队。

完成映射定义后，您可以发布映射。 部署步骤完成后，Campaign Standard和Adobe Experience Platform之间的数据复制将自动启动。 您可以随时单击&#x200B;**[!UICONTROL Stop]**&#x200B;按钮来停止复制。

根据您的映射修改，您可以选择向Adobe Experience Platform重新发送所有记录。

![](assets/aep_publishmapping.png)

从部署拼贴中，您可以访问发布日志并导出日志。

![](assets/aep_publog.png)

在&#x200B;**[!UICONTROL Export jobs]**&#x200B;选项卡中，可以监视已发布映射的导出作业。

![](assets/aep_jobstatus.png)

如果要监视所有数据导出作业，请转到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]**&#x200B;菜单。

![](assets/aep_statusmapping.png)

数据摄取作业状态为：

* **[!UICONTROL Created]**:已创建数据摄取作业，并正在进行数据摄取。
* **[!UICONTROL Failed]**:数据获取作业失败。原因字段描述失败的原因。 故障可以是暂时的或永久的。 如果出现暂时性故障，将在配置的间隔后创建新的摄取作业。 作为故障排除的第一步，用户可以检查故障的原因字段。 如果原因将用户重定向到Adobe Experience Platform UI，则用户可登录Adobe Experience Platform并检查数据集中的批处理状态以确定确切失败原因。
* **[!UICONTROL Uploaded]**:首先在Adobe Experience Platform中创建批，然后将数据引入该批。批ID字段显示Adobe Experience Platform中批的批ID。 Adobe Experience Platform还对批执行后期验证。 该批首先标记为已上载，直到Adobe Experience Platform完成帖子验证步骤。 一个作业在上传后不断轮询Adobe Experience Platform以了解批的状态。 批处理可以在Adobe Experience Platform中以失败或成功状态进行帖子验证。
* **[!UICONTROL Success]**:在将批上传到Adobe Experience Platform后，将在配置的时间间隔后检查作业的状态（平台中的后期验证）。状态“成功”表明在Adobe Experience Platform中成功获取数据。

在某些情况下，发布映射时可能会出现以下验证错误。

![](assets/aep_datamapping_ccpa.png)

当您使用的XDM模式尚未更新为与隐私管理相关的最新XDM字段且仍包含已弃用的“ccpa”XDM字段时，会发生这种情况。

要更新XDM模式，请执行以下步骤：

1. 使用XDM映射页面上的链接转到Adobe Experience Platform上的数据集。

1. 导航到您的XDM模式。

1. 将&#x200B;**[!UICONTROL Profile Privacy]**&#x200B;混音添加到模式。

   ![](assets/aep_datamapping_privacyfield.png)

1. 保存模式，然后重试发布映射。 该出版物现在应通过。

   ![](assets/aep_save_mapping.png)
