---
title: 故障排除
description: 了解如何解决共享资源时的问题。
page-status-flag: never-activated
uuid: 1c764dd8-e09f-4e8e-9ccd-88ab3d714284
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: c28e1d90-8074-4127-a6fc-ed39d69cdb19
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 1%

---


# 故障排除{#troubleshooting}

使用与Audience Manager或人员核心服务的集成时可能会遇到错误。

在这种情况下，请确保正确配置了以下元素：

* **外部帐户**

   在 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts]**&#x200B;中，确保正确配置了以下外部S3帐户。 在配置过程中应已配置上述S3服务器。

   * **[!UICONTROL importSharedAudience]**:专用于导入受众的S3帐户。
   * **[!UICONTROL exportSharedAudience]**:专用于导出受众的S3帐户。

* **共享数据源**

   在 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**&#x200B;中，检查共享数据源设置是否正确。

   **[!UICONTROL Priority]** 当您定义了多个数据源时使用。 优先级决定将哪个数据源用于匹配在定义的顺序中接收的别名。 **[!UICONTROL Priority]** 仅用于触发器实施。

   检查合并关键项是否正确。 用于导出和导入受众的是此字段的哈希／加密值。

   如果对声明的ID进行散列或加密，请检查您的网站上是否使用了相同的参数／加密算法。

   仅支持一种加密算法：密钥大小为128、192或256位的CBC模式下的AES，使用PKCS填充。

   如果选择AES加密算法，则必须正确设置以下附加字段：

   * **AES的加密密钥** （英文）
   * **AES的Encryption** IV（初始化矢量）
   * **渠道** （电子邮件／短信／其他）:此字段允许直接解密电子邮件地址和SMS号码。 确保合并关键项与渠道字段的设置 **匹配** 。 如果您选择“其他”，则此特定解密不会发生，并且合并关键项将用于协调数据。

   Experience Cloud受众可能未共享，因为技术工作流已停止或暂停。 直接单击 **[!UICONTROL Import shared audience]** 数据源中的选项， **[!UICONTROL Show ImportShared Audience workflow]** 以访问工作流。

在通过People核心服务共享受众或导入受众时，可能会丢失某些数据。 只能传输ID(“访客ID”或“声明ID”)与用户档案维协调的记录。 不会导入Adobe Campaign无法识别的People核心服务区段的ID。
