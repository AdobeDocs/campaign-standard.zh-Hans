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
source-git-commit: 9c04148a6c0eafdd909c461fc3e927ec8c8fbfed

---


# 外部帐户{#external-accounts}

外部帐户是一种配置，允许您配置和测试对Adobe Campaign外部服务器的访问。

这些外部帐户可用于Campaign工作流程中访问和管理数据。

您可以设置以下类型的外部帐户：

* SFTP。 如需详细信息，请参阅[此部分](#sftp-external-account)。
* Amazon Storage Service(S3)。 如需详细信息，请参阅[此部分](#amazon-s3-external-account)。
* Adobe Experience Manager。 如需详细信息，请参阅[此部分](#adobe-experience-manager-external-account)。
* Adobe Analytics。 如需详细信息，请参阅[此部分](../../integrating/using/configure-campaign-analytics-integration.md)。
* Google reCAPTCHA。 如需详细信息，请参阅[此部分](#google-recaptcha-external-account)。

>[!NOTE]
>
>Adobe在产品配置过程中会使用其他类型的外部帐户。 从Campaign Standard 17.9版本中，FTP外部帐户仍可以定义，但在新的工作流程活动中不再可用。 如果已设置连接，则该连接仍处于启用状态。

管理员可以在菜单下配置外部 **[!UICONTROL Administration > Application settings > External accounts]**帐户。

## 创建外部帐户 {#creating-an-external-account}

Adobe Campaign附带一组预定义的外部帐户。 要与外部系统（如用于文件传输的FTP服务器）建立连接，您可以创建自己的外部帐户。

技术流程（如技术工作流或营销活动工作流程）使用外部帐户。 在工作流中设置文件传输或与任何其他应用程序（Adobe Target、Experience Manager等）进行数据交换时，您需要选择一个外部帐户。

1. Click the **[!UICONTROL Create]**button.
1. 输入标签。 在工作流中选择外部帐户时，将使用标签和ID。
1. 选择要创建的帐户类型。
1. 通过在相关时指定凭据、服务器地址、端口号或密钥，配置对帐户的访问。

   必需的信息通常由您所连接的服务器的提供者提供。

1. 保存帐户。

将创建外部帐户并将其添加到帐户列表。 它现在可用于工作流活动和交付属性中的数据／文件传输或路由配置。

## SFTP外部帐户 {#sftp-external-account}

不同的外部帐户类型需要指定不同的信息。

对于SFTP外部帐户，请提供以下详细信息：

* 服务器地址。 例如， **ftp.domain.com**。
* 端口号。 例如， **22**。
* SFTP服务器凭据：用于连接到服务器的帐户名和口令。

### Adobe托管的SFTP服务器建议 {#adobe-hosted-sftp-server-recommendations}

管理用于 ETL 的文件和数据时，这些文件存储在 Adobe 提供的托管 SFTP 服务器上。此 SFTP 旨在作为临时存储空间，您可以在其上控制文件的保留和删除。

如果未正确使用或监视，该空间会快速填充服务器上可用的物理空间，并导致严重问题。 它可能导致您的平台上的数据丢失或损坏。

为避免此类问题，Adobe建议遵循以下最佳实践：

* 保持尽可能少的数据。
* 使用基于密钥的身份验证来避免口令过期。 支持的格 **式仅****限OpenSSH和** SSH2。 您必须向Adobe支持团队提供公钥，才能将其上传到Campaign服务器上。
* 只要需要多长时间，即可保留数据。 15天为最大时限。
* 按照工作流程正确删除数据（通过消费数据的工作流程来管理保留）。
* 在 SFTP 上传和工作流程中使用批处理。
* 处理错误/例外状况。
* 时常登入 SFTP 以直接检查其内容。
* 请记住，SFTP 硬盘的管理主要由您负责。

另外，请注意，您尝试从中启动SFTP连接的公共IP必须列在营销活动实例的白名单中。 IP地址的白名单可以通过支 [持票证请求](https://support.neolane.net)，并提供用于身份验证的公共密钥。

SFTP服务器可以从控制面板进行管理。 有关详细信息，请参阅控 [制面板文档](https://docs.adobe.com/content/help/en/control-panel/using/sftp-management/about-sftp-management.html)。

>[!NOTE]
>
>控制面板仅对在AWS上托管的客户的管理员用户可用。
在此处检查您的实例是否托管在AWS [上](https://docs.adobe.com/content/help/en/control-panel/using/faq.html#ims-org-id)。

## Amazon S3外部帐户 {#amazon-s3-external-account}

Amazon S3服务器字段应填写如下：

```
<S3 bucket name>.s3.amazonaws.com/<s3 object path>
```

要以S3加密模式存储文件，请选中此 **[!UICONTROL Keep files in S3 encrypted]**框。

![](assets/external_accounts_2.png)

必需的信息通常由您所连接的服务器的提供者提供。

指定与 **[!UICONTROL AWS Region]**您的端点关联的。 您可以在官方[Amazon S3文档中查看受支持区域和签名版本](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region)。

>[!NOTE]
>
>您 **[!UICONTROL Receiver server]**应该在没有AWS区域的情况下输入，稍后会自动将其添加到您的URL。

### Amazon S3帐户建议 {#amazon-s3-account-recommendations}

为了帮助您设置Amazon S3帐户，我们建议您遵循以下建议：

* 创建严格的存储段策略以限制对S3存储段的访问。 可在创建存储段时配置存储段策略。 有关详细信息，请参阅 [Amazon S3文档](https://docs.aws.amazon.com/AmazonS3/latest/dev//example-bucket-policies.html)。
* 在创建外部帐户时，通过选中该框，启用加密功能可将敏感数据存储在S3存储 **[!UICONTROL Keep files in S3 encrypted]**桶中。
* 授予存储段权限，以指定谁可以访问存储段中的对象。 有关存储段权限的详细信息，请参阅 [Amazon S3文档](https://docs.aws.amazon.com/AmazonS3/latest/dev//access-control-overview.html)。

## Adobe Experience manager外部帐户 {#adobe-experience-manager-external-account}

在将Campaign与Experience manager集成时，会使用Adobe Experience manager外部帐户。

本文档提供与此集成相关的流程和 [要求](../../integrating/using/about-campaign-integrations.md)。

在设置此新外部帐户时，您需要提供以下详细信息：

* 服务器：输入Adobe Experience Manager服务器的URL。 例如， **http://aem.domain.com:4502**。
* AEM帐户凭据：使用将访问Adobe Experience manager实例的帐户。 它应是Experience Manager中营销活动远程组的帐户部分。

## Google reCAPTCHA外部帐户 {#google-recaptcha-external-account}

>[!NOTE]
>
>Google reCAPTCHA配置需要Google帐户。

Google reCAPTCHA机制允许您保护登录页面免受由机器人程序引起的垃圾邮件和滥用。 这对于您的客户来说是非侵入式的，因为它不需要客户进行任何交互，并且基于与您网站的交互。 要注册您的站点，请参阅本 [页](https://www.google.com/recaptcha/admin/create)。 您需要选择V3 reCAPTCHA类型。

要将Google reCAPTCHA V3添加到登录页面，您首先需要在外部帐户中配置它。 有关如何将其添加到登录页面的详细信息，请参阅此 [部分](../../channels/using/configuring-landing-page.md#setting-google-recaptcha)。

对于Google reCAPTCHA V3外部帐户，请提供以下详细信息：

* A **[!UICONTROL Label]**和**[!UICONTROL ID]** 您的外部帐户
* **[!UICONTROL Type]**:Google reCAPTCHA
* 您的 **[!UICONTROL Site key]**和**[!UICONTROL Site secret]**
* A **[!UICONTROL Threshold]**0到1之间

   0.0值表 **[!UICONTROL Threshold]**示它可能是一个机器人，1.0可能是一个良好的交互。 默认情况下，可以使用0.5的阈值。

![](assets/external_accounts_3.png)
