---
title: 配置活动-动态集成应用程序
description: 了解如何配置活动-动态集成应用程序
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: efa30d7ed4a0caf929da6f485681078318849cda
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 2%

---


# 使用集成应用程序连接系统

## 向集成应用程序添加凭据

在&#x200B;**[!UICONTROL Settings]**&#x200B;屏幕中，可指定Microsoft Dynamics 365和AdobeAPI凭据。 您还可以配置与Adobe CampaignSFTP实例相关的设置。

### Microsoft Dynamics 365凭据

Microsoft Dynamics 365凭据授予集成应用程序从Microsoft Dynamics 365中提取数据的权限。  必须首先按照屏幕[上的步骤配置Microsoft Dynamics 365以进行活动集成](../../integrating/using/d365-acs-configure-d365.md)，才能生成将粘贴到此屏幕中的值。 下面描述的输入将引用此屏幕。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL Client ID]**:在本节中了解如何引用您的客 [户端ID](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)

* **[!UICONTROL Client Secret]**:在本节中了解如何生成您的客户 [端机密](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)

* **[!UICONTROL Tenant]**:了解如何在本节中查找您的 [租户ID](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)

* **[!UICONTROL URL]**:url的格式为https://&lt;servername>.api.crm.dynamics.com/

### AdobeAPI凭据

Adobe Campaign凭据使用[Adobe I/O](https://www.adobe.io/)生成。 您需要访问屏幕[配置Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md)并按照此处的说明操作，才能填写本节中的输入。

下图将详细说明Adobe I/O与设置屏幕输入之间的映射。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *私钥*:通过单击“生成公共／私有密钥对”按钮定义此开始的过程。这将创建一个必须下载的zip文件。 下载文件后，解压该文件，它将生成两个名为certificate_pub.crt和private.key的文件。 请确保将private.key放在安全位置，而不要共享它。 在文本编辑器中打开private.key文件。 在文本编辑器中复制整个值（在PC上依次为ctrl-A和ctrl-C，在Mac上依次为cmd-A和cmd-C）。 这应包括完整的带有“BEGIN PRIVATE KEY”和“END PRIVATE KEY”的行。 将整个多行文本粘贴到“设置”屏幕的“私钥”输入中。

* *URL*:此值将适合模式https\://mc.adobe.io/&lt;campaign-instance-name>。集成应用程序的标题包括“组织”和“实例”。 url的“活动-实例——名称”部分只是在此实例值中找到的名称。

## Adobe CampaignSFTP设置{#ac-smtp-settings}

这些设置是可选的。 如果您计划使用Adobe CampaignSFTP实例从连接器输出日志，则需要定义它们。 如果您在集成运行时遇到问题，并且需要调试输出为何不符合您的预期，这将很有帮助。

设置SFTP服务器的另一个原因是，如果您计划运行参与／退出工作流，并且存在从Adobe Campaign到Microsoft Dynamics 365的数据流，即&#x200B;**[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**&#x200B;或&#x200B;**[!UICONTROL Bidirectional]**。

>[!IMPORTANT]
>
>您负责从SFTP文件夹访问和下载的信息。 如果信息包含个人数据，您有责任遵守任何适用的隐私法律和法规。 [了解详情](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy)。


要为Microsoft Dynamics 365集成定义活动SFTP设置，请访问以下部分：

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-sftp.png)

您需要指定：

* **SFTP主机**:此字段将 &lt;campaign-instance-name>包含。活动.adobe.com。集成应用程序的标题包括&#x200B;**Org**&#x200B;和&#x200B;**Instance**。 url的“活动-实例——名称”部分只是在此实例值中找到的名称。

* **SFTP用户**:如果您有SFTP用户，请将其添加到此处。否则，请参阅[此部分](#ac-control-panel-settings)。 在此过程中，将显示用户名。

* **SFTP密钥**:如果您有SSH密钥，请在此处添加它。否则，请参阅[此部分](#ac-control-panel-settings)。

* **IP范围**&#x200B;需要包含在Adobe CampaignSFTP配置中。 需要这列入允许列表些端点，以便集成能够利用SFTP端点。

* **是否要将日志导出到Adobe CampaignSFTP?** 允许您确定集成是否将日志记录信息输出到SFTP端点。如果Adobe Campaign或Microsoft Dynamics 365未显示您期望的信息，则此选项可用于帮助进行调试。

## Adobe Campaign{#ac-control-panel-settings}中的SFTP设置

在以下部分中发现具有[活动控制面板](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hans)的SFTP管理：

* [关于 SFTP 管理](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html?lang=en#sftp-management)

* [SFTP 存储管理](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#installing-ssh-key)

* [添加IP范围](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html?lang=en#sftp-management)

* [管理密钥](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#sftp-management)

* [登录到SFTP服务器](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html?lang=en#sftp-management)

完成配置后，使用私钥登录SFTP服务器并创建目录“d365_loads/exports”。

[请访问本](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=en#sftp-management) 页，了解有关Adobe Campaign StandardSFTP服务器的信息。
