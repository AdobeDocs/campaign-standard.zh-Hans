---
title: 外部帐户
description: 了解如何配置外部帐户以设置与外部系统（如SFTP服务器）的连接
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 747e82ff-d3e6-4945-8f29-80e4a190c96f
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1720'
ht-degree: 77%

---

# 外部帐户{#external-accounts}

利用外部帐户配置，可配置和测试对 Adobe Campaign 外部服务器的访问。

这些外部帐户可用于 Campaign 工作流访问和管理数据。

您可以设置以下类型的外部帐户：

* SFTP。有关更多信息，请参阅[此章节](#sftp-external-account)。
* Amazon Storage Service (S3)。有关更多信息，请参阅[此章节](#amazon-s3-external-account)。
* Adobe Experience Manager。有关更多信息，请参阅[此章节](#adobe-experience-manager-external-account)。
* Adobe Analytics。有关更多信息，请参阅[此章节](../../integrating/using/configure-campaign-analytics-integration.md)。
* Google reCAPTCHA。有关更多信息，请参阅[此章节](#google-recaptcha-external-account)。
* Microsoft Azure Blob Storage。有关更多信息，请参阅[此章节](#microsoft-azure-external-account)。
* OAuth 2.0。有关详细信息，请参见 [本节](#oauth-account).

>[!NOTE]
>
>Adobe 在产品预配过程中，会使用其他类型的外部帐户。从 Campaign Standard 17.9 版开始，仍可以定义 FTP 外部帐户，但在新的工作流活动中已不再可用。如果已设置该连接，则仍可使用该连接。

外部帐户可由管理员通过 **[!UICONTROL Administration > Application settings > External accounts]** 菜单进行配置。

## 创建外部帐户 {#creating-an-external-account}

Adobe Campaign 提供了一组预定义的外部帐户。要与外部系统（如用于文件传输的 FTP 服务器）建立连接，您可以创建自己的外部帐户。

技术工作流或营销策划工作流等技术流程，会使用外部帐户。在工作流中设置文件传输或与任何其他应用程序（Adobe Target、Experience Manager 等）进行数据交换时，您需要选择外部帐户。

1. 单击 **[!UICONTROL Create]** 按钮。
1. 输入标签。在工作流中选择外部帐户时，将使用标签和 ID。
1. 选择要创建的帐户类型。
1. 根据需要指定凭据、服务器地址、端口号或密钥，以配置对帐户的访问。

   所连接服务器的提供者通常会提供必需的信息。

1. 保存您的帐户。

外部帐户已创建并添加到帐户列表。现在可将其用于工作流活动和投放属性中的数据/文件传输或路由配置。

## SFTP外部帐户 {#sftp-external-account}

不同的外部帐户类型需要指定不同的信息。

对于 SFTP 外部帐户，请提供以下详细信息：

* 服务器地址。例如，**ftp.domain.com**。
* 端口号。例如，**22**。
* SFTP 服务器凭据：用于连接到服务器的帐户名称和密码。

### Adobe托管的SFTP服务器推荐 {#adobe-hosted-sftp-server-recommendations}

管理用于 ETL 的文件和数据时，这些文件存储在 Adobe 提供的托管 SFTP 服务器上。此 SFTP 旨在作为临时存储空间，您可以在其上控制文件的保留和删除。

如果未正确使用或监控，则该空间会快速填充服务器上可用的物理空间，并导致严重问题。这可能导致平台上的数据丢失或损坏。

为避免此类问题，Adobe 建议遵循以下最佳实践：

* 尽可能少地保留数据。
* 使用基于密钥的身份验证以避免密码过期。支持的格式仅限 **OpenSSH** 和 **SSH2**。您必须向 Adobe 支持团队提供公共密钥，才能将其上传到 Campaign 服务器。
* 仅将数据保留要求的时长。最大时限 15 天。
* 按照工作流程正确删除数据（通过消费数据的工作流程来管理保留）。
* 在 SFTP 上传和工作流程中使用批处理。
* 处理错误/例外状况。
* 时常登入 SFTP 以直接检查其内容。
* 请记住，SFTP 硬盘的管理主要由您负责。

列入允许列表另请注意，您尝试启动SFTP连接的公共IP必须添加到Campaign实例的。 可以通过向允许列表添加IP地址 [支持服务单](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)，并提供用于身份验证的公共密钥。

可从控制面板管理 SFTP 服务器。有关更多信息，请参阅[控制面板文档](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html)。

>[!NOTE]
>
>所有管理员用户都可访问控制面板。[此页面](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=zh-Hans#discover-control-panel)详细介绍了授予用户管理员访问权限的步骤。

## OAuth 2.0帐户 {#oauth-account}

对于OAuth 2.0外部帐户，请提供以下详细信息：

* A **授权类型**：仅限 **客户端凭据** 受支持。
* A **安全API URL**：输入授权端点。
* **OAuth 2.0敏感凭据**：此部分适用于本质上敏感的凭据。 添加凭据值后，会在屏幕上将其蒙版；在这种情况下，凭据值将不可读或编辑。 如果授权端点要求将特定凭据插入HTTP授权标头而不是POST正文参数，则可以选择该凭据的标头中的包含选项。
* **OAuth 2.0非敏感凭据**：本节适用于本质上不敏感的凭据。 添加凭据值后，凭据值将显示在屏幕上；凭据值也可以编辑。  如果授权端点要求将特定凭据插入HTTP授权标头而不是POST正文参数，则可以选择该凭据的标头中的包含选项。

输入帐户信息后，单击 **测试连接** 验证外部帐户是否已正确配置。

![](assets/external_accounts_OAuth.png)

>[!NOTE]
>
>凭据“Content-Type： application/x-www-form-urlencoded”和“grant_type=client_credentials”将自动添加到API调用中；因此，您不需要在凭据部分中添加它们。

## Amazon S3外部帐户 {#amazon-s3-external-account}

Amazon S3 服务器字段应按以下方式填写：

```
<S3 bucket name>.s3.amazonaws.com/<s3 object path>
```

要以 S3 加密模式存储文件，请选中 **[!UICONTROL Keep files in S3 encrypted]** 方框。

![](assets/external_accounts_2.png)

所连接服务器的提供者通常会提供必需的信息。

指定与您的端点关联的 **[!UICONTROL AWS Region]**。您可以在官方的 [Amazon S3 文档](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region)中查看受支持的地区和签名版本。

>[!NOTE]
>
>输入的 **[!UICONTROL Receiver server]** 不应包含 AWS 区域，稍后会自动将其添加到您的 URL 中。

### Amazon S3帐户建议 {#amazon-s3-account-recommendations}

为了帮助您设置 Amazon S3 帐户，我们建议您遵循以下建议：

* 创建严格存储段策略以限制对 S3 存储段的访问。在创建存储段时可以配置存储段策略。有关更多信息，请参阅 [Amazon S3 文档](https://docs.aws.amazon.com/AmazonS3/latest/dev//example-bucket-policies.html)。
* 在创建外部帐户时，通过勾选 **[!UICONTROL Keep files in S3 encrypted]** 方框，可启用加密以在 S3 存储桶中存储敏感数据。
* 授予存储段权限，以指定可访问存储段中对象的用户。有关存储桶权限的更多信息，请参阅 [Amazon S3 文档](https://docs.aws.amazon.com/AmazonS3/latest/dev//access-control-overview.html)。

## Adobe Experience Manager外部帐户 {#adobe-experience-manager-external-account}

将 Campaign 与 Experience Manager 集成时，会使用 Adobe Experience Manager 外部帐户。

[此文档](../../integrating/using/get-started-campaign-integrations.md)提供了与此集成相关的流程和要求。

在设置此新外部帐户时，必须提供以下详细信息：

* 服务器：输入 Adobe Experience Manager 服务器的 URL。例如：

  ```
  http://aem.domain.com:4502
  ```

* AEM 帐户凭据：使用访问 Adobe Experience Manager 实例的帐户。它应是 Experience Manager 中属于 campaign-remote 组的帐户。

## Google reCAPTCHA外部帐户 {#google-recaptcha-external-account}

>[!NOTE]
>
>Google reCAPTCHA 配置需要 Google 帐户。

利用 Google reCAPTCHA 机制，可保护登陆页面免受由机器人程序造成的垃圾邮件和滥用。对于您的客户而言，这是非侵入式的，因为它不需要与客户进行任何交互，并且基于与您网站的交互。要注册您的站点，请参阅[本页面](https://www.google.com/recaptcha/admin/create)。您必须选择V3 reCAPTCHA类型。

要将Google reCAPTCHA V3添加到登录页面，请在外部帐户中进行配置。 有关如何将其添加到登陆页面的更多信息，请参阅此[章节](../../channels/using/configuring-landing-page.md#setting-google-recaptcha)。

对于 Google reCAPTCHA V3 外部帐户，请提供以下详细信息：

* 外部帐户的 **[!UICONTROL Label]** 和 **[!UICONTROL ID]**
* **[!UICONTROL Type]**：Google reCAPTCHA
* 您的 **[!UICONTROL Site key]** 和 **[!UICONTROL Site secret]**
* 介于 0 到 1 之间的 **[!UICONTROL Threshold]**

  0.0 **[!UICONTROL Threshold]** 值表示它可能是一个机器人，而 1.0 值可能属于良好的交互。默认情况下，可以使用 0.5 的阈值。

![](assets/external_accounts_3.png)

## Microsoft Azure Blob Storage外部帐户 {#microsoft-azure-external-account}

>[!NOTE]
>
>有关在 Adobe Campaign Standard 中配置外部帐户所需的信息，可通过选择 **[!UICONTROL Settings]** > **[!UICONTROL Access keys]** 查看 Azure Portal。

Azure Blob Storage 连接器可用于通过 **[!UICONTROL Transfer file]** 工作流活动将数据导入或导出 Adobe Campaign。有关更多信息，请参阅此](../../automating/using/transfer-file.md#azure-blob-configuration-wf)章节[。

对于 Microsoft Azure Blob Storage 外部帐户，请提供以下详细信息：

* 外部帐户的 **[!UICONTROL Label]** 和 **[!UICONTROL ID]**
* **[!UICONTROL Type]**：Microsoft Azure Blob Storage
* 您的 **[!UICONTROL Account name]** 和 **[!UICONTROL Account key]**。要了解在何处查找您的帐户名称和密钥，请参阅本[页面](https://docs.microsoft.com/zh-cn/azure/storage/common/storage-account-keys-manage)。
* 您的 **[!UICONTROL Endpoint suffix]**。通过 Azure Portal 的 **[!UICONTROL Access keys]** 菜单中的 **[!UICONTROL Connection string]**，可找到该项。有关更多信息，请参见此[页面](https://docs.microsoft.com/zh-cn/azure/storage/common/storage-account-keys-manage)。
* 您的 **[!UICONTROL Container]** 名称。如果您计划使用多个容器，请创建与容器数量相同的外部帐户。
* 利用 **[!UICONTROL Concurrency]** 选项，可优化文件传输的速度。

![](assets/external_accounts_4.png)

配置完毕后，单击 **[!UICONTROL Test connection]** 将 Adobe Campaign 链接到 Microsoft Azure Blob Storage。

### Microsoft Azure Blob Storage建议 {#azure-blob-recommendations}

**加密**

Adobe Campaign 使用安全连接 (HTTPS) 访问 Microsoft Azure Blob Storage 帐户。

**帐户密钥**

配置外部帐户时，必须使用 Azure Portal 提供的 **[!UICONTROL Account key]** 之一。有关在何处查找帐户密钥的更多信息，请参阅本[页面](https://docs.microsoft.com/zh-cn/azure/storage/common/storage-account-keys-manage#view-access-keys-and-connection-string)。

**优化文件传输速度**

利用 **[!UICONTROL Concurrency]** 选项，可优化文件传输的速度。此选项代表用于执行文件传输的线程数。每个此类线程都将从 blob 下载约 1MB 的一部分。然后，它们将排队以写入磁盘。请注意，增加线程数，文件传输期间中应用程序所用资源的负载也会增加。

在文件传输完成后，您可以在工作流日志中查看性能指标。

**重试**

默认情况下，Azure Blob 的文件传输最多可进行四次重试。如果 Azure Storage 服务返回错误代码，如 503（服务器忙）或 500（操作超时），则可能表示您正在接近或已超过存储帐户的可扩展能力。使用新帐户或执行测试时，可能发生这种情况。

如果错误仍然存在，您可以通过高级菜单 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]** 创建一个选项，增加重试的次数。

如要实施，则必须按以下方式创建选项：

```
ID:        AzureBlob_Max_Retries
Date type: Integer
Default:   <the number of retries needed>
```
