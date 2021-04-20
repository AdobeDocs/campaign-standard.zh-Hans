---
title: 配置活动-Dynamics集成应用程序
description: 了解如何配置活动-Dynamics集成应用程序
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 2%

---


# 连接系统与集成应用程序

## 向集成应用程序添加凭据

在&#x200B;**[!UICONTROL Settings]**&#x200B;屏幕中，可指定Microsoft Dynamics 365和Adobe API凭据。 您还可以配置与Adobe Campaign SFTP实例相关的设置。

### Microsoft Dynamics 365凭据

Microsoft Dynamics 365凭据授予集成应用程序从Microsoft Dynamics 365中提取数据的权限。  必须首先执行屏幕[为活动集成](../../integrating/using/d365-acs-configure-d365.md)配置Microsoft Dynamics 365上的步骤，才能生成将粘贴到此屏幕中的值。 下面描述的输入将引用此屏幕。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL Client ID]**:在本节中了解如何引用您的客 [户端ID](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)

* **[!UICONTROL Client Secret]**:在本节中了解如何生成您的客 [户机密](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)

* **[!UICONTROL Tenant]**:了解如何在本节中查找您的租 [户ID](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)

* **[!UICONTROL URL]**:url的格式为“https://&lt;servername>.api.crm.dynamics.com/

### Adobe API凭据

Adobe Campaign凭据使用[Adobe I/O](https://www.adobe.io/)生成。 您需要访问屏幕[配置Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md)并按照此处的说明操作，才能填写本节中的输入。

下图将详细说明Adobe I/O和设置屏幕输入之间的映射。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *私钥*:通过单击“生成公共/私有密钥对”按钮来定义此开始的过程。这将创建一个必须下载的zip文件。 下载后，解压缩文件，该文件将生成两个名为certificate_pub.crt和private.key的文件。 请确保将private.key放在安全位置，但不要共享它。 在文本编辑器中打开private.key文件。 在文本编辑器中复制整个值（在PC上依次为ctrl-A和ctrl-C，在Mac上依次为cmd-A和cmd-C）。 这应包括全部带有“BEGIN PRIVATE KEY”和“END PRIVATE KEY”的行。 将整个多行文本粘贴到“设置”屏幕的“私钥”输入中。

* *URL*:此值将适合模式https\://mc.adobe.io/&lt;campaign-instance-name>。集成应用程序的标题包括“Org”和“Instance”。 url的“活动-instance-name”部分只是在此实例值中找到的名称。

## Adobe CampaignSFTP设置{#ac-smtp-settings}

这些设置是可选的。 如果您计划使用Adobe Campaign SFTP实例从连接器输出日志，则需要定义它们。 如果您在集成运行时遇到问题，并且需要调试输出为什么不符合您的预期，则此功能会很有帮助。

设置SFTP服务器的另一个原因是，如果您计划运行选择加入/退出工作流，并且存在从Adobe Campaign到Microsoft Dynamics 365（**[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**&#x200B;或&#x200B;**[!UICONTROL Bidirectional]**）的数据流。

>[!IMPORTANT]
>
>您负责从SFTP文件夹访问和下载的信息。 如果信息包含个人数据，您有责任遵守任何适用的隐私法律和法规。 [了解详情](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy)。


要为Microsoft Dynamics 365集成定义活动SFTP设置，请访问以下部分：

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-sftp.png)

您需要指定：

* **SFTP主机**:此字段将 &lt;campaign-instance-name>包含。活动.adobe.com。集成应用程序的标头包括&#x200B;**Org**&#x200B;和&#x200B;**Instance**。 url的“活动-instance-name”部分只是在此实例值中找到的名称。

* **SFTP用户**:如果您有SFTP用户，请在此处添加它。否则，请参阅[此部分](#ac-control-panel-settings)。 在此过程中，将显示用户名。

* **SFTP密钥**:如果您有SSH密钥，请在此处添加它。否则，请参阅[此部分](#ac-control-panel-settings)。

* 您的Adobe CampaignSFTP配置中需要包含&#x200B;**IP范围**。 需要这列入允许列表些端点，以便集成能够利用SFTP端点。

* **是否要将日志导出到您的Adobe CampaignSFTP?** 允许您确定集成是否将日志信息输出到SFTP端点。如果Adobe Campaign或Microsoft Dynamics 365未显示您需要的信息，则此选项可用于帮助进行调试。

## Adobe Campaign {#ac-control-panel-settings}中的SFTP设置

通过以下部分[活动控制面板](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hans)发现SFTP管理：

* [关于 SFTP 管理](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html?lang=en#sftp-management)

* [SFTP 存储管理](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#installing-ssh-key)

* [添加IP范围](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html?lang=en#sftp-management)

* [管理密钥](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#sftp-management)

* [登录到SFTP服务器](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html?lang=en#sftp-management)

完成配置后，使用私钥登录SFTP服务器并创建目录“d365_loads/exports”。

[有关Adobe Campaign Standard ](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=en#sftp-management) SFTP服务器的信息，请访问此页。
