---
title: 外部帐户
seo-title: 外部帐户
description: 外部帐户
seo-description: 配置外部帐户，以设置与外部系统(如SFTP服务器)连接。
page-status-flag: 从未激活
uuid: 5d2e2e3d-5d1f-4466-97e5-842c50390146
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: 应用程序设置
discoiquuid: d5c6a3d4-f767-46c1-a8 c0-3b9 dc52 dcf8
internal: n n
snippet: y
context-tags: extAccount，main；Extaccount，概述
translation-type: tm+mt
source-git-commit: 0fcedd464ae2074e7eda793bbf20cc53ce04f324

---


# External accounts{#external-accounts}

外部帐户是一个配置，用于配置和测试访问Adobe Campaign外部服务器的权限。

这些外部帐户可在Campaign工作流程中使用以访问和管理数据。

您可以设置以下类型的外部帐户：

* SFTP。For more on this, refer to [this section](../../administration/using/external-accounts.md#sftp-external-account).
* Amazon Storage Service(S3)。For more on this, refer to [this section](../../administration/using/external-accounts.md#amazon-s3-external-account).
* Adobe Experience Manager。For more on this, refer to [this section](../../administration/using/external-accounts.md#adobe-experience-manager-external-account).
* Adobe Analytics。For more on this, refer to [this section](../../integrating/using/configure-campaign-analytics-integration.md).
* Google ReCAPTCHA.For more on this, refer to [this section](../../administration/using/external-accounts.md#google-recaptcha-external-account).

>[!NOTE]
>
>Adobe在产品供应过程中使用其他类型的外部帐户。从Campaign Standard17.9版本中，仍可以定义FTP外部帐户，但不再可用于新的工作流程活动。如果您已经设置了连接，则仍处于启用状态。

External accounts can be configured by administrators under the **[!UICONTROL Administration > Application settings > External accounts]** menu.

## Creating an external account {#creating-an-external-account}

Adobe Campaign附带一系列预定义的外部帐户。为了设置与外部系统(如用于文件传输的FTP服务器)建立连接，您可以创建自己的外部帐户。

外部帐户由技术工作流程或营销活动工作流程等技术流程使用。在工作流中设置文件传输或与任何其他应用程序(Adobe Target、Experience Manager等)进行数据交换时，您需要选择外部帐户。

1. Click the **[!UICONTROL Create]** button.
1. 输入标签。在工作流中选择外部帐户时，将使用标签和ID。
1. 选择要创建的帐户类型。
1. 在相关的情况下指定凭据、服务器地址、端口号和密钥，以配置对帐户的访问。

   必要的信息通常由您连接到的服务器提供商提供。

1. 保存帐户。

将创建外部帐户并将其添加到帐户列表。它现在可用于您的数据/文件传输或工作流活动和交付属性中的配置配置。

## SFTP external account {#sftp-external-account}

不同的外部帐户类型需要指定不同的信息。

对于SFTP外部帐户，提供以下详细信息：

* 服务器地址。For example, **ftp.domain.com**.
* 端口号。For example, **22**.
* SFTP服务器凭据：用于连接服务器的帐户名和口令。

### Adobe hosted SFTP server recommendations {#adobe-hosted-sftp-server-recommendations}

为ETL目的管理文件和数据时，这些文件存储在Adobe提供的托管SFTP服务器上。此SFTP设计为可在其中控制文件保留和删除的临时存储空间。

当未正确使用或监视时，此空间可快速填充服务器上可用的物理空间并造成严重问题。它可能会导致平台上的数据丢失或损坏。

为了避免出现此类问题，Adobe建议遵循以下最佳做法：

* 尽可能保持最低数据。
* 使用基于密钥的身份验证避免密码过期。Supported formats are **OpenSSH** and **SSH2** only. 您必须向Adobe支持团队提供公钥，才能在Campaign服务器上上传它。
* 始终保持数据的一致性。15天是最大时限。
* 使用工作流正确删除数据(管理使用数据的工作流中的保留)。
* 使用SFTP上传以及工作流中的批量操作。
* 处理错误/例外情况。
* 偶尔，登录到SFTP以直接检查躺在那里的内容。
* 记住，SFTP磁盘管理主要是您的职责。

另外，请注意，您尝试启动SFTP连接的公共IP必须在Campaign实例上列入白名单。Whitelisting of IP addresses can be requested via a [support ticket](https://support.neolane.net), along with providing the public key to use for authentication.

可以从控制面板管理SFTP服务器。For more information, refer to the [Control Panel documentation](https://helpx.adobe.com/campaign/kb/control-panel-sftp.html).

>[!NOTE]
>
>控制面板仅适用于AWS上托管的客户的管理员用户。
Check if your instance is hosted on AWS [here](https://helpx.adobe.com/campaign/kb/control-panel-faq.html#IMSOrgID).

## Amazon S3 external account {#amazon-s3-external-account}

Amazon S服务器字段应填写如下：

```
<S3 bucket name>.s3.amazonaws.com/<s3 object path>
```

To store your file in S3 encrypted mode, check the **[!UICONTROL Keep files in S3 encrypted]** box.

![](assets/external_accounts_2.png)

必要的信息通常由您连接到的服务器提供商提供。

Specify the **[!UICONTROL AWS Region]** associated to your endpoint. You can check the supported regions and signature versions in the official [Amazon S3 documentation](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region) .

### Amazon S3 account recommendations {#amazon-s3-account-recommendations}

为了帮助您设置Amazon S帐户，我们建议您遵循以下建议：

* 创建严格的桶策略以限制访问S3buckets。可在创建桶时配置Bucket策略。For more information, refer to the [Amazon S3 documentation](http://docs.aws.amazon.com/AmazonS3/latest/dev//example-bucket-policies.html).
* While creating an external account, enable the encryption to store sensitive data in the S3 bucket by checking the **[!UICONTROL Keep files in S3 encrypted]** box.
* 授予库权限以指定可在桶中访问对象的用户。For more information on bucket permission, refer to the [Amazon S3 documentation](http://docs.aws.amazon.com/AmazonS3/latest/dev//access-control-overview.html)

## Adobe Experience Manager external account {#adobe-experience-manager-external-account}

在将Campaign与Experience Manager集成时，将使用Adobe Experience Manager外部帐户。

Process and requirements related to this integration are available in [this document](../../integrating/using/about-campaign-integrations.md).

在设置此新外部帐户时，您需要提供以下详细信息：

* 服务器：输入Adobe Experience Manager服务器的URL。For example, **http://aem.domain.com:4502**.
* AEM帐户凭据：使用将访问Adobe Experience Manager实例的帐户。它应该是Experience Manager中营销活动远程组的一个帐户部分。

## Google reCAPTCHA external account {#google-recaptcha-external-account}

>[!NOTE]
>
>Google ReCAPTCHA配置需要Google帐户。

Google ReCAPTCHA机制允许您保护登陆页面免受蠕虫造成的垃圾邮件和滥用。这对客户不会产生打扰，因为它不需要来自客户的任何互动，并且基于与您网站的交互。To register your site, refer to this [page](https://www.google.com/recaptcha/admin/create). 您需要选择V3RECAPTCHA类型。

要将Google ReCAPTCHA V添加到登录页面，您首先需要在外部帐户中对其进行配置。For more information on how to add it to your landing page, refer to this [section](../../channels/using/designing-a-landing-page.md#setting-google-recaptcha).

对于Google ReapPTCHA V外部帐户，请提供以下详细信息：

* A **[!UICONTROL Label]** and **[!UICONTROL ID]** of your external account
* **[!UICONTROL Type]**：Google ReCAPTCHA
* Your **[!UICONTROL Site key]** and **[!UICONTROL Site secret]**
* A **[!UICONTROL Threshold]** between 0 and 1

   **[!UICONTROL Threshold]** 0.0值意味着可能是机器人程序，1.0可能是一个良好的交互。默认情况下，您可以使用0.5的阈值。

![](assets/external_accounts_3.png)

