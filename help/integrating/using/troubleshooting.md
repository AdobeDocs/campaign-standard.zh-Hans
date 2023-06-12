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
source-wordcount: '347'
ht-degree: 0%

---

# 故障排除{#troubleshooting}

使用与Audience Manager或人员核心服务集成时，可能会遇到错误。

在这种情况下，请确保正确配置了以下元素：

* **外部帐户**

   In **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts]**，确保正确配置了以下外部S3帐户。 在配置期间应配置上述S3服务器。

   * **[!UICONTROL importSharedAudience]**：专门用于导入受众的S3帐户。
   * **[!UICONTROL exportSharedAudience]**：专门用于导出受众的S3帐户。

* **共享数据源**

   In **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**，检查是否正确设置了共享数据源。

   **[!UICONTROL Priority]** 定义多个数据源时使用。 优先级决定将使用哪个数据源与按定义的顺序接收的别名匹配。 **[!UICONTROL Priority]** 仅适用于Triggers实施。

   检查协调密钥是否正确。 此字段的哈希/加密值用于导出和导入受众。

   如果对声明的ID进行哈希处理或加密，请检查您的网站上是否使用了相同的参数/加密算法。

   仅支持一种加密算法：AES在CBC模式下使用，密钥大小为128、192或256位，带有PKCS填充。

   如果选择AES加密算法，则必须正确设置以下附加字段：

   * **加密密钥** 用于AES
   * **加密IV** AES的（初始化矢量）
   * **渠道** （电子邮件/短信/其他）：此字段允许直接解密电子邮件地址和短信号码。 确保协调键值与 **渠道** 字段。 如果选择“其他”，将不会发生此特定解密，并且协调密钥将用于协调数据。

   由于技术工作流已停止或暂停，可能无法共享Experience Cloud受众。 访问 **[!UICONTROL Import shared audience]** 工作流，只需直接单击 **[!UICONTROL Show ImportShared Audience workflow]** 选项。

在通过“人员”核心服务共享受众或导入受众时，可能会丢失某些数据。 仅转移ID（“访客ID”或“声明的ID”）能够与配置文件维度协调的记录。 Adobe Campaign无法识别的“人员”核心服务区段中的ID不会导入。
