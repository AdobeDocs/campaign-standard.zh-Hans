---
title: 集成问题疑难解答
description: 了解如何在共享资源时排除问题。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 5882ada6-dff4-4fd1-a433-0eb31570f73c
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 0%

---

# 故障排除{#troubleshooting}

将与Audience Manager或人员核心服务集成使用时可能会遇到错误。

在这种情况下，请确保已正确配置以下元素：

* **外部帐户**

  在 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts]**，确保正确配置了以下外部S3帐户。 在配置期间应配置上述S3服务器。

   * **[!UICONTROL importSharedAudience]**：专门用于导入受众的S3帐户。
   * **[!UICONTROL exportSharedAudience]**：专门用于导出受众的S3帐户。

* **共享数据源**

  在 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**，检查是否正确设置了共享数据源。

  **[!UICONTROL Priority]** 定义多个数据源时使用。 优先级决定要使用哪个数据源与按定义的顺序接收的别名匹配。 **[!UICONTROL Priority]** 仅需要用于Triggers实施。

  检查协调键值是否正确。 此字段的哈希/加密值用于导出和导入受众。

  如果对声明的ID进行哈希处理或加密，请检查您的网站上是否使用了相同的参数/加密算法。

  仅支持一种加密算法：CBC模式的AES，密钥大小为128、192或256位，带有PKCS填充。

  如果选择AES加密算法，则必须正确设置以下附加字段：

   * **加密密钥** 用于AES
   * **加密IV** AES的（初始化矢量）
   * **渠道** （电子邮件/短信/其他）：此字段允许直接解密电子邮件地址和短信编号。 确保协调键值与 **渠道** 字段。 如果选择“其他”，将不会发生此特定解密，并且协调密钥将用于协调数据。

  可能未共享Experience Cloud受众，因为技术工作流已停止或暂停。 访问 **[!UICONTROL Import shared audience]** 工作流，方法是直接单击 **[!UICONTROL Show ImportShared Audience workflow]** 选项。

在通过People核心服务共享受众或导入受众时，可能会丢失某些数据。 只传输ID（“访客ID”或“声明的ID”）能够与用户档案维度协调的记录。 Adobe Campaign无法识别的People核心服务区段中的ID不会导入。
