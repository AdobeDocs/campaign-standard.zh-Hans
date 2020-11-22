---
solution: Campaign Standard
product: campaign
title: 映射激活
description: 了解如何激活数据映射
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 1%

---


# 映射激活 {#mapping-activation}

>[!IMPORTANT]
>
>Adobe Experience Platform数据连接器目前处于测试阶段，可能会在不通知的情况下频繁进行更新。 客户必须托管在Azure上（目前仅限北美的beta版），才能访问这些功能。 如果您想要访问，请联系Adobe客户服务中心。

完成映射定义后，您可以发布映射。 部署步骤完成后，Campaign Standard和Adobe Experience Platform之间的数据复制将自动启动。 您可以随时单击该按钮来停止复 **[!UICONTROL Stop]** 制。

根据您的映射修改，您可以选择将所有记录重新发送到Adobe Experience Platform。

![](assets/aep_publishmapping.png)

从部署拼贴中，您可以访问发布日志并导出日志。

![](assets/aep_publog.png)

在选项卡 **[!UICONTROL Export jobs]** 中，您可以监视已发布映射的导出作业。

![](assets/aep_jobstatus.png)

如果要监视所有数据导出作业，请转到 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** >菜 **[!UICONTROL Status of data export to platform]** 单。

![](assets/aep_statusmapping.png)

数据摄取作业状态：

* **[!UICONTROL Created]**:已创建数据获取作业并正在进行数据获取。
* **[!UICONTROL Failed]**:数据获取作业失败。 原因字段描述失败的原因。 故障可以是临时的或永久的。 如果出现临时故障，将在配置的时间间隔后创建新的摄取作业。 作为故障排除的第一步，用户可以检查故障的原因字段。 如果原因将用户重定向到Adobe Experience PlatformUI，则用户可登录Adobe Experience Platform并检查数据集中的批处理状态以确定确切失败原因。
* **[!UICONTROL Uploaded]**:首先在Adobe Experience Platform创建批，然后将数据摄取到该批。 批ID字段显示Adobe Experience Platform的批的批ID。 Adobe Experience Platform还对批执行后期验证。 批首先标记为已上载，直到Adobe Experience Platform完成后期验证步骤。 上传后，作业会持续轮询Adobe Experience Platform以了解批的状态。 在Adobe Experience Platform，批处理可以进入“失败”或“成功”状态后验证。
* **[!UICONTROL Success]**:在将批上传到Adobe Experience Platform后，在配置的时间间隔后检查作业的状态（平台中的后验证）。 “成功”状态在Adobe Experience Platform发现成功获取数据。
