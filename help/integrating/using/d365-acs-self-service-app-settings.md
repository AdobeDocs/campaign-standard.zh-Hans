---
title: 配置Campaign-Dynamics集成应用程序
description: 了解如何配置Campaign-Dynamics集成应用程序
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 184bc656-2107-4380-9b35-148cb4380547
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 4%

---

# 连接系统与集成应用程序

## 向集成应用程序添加凭据

此 **[!UICONTROL Settings]** 屏幕允许您指定Microsoft Dynamics 365和AdobeAPI凭据。 您还可以配置与Adobe Campaign SFTP实例相关的设置。

### Microsoft Dynamics 365凭据

Microsoft Dynamics 365凭据为集成应用程序提供从Microsoft Dynamics 365中提取数据的权限。  您必须首先按照屏幕上的步骤操作 [为Campaign集成配置Microsoft Dynamics 365](../../integrating/using/d365-acs-configure-d365.md) 以生成将粘贴到此屏幕中的值。 下面介绍的输入将引用此屏幕。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL Client ID]**：了解如何在中引用您的客户端ID [本节](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)

* **[!UICONTROL Client Secret]**：了解如何在中生成您的客户端密钥 [本节](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)

* **[!UICONTROL Tenant]**：了解如何在中查找您的租户ID [本节](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)

* **[!UICONTROL URL]**：URL将具有以下格式 `https://&lt;servername&gt;.api.crm.dynamics.com/`

### AdobeAPI凭据

使用以下方式生成Adobe Campaign凭据 [Adobe I/O](https://www.adobe.io/). 您需要访问屏幕 [配置Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md) 并遵循该说明，然后才能填写此部分中的输入内容。

下图将详细解释Adobe I/O与设置屏幕输入之间的映射。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *私钥*：定义此值的过程从单击“生成公钥/私钥对”按钮开始。 这将创建一个您必须下载的zip文件。 下载文件后，解压缩该文件，这将产生两个名为certificate_pub.crt和private.key的文件。 请确保将private.key放在安全位置，并且不要共享它。 在文本编辑器中打开private.key文件。 在文本编辑器中复制整个值(在PC上依次按ctrl-A和ctrl-C，在Mac上依次按cmd-A和cmd-C)。 这应该包括包含“BEGIN PRIVATE KEY”和“END PRIVATE KEY”的完整行。 将此完整的多行文本粘贴到“设置”屏幕中的“私钥”输入中。

* *URL*：此值将采用以下模式：https\：//mc.adobe.io/&lt;campaign-instance-name>. 集成应用程序的标头包括“Org”和“Instance”。 URL的“campaign-instance-name”部分只是此实例值中的名称。

## Adobe Campaign SFTP设置 {#ac-smtp-settings}

这些设置是可选的。 如果您计划使用Adobe Campaign SFTP实例从连接器输出日志，则需要定义它们。 如果您在集成运行时遇到问题，并且需要调试输出为何不符合您的预期，这将很有帮助。

设置SFTP服务器的另一个原因是，如果您计划运行选择加入/退出工作流，并且存在从Adobe Campaign到Microsoft Dynamics 365的数据流，也就是 **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** 或 **[!UICONTROL Bidirectional]**.

>[!IMPORTANT]
>
>您对从SFTP文件夹访问和下载的信息负责。 如果信息包含个人数据，则您有责任遵守任何适用的隐私法律和法规。 [了解详情](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy)。
>

要为Microsoft Dynamics 365集成定义Campaign SFTP设置，请访问以下部分：

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-sftp.png)

您需要指定：

* **SFTP主机**：此字段将包含 &lt;campaign-instance-name>.campaign.adobe.com. 集成应用程序的标头同时包括 **组织** 和 **实例**. URL的“campaign-instance-name”部分只是此实例值中的名称。

* **SFTP用户**：如果您有SFTP用户，请将其添加到此处。 否则，请参阅 [本节](#ac-control-panel-settings). 在该过程中，将向您显示用户名。

* **SFTP密钥**：如果您有SSH密钥，请在此处添加它。 否则，请参阅 [本节](#ac-control-panel-settings).

* 此 **IP范围** 将需要包含在您的Adobe Campaign SFTP配置中。 集成需要列入允许列表这些组件才能使用SFTP端点。

* 此 **是否要将日志导出到Adobe Campaign SFTP？** 允许您确定集成是否会将日志记录信息输出到SFTP端点。 如果Adobe Campaign或Microsoft Dynamics 365未显示您预期的信息，则可以使用此帮助进行调试。

## Adobe Campaign中的SFTP设置 {#ac-control-panel-settings}

发现SFTP管理 [营销活动控制面板](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hans) 在以下部分中：

* [关于 SFTP 管理](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html?lang=zh-Hans#sftp-management)

* [SFTP 存储管理](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html#installing-ssh-key)

* [添加IP范围](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html#sftp-management)

* [管理密钥](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html#sftp-management)

* [登录到SFTP服务器](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html#sftp-management)

配置完成后，使用私钥登录SFTP服务器并创建目录“d365_loads/exports”。

[访问此页面](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=zh-Hans#sftp-management) 有关Adobe Campaign Standard SFTP服务器的信息。
