---
title: 集成问题疑难解答
description: 了解如何对共享资源时的问题进行故障诊断。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 5882ada6-dff4-4fd1-a433-0eb31570f73c
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 0%

---

# 故障排除{#troubleshooting}

使用与Audience Manager或People核心服务的集成时可能会遇到错误。

在这种情况下，请确保正确配置了以下元素：

* **外部帐户**

   在 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts]**，请确保正确配置以下外部S3帐户。 在预配期间应配置上述S3服务器。

   * **[!UICONTROL importSharedAudience]**:专门用于导入受众的S3帐户。
   * **[!UICONTROL exportSharedAudience]**:专门用于导出受众的S3帐户。

* **共享数据源**

   在 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**，请检查共享数据源是否设置正确。

   **[!UICONTROL Priority]** 定义了多个数据源时使用。 优先级决定将使用哪个数据源与按定义的顺序接收的别名进行匹配。 **[!UICONTROL Priority]** 仅需用于触发器实施。

   检查协调键值是否正确。 用于导出和导入受众的是此字段的哈希/加密值。

   如果对声明的ID进行哈希处理或加密，请检查您的网站上是否使用了相同的参数/加密算法。

   仅支持一种加密算法：AES在CBC模式下，密钥大小为128、192或256位，带PKCS内边距。

   如果选择了AES加密算法，则必须正确设置以下附加字段：

   * **加密密钥** （对于AES）
   * **加密IV** （初始化矢量）
   * **渠道** （电子邮件/短信/其他）：利用此字段，可直接解密电子邮件地址和短信号码。 确保协调键值与 **渠道** 字段。 如果选择“其他”，则不会发生此特定解密，并且将使用协调密钥协调数据。

   Experience Cloud受众可能由于技术工作流已停止或暂停而无法共享。 访问 **[!UICONTROL Import shared audience]** 工作流，直接单击 **[!UICONTROL Show ImportShared Audience workflow]** 选项。

在通过“人员”核心服务共享受众或导入受众时，可能会发生缺少某些数据的情况。 只有能够与用户档案维度协调ID（“访客ID”或“声明的ID”）的记录才会被传输。 不会导入未被Adobe Campaign识别的“人员”核心服务区段中的ID。
