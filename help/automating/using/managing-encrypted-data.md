---
title: 管理加密数据
description: 了解如何管理加密数据。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows, Encryption
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 1df1552a-6578-47eb-ba14-fb91cd2a3999
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 3%

---

# 管理加密数据 {#managing-encrypted-data}

## 关于预处理阶段 {#about-preprocessing-stages}

在某些情况下，需要加密要导入Campaign服务器的数据，例如包含PII数据的数据。

若要能够加密传出数据或解密传入数据，您需要使用[控制面板](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html?lang=zh-Hans)管理GPG密钥。

>[!NOTE]
>
>控制面板适用于在AWS上托管的所有客户（本地托管营销实例的客户除外）。

如果您不符合使用控制面板的资格，则需要联系Adobe客户关怀团队，以便他们为您的实例提供所需的加密/解密命令。 为此，请提交请求，说明：

* 将在Campaign界面中显示的&#x200B;**标签**，用于使用该命令。 例如“加密文件”。
* 要在实例上安装的&#x200B;**命令**。

处理请求后，加密/解密命令将在&#x200B;**[!UICONTROL Pre-processing stage]**&#x200B;和&#x200B;**[!UICONTROL Load file]**&#x200B;活动的&#x200B;**[!UICONTROL Extract file]**&#x200B;字段中可用。 您可以使用它们来解密或加密要导入或导出的文件。

![](assets/preprocessing-encryption.png)

**相关主题：**

* [加载文件](../../automating/using/load-file.md)
* [提取文件](../../automating/using/extract-file.md)

## 用例：导入使用控制面板生成的密钥加密的数据 {#use-case-gpg-decrypt}

在此使用案例中，构建一个工作流，以使用在控制面板中生成的密钥导入已在外部系统中加密的数据。

![](assets/do-not-localize/how-to-video.png) [通过观看视频了解此功能](#video)

执行此用例的步骤如下：

1. 使用控制面板生成密钥对（公共/私有）。 [控制面板文档](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html#decrypting-data)中提供了详细步骤。

   * 公共密钥将与外部系统共享，外部系统将使用它来加密要发送到Campaign的数据。
   * Campaign将使用私钥对传入的加密数据进行解密。

   ![](assets/gpg_generate.png)

1. 在外部系统中，使用从控制面板下载的公共密钥加密要导入到Campaign Standard中的数据。

1. 在Campaign Standard中，构建一个工作流以导入加密数据，并使用已通过控制面板安装的私钥对其进行解密。 要实现此目的，请构建一个工作流，如下所示：

   ![](assets/gpg_workflow.png)

   * **[!UICONTROL Transfer file]**&#x200B;活动：将文件从外部源传输到Campaign。 在本例中，我们要从SFTP服务器传输文件。
   * **[!UICONTROL Load file]**&#x200B;活动：将数据从文件加载到数据库中，并使用控制面板中生成的私钥将其解密。

1. 打开&#x200B;**[!UICONTROL Transfer file]**&#x200B;活动，然后根据需要进行配置。 有关如何配置活动的全局概念，请参见[此部分](../../automating/using/load-file.md)。

   在&#x200B;**[!UICONTROL Protocol]**&#x200B;选项卡中，指定有关要传输的sftp服务器和加密.gpg文件的详细信息。

   ![](assets/gpg_transfer.png)

1. 打开&#x200B;**[!UICONTROL Load file]**&#x200B;活动，然后根据需要进行配置。 有关如何配置活动的全局概念，请参见[此部分](../../automating/using/load-file.md)。

   为活动添加预处理阶段，以便解密传入数据。 为此，请从列表中选择&#x200B;**[!UICONTROL Decryption GPG]**&#x200B;选项。

   >[!NOTE]
   >
   >请注意，您无需指定用于解密数据的私钥。 私钥存储在控制面板中，它将自动检测用于解密文件的密钥。

   ![](assets/gpg_load.png)

1. 单击&#x200B;**[!UICONTROL OK]**&#x200B;以确认活动配置。

1. 您现在可以运行工作流。

## 用例：使用安装在控制面板上的密钥加密和导出数据 {#use-case-gpg-encrypt}

在此使用案例中，构建一个工作流，以便使用安装在控制面板上的密钥加密和导出数据。

![](assets/do-not-localize/how-to-video.png) [通过观看视频了解此功能](#video)

执行此用例的步骤如下：

1. 使用GPG实用程序生成GPG密钥对（公共/私有），然后将公共密钥安装到控制面板上。 [控制面板文档](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html#encrypting-data)中提供了详细步骤。

   ![](assets/gpg_install.png)

1. 在Campaign Standard中，构建一个工作流以导出数据，并使用已通过控制面板安装的私钥对其进行加密。 要实现此目的，请构建一个工作流，如下所示：

   ![](assets/gpg-workflow-export.png)

   * **[!UICONTROL Query]**&#x200B;活动：在本例中，我们要执行查询以定向要导出的数据库中的数据。
   * **[!UICONTROL Extract file]**&#x200B;活动：加密数据并将其提取到文件中。
   * **[!UICONTROL Transfer file]**&#x200B;活动：将包含加密数据的文件传输到SFTP服务器。

1. 配置&#x200B;**[!UICONTROL Query]**&#x200B;活动以定位数据库中的所需数据。 如需详细信息，请参阅[此小节](../../automating/using/query.md)。

1. 打开&#x200B;**[!UICONTROL Extract file]**&#x200B;活动，然后根据需要对其进行配置（输出文件、列、格式等）。 有关如何配置活动的全局概念，请参见[此部分](../../automating/using/extract-file.md)。

   向活动添加一个预处理阶段，以便加密要提取的数据。 为此，请选择用于加密数据的加密GPG密钥。

   ![](assets/gpg-extract-stage.png)

   >[!NOTE]
   >
   >括号中的值是您在使用GPG加密工具生成密钥对时定义的&#x200B;**注释**。 请确保选择正确的匹配密钥，否则收件人将无法解密文件。

1. 打开&#x200B;**[!UICONTROL Transfer file]**&#x200B;活动，然后指定要将文件发送到的SFTP服务器。 有关如何配置活动的全局概念，请参见[此部分](../../automating/using/transfer-file.md)。

   ![](assets/gpg-transfer-encrypt.png)

1. 您现在可以运行工作流。 执行查询后，查询的数据目标将导出到SFTP服务器中，并转换为加密的.gpg文件。

## 教程视频 {#video}

本视频说明如何使用GPG密钥解密数据。

>[!VIDEO](https://video.tv.adobe.com/v/35753?quality=12)

本视频说明如何使用GPG密钥加密数据。

>[!VIDEO](https://video.tv.adobe.com/v/36380?quality=12)

[此处](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hans)提供了其他Campaign Standard操作方法视频。
