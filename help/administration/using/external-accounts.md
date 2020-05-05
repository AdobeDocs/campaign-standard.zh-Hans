---
title: 外部帐户
description: 配置外部帐户以设置与外部系统（如SFTP服务器）的连接。
page-status-flag: never-activated
uuid: 5d2e2e3d-5d1f-4466-97e5-842c50390146
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: d5c6a3d4-f767-46c1-a8c0-3b9dc52dcea8
internal: n
snippet: y
context-tags: extAccount,main;extAccount,overview
translation-type: tm+mt
source-git-commit: a73cbdd1af2ce134e10222ab07709639ba419ebe

---


# 外部帐户{#external-accounts}

外部帐户是一种配置，允许您配置和测试对Adobe Campaign外部服务器的访问。

这些外部帐户可用于活动工作流访问和管理数据。

您可以设置以下类型的外部帐户:

* SFTP。 如需详细信息，请参阅[此部分](#sftp-external-account)。
* Amazon存储服务(S3)。 如需详细信息，请参阅[此部分](#amazon-s3-external-account)。
* Adobe Experience Manager。 如需详细信息，请参阅[此部分](#adobe-experience-manager-external-account)。
* Adobe Analytics。 如需详细信息，请参阅[此部分](../../integrating/using/configure-campaign-analytics-integration.md)。
* Google reCAPTCHA。 如需详细信息，请参阅[此部分](#google-recaptcha-external-account)。
* Microsoft Azure Blob存储。 如需详细信息，请参阅[此部分](#microsoft-azure-external-account)。

>[!NOTE]
>
>Adobe在产品配置过程中使用其他类型的外部帐户。 从Campaign Standard17.9版本开始，FTP外部帐户仍可以定义，但在新的工作流活动中不再可用。 如果已设置连接，则仍启用该连接。

外部帐户可由管理员在菜单下进行 **[!UICONTROL Administration > Application settings > External accounts]** 配置。

## 创建外部帐户 {#creating-an-external-account}

Adobe Campaign附带一组预定义外部帐户。 要与外部系统（如用于文件传输的FTP服务器）建立连接，您可以创建自己的外部帐户。

外部帐户由技术工作流或活动工作流等技术流程使用。 在工作流中设置文件传输或与任何其他应用程序(Adobe目标、Experience Manager等)进行数据交换时，您需要选择外部帐户。

1. Click the **[!UICONTROL Create]** button.
1. 输入标签。 在工作流中选择外部帐户时，将使用标签和ID。
1. 选择要创建的帐户类型。
1. 根据需要指定凭据、服务器地址、端口号或密钥，以配置对帐户的访问。

   必需信息通常由您所连接的服务器的提供者提供。

1. 保存您的帐户。

将创建外部帐户并将其添加到帐户列表。 它现在可用于工作流活动和路由属性中的数据／文件传输或投放配置。

## SFTP外部帐户 {#sftp-external-account}

不同的外部帐户类型需要指定不同的信息。

对于SFTP外部帐户，请提供以下详细信息：

* 服务器地址。 例如， **ftp.domain.com**。
* 端口号。 For example, **22**.
* SFTP服务器凭据： 用于连接到服务器的帐户名称和密码。

### Adobe托管的SFTP服务器建议 {#adobe-hosted-sftp-server-recommendations}

管理用于 ETL 的文件和数据时，这些文件存储在 Adobe 提供的托管 SFTP 服务器上。此 SFTP 旨在作为临时存储空间，您可以在其上控制文件的保留和删除。

如果未正确使用或监视，该空间会快速填满服务器上可用的物理空间，并导致严重问题。 它可能导致您的平台上的数据丢失或损坏。

为避免出现此类问题，Adobe建议遵循以下最佳实践：

* 保持尽可能少的数据。
* 使用基于密钥的身份验证来避免口令过期。 支持的格 **式仅****限OpenSSH和** SSH2。 您必须向Adobe支持团队提供公钥，才能将其上传到活动服务器。
* 只按需保留数据。 15天是最大时限。
* 按照工作流程正确删除数据（通过消费数据的工作流程来管理保留）。
* 在 SFTP 上传和工作流程中使用批处理。
* 处理错误/例外状况。
* 时常登入 SFTP 以直接检查其内容。
* 请记住，SFTP 硬盘的管理主要由您负责。

另外，请注意，您尝试从中启动SFTP连接的公共IP必须在活动实例中列入白名单。 IP地址的白名单可以通过支 [持票](https://support.neolane.net)请求，同时提供用于身份验证的公共密钥。

SFTP服务器可从控制面板进行管理。 有关详细信息，请参阅控 [制面板文档](https://docs.adobe.com/content/help/en/control-panel/using/sftp-management/about-sftp-management.html)。

>[!NOTE]
>
>控制面板仅适用于在AWS上托管的客户的管理员用户。
在此处检查您的实例是否托管 [在AWS](https://docs.adobe.com/content/help/en/control-panel/using/faq.html#ims-org-id)。

## Amazon S3外部帐户 {#amazon-s3-external-account}

Amazon S3服务器字段应填写如下：

```
<S3 bucket name>.s3.amazonaws.com/<s3 object path>
```

要以S3加密模式存储文件，请选中此 **[!UICONTROL Keep files in S3 encrypted]** 框。

![](assets/external_accounts_2.png)

必需信息通常由您所连接的服务器的提供者提供。

指定与 **[!UICONTROL AWS Region]** 您的端点关联的。 您可以在官方的Amazon S3文档中检查受支持 [的地区和签名版本](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region)。

>[!NOTE]
>
>您 **[!UICONTROL Receiver server]** 应在没有您的AWS区域的情况下输入，稍后会自动将其添加到您的URL。

### Amazon S3帐户建议 {#amazon-s3-account-recommendations}

为了帮助您设置Amazon S3帐户，我们建议您遵循以下建议：

* 创建严格存储段策略以限制对S3存储段的访问。 在创建存储段时可以配置存储段策略。 有关详细信息，请参 [阅Amazon S3文档](https://docs.aws.amazon.com/AmazonS3/latest/dev//example-bucket-policies.html)。
* 在创建外部帐户时，通过选中该框，启用加密以在S3存储桶中存储敏感 **[!UICONTROL Keep files in S3 encrypted]** 数据。
* 授予存储段权限，以指定谁可以访问存储段中的对象。 有关存储桶权限的详细信息，请参 [阅Amazon S3文档](https://docs.aws.amazon.com/AmazonS3/latest/dev//access-control-overview.html)。

## Adobe Experience Manager外部帐户 {#adobe-experience-manager-external-account}

将外部帐户与Experience Manager集成时，会使用Adobe Experience Manager活动。

此文档提供与此集成相关的流程 [和要求](../../integrating/using/get-started-campaign-integrations.md)。

在设置此新外部帐户时，您需要提供以下详细信息：

* 服务器： 输入Adobe Experience Manager服务器的URL。 例如， **http://aem.domain.com:4502**。
* AEM帐户凭据： 使用将访问Adobe Experience Manager实例的帐户。 它应是Experience Manager中活动远程组的帐户部分。

## Google reCAPTCHA外部帐户 {#google-recaptcha-external-account}

>[!NOTE]
>
>Google reCAPTCHA配置需要Google帐户。

Google reCAPTCHA机制允许您保护登陆页免受由机器人程序造成的垃圾邮件和滥用。 这对您的客户来说是非侵入式的，因为它不需要客户进行任何交互，并且基于与您网站的交互。 要注册您的站点，请参阅本 [页](https://www.google.com/recaptcha/admin/create)。 您需要选择V3 reCAPTCHA类型。

要将Google reCAPTCHA V3添加到您的登陆页，您首先需要在外部帐户中配置它。 有关如何将其添加到登陆页的更多信息，请参阅此 [部分](../../channels/using/configuring-landing-page.md#setting-google-recaptcha)。

对于Google reCAPTCHA V3外部帐户，请提供以下详细信息：

* **[!UICONTROL Label]** 和 **[!UICONTROL ID]** 您的外部帐户
* **[!UICONTROL Type]**: Google reCAPTCHA
* 您的 **[!UICONTROL Site key]** 和 **[!UICONTROL Site secret]**
* A **[!UICONTROL Threshold]** 0到1

   0.0值表 **[!UICONTROL Threshold]** 示它可能是一个机器人，1.0可能是一个良好的交互。 默认情况下，可以使用阈值0.5。

![](assets/external_accounts_3.png)

## Microsoft Azure Blob存储外部帐户 {#microsoft-azure-external-account}

>[!NOTE]
>
>在Adobe Campaign标准中配置外部帐户所需的信息，可在Azure门户中通过选择> **[!UICONTROL Settings]** 找到 **[!UICONTROL Access keys]**。

Azure Blob存储连接器可用于使用传输文件工作流活动将数据导入或 **[!UICONTROLT导出到Adobe Campaign]** 。 For more on this, refer to this [section](../../automating/using/transfer-file.md#azure-blob-configuration-wf).

对于Microsoft Azure Blob存储外部帐户，请提供以下详细信息：

* **[!UICONTROL Label]** 和 **[!UICONTROL ID]** 您的外部帐户
* **[!UICONTROL Type]**: Microsoft Azure Blob存储
* 您的 **[!UICONTROL Account name]** 和 **[!UICONTROL Account key]**。 要了解在何处查找您的帐户名称和密钥，请参阅本 [页](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage)。
* 您的 **[!UICONTROL Endpoint suffix]**。 可以在Azure门户的 **[!UICONTROL Connection string]** 菜单 **[!UICONTROL Access keys]** 中找到它。 For more on this, refer to this [page](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage).
* 你的 **[!UICONTROL Container]** 名字。 如果您计划使用多个容器，则需要创建与容器相同的外部帐户。
* 通过 **[!UICONTROL Concurrency]** 此选项可微调文件传输的速度。

![](assets/external_accounts_4.png)

配置完毕后，单 **[!UICONTROL Test connection]** 击将Adobe Campaign链接到Microsoft Azure Blob存储。

### Microsoft Azure Blob存储建议 {#azure-blob-recommendations}

**加密**

Adobe Campaign使用安全连接(HTTPS)访问您的Microsoft Azure Blob存储帐户。

**帐户密钥**

配置外部帐户时，必须使用Azure门户 **[!UICONTROL Account key]** 中的一个可用。 有关在何处查找帐户密钥的详细信息，请参阅本 [页](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage#view-access-keys-and-connection-string)。

**优化文件传输速度**

通过 **[!UICONTROL Concurrency]** 此选项可微调文件传输的速度。
它表示用于执行文件传输的线程数。 每个线程都将从blob下载约1MB的一部分。 然后，它们将排队以写入磁盘。 请注意，通过增加线程数，您还将增加应用程序在文件传输过程中使用的资源的负载。

在文件传输完成后，您可以在工作流日志中找到性能指标。

**重试**

默认情况下，Azure Blob的文件传输最多有四个重试。  如果Azure存储服务返回错误代码，如503（服务器忙）或500（操作超时），这可能表示您正在接近或超过存储帐户的可伸缩性。 在使用新帐户或执行测试时可能发生这种情况。

如果错误仍然存在，您可以通过在高级菜单> >下创建一个选项来增加重试 **[!UICONTROL Administration]** 的 **[!UICONTROL Application Settings]** 数量 **[!UICONTROL Options]**。

如果实现，则必须按如下方式创建选项：

```
ID:        AzureBlob_Max_Retries
Date type: Integer
Default:   <the number of retries needed>
```
