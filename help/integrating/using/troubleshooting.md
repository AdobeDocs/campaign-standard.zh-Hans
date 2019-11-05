---
title: 故障排除
description: 了解如何解决共享资源时的问题。
page-status-flag: 从未激活
uuid: 1c764dd8-e09f-4e8e-9ccd-88ab3d714284
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 集成
content-type: 参考
topic-tags: 使用Campaign和Audience manager或People核心服务
discoiquuid: c28e1d90-8074-4127-a6fc-ed39d69cdb19
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 故障排除{#troubleshooting}

使用与Audience manager或People核心服务的集成时可能会遇到错误。

在这种情况下，请确保正确配置了以下元素：

* **外部帐户**

   在 **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL External accounts]**&#x200B;中，确保正确配置了以下外部S3帐户。 在配置过程中，应已配置上述S3服务器。

   * **[!UICONTROL importSharedAudience]**:专用于导入受众的S3帐户。
   * **[!UICONTROL exportSharedAudience]**:专用于导出受众的S3帐户。

* **共享数据源**

   在 **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Shared Data Sources]**&#x200B;中，检查共享数据源设置是否正确。

   **[!UICONTROL Priority]** 当您定义了多个数据源时使用。 优先级决定将使用哪个数据源与在定义的顺序中接收的别名匹配。 **[!UICONTROL Priority]** 仅用于触发器实施。

   检查对帐密钥是否正确。 用于导出和导入受众的是此字段的哈希／加密值。

   如果对声明的ID进行哈希或加密，请检查您的网站上是否使用了相同的参数／加密算法。

   只支持一种加密算法：AES在CBC模式下，密钥大小为128、192或256位，并带有PKCS填充。

   如果选择了AES加密算法，则必须正确设置以下附加字段：

   * **AES的加密密钥**
   * **AES的Encryption IV** （初始化矢量）
   * **频道** （电子邮件／短信／其他）:此字段允许直接解密电子邮件地址和SMS号码。 确保对帐密钥与“渠道”字段的设置 **匹配** 。 如果选择“其他”，则此特定解密将不发生，且将使用协调密钥来协调数据。
   Experience cloud受众可能无法共享，因为技术工作流已停止或暂停。 直接单 **[!UICONTROL Import shared audience]** 击数据源中的选项，以 **[!UICONTROL Show ImportShared Audience workflow]** 访问该工作流。

在通过“人员”核心服务共享受众或导入受众时，可能会发生一些数据缺失的情况。 只有ID（“访客ID”或“声明ID”）能够与配置文件维度协调的记录才会被传输。 不会导入Adobe Campaign无法识别的People核心服务区段的ID。
