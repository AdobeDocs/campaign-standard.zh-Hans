---
title: 疑难解答
seo-title: 疑难解答
description: 疑难解答
seo-description: 了解如何在共享资源时解决问题。
page-status-flag: 从未激活
uuid: 1c764dd8-e09 f-4e8 e-9cr-3d3 d714284
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 集成
content-type: reference
topic-tags: publishing-with-campaign-and-operators-manager-or-ople-core-service
discoiquuid: c28e1d90-8074-4127-a6 fc-ed39 d69 cdb19
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Troubleshooting{#troubleshooting}

在使用Audience Manager或People核心服务时可能会遇到错误。

在这种情况下，请确保正确配置以下元素：

* **外部帐户**

   In **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL External accounts]**, make sure that the following external S3 accounts are correctly configured. 指定的S服务器应在供应过程中配置。

   * **[!UICONTROL importSharedAudience]**：专用于导入受众的S帐户。
   * **[!UICONTROL exportSharedAudience]**：专用于导出受众的S帐户。

* **共享数据源**

   In **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Shared Data Sources]**, check that the shared data source is set properly.

   **[!UICONTROL Priority]** 在定义多个数据源时使用。优先级决定将使用哪个数据源匹配按定义顺序接收的别名。**[!UICONTROL Priority]** 仅适用于触发器实现。

   检查对帐密钥是否正确。它是用于导出和导入受众的此字段的散列/加密值。

   如果对声明的ID进行散列处理或加密，请检查您的网站是否使用相同的参数/加密算法。

   仅支持一种加密算法：具有128、192或256位的AES模式，PKCS边距。

   如果选择AES加密算法，则必须正确设置以下字段：

   * **AES的加密密钥**
   * **AES的加密IV** (初始化矢量)
   * **渠道** (电子邮件/短信/其他)：此字段允许直接解密电子邮件地址和SMS号码。Make sure that the reconciliation key matches the setting of the **Channel** field. 如果您选择“其他”，则不会发生此特定解密，并且将使用对帐密钥来调解数据。
   由于技术工作流程已停止或暂停，因此无法共享Experience Cloud受众。Access the **[!UICONTROL Import shared audience]** workflow by clicking directly the **[!UICONTROL Show ImportShared Audience workflow]** option in your Data source.

当通过People核心服务或导入受众时共享受众时，可能会缺少一些数据。只传输ID('访问者ID'或“声明ID”)能够与配置文件维度协调一致的记录。不会导入来自Adobe Campaign未识别的人员核心服务区段的ID。
