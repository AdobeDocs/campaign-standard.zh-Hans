---
title: 配置Campaign-Dynamics集成应用程序
description: 了解如何配置Campaign-Dynamics集成应用程序
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 184bc656-2107-4380-9b35-148cb4380547
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 2%

---

# 连接系统与集成应用程序

## 向集成应用程序添加凭据

**[!UICONTROL Settings]**&#x200B;屏幕允许您指定Microsoft Dynamics 365和Adobe API凭据。 您还可以配置与Adobe Campaign SFTP实例相关的设置。

### Microsoft Dynamics 365凭据

Microsoft Dynamics 365凭据为集成应用程序提供从Microsoft Dynamics 365中提取数据的权限。  您必须首先按照[为Campaign集成配置Microsoft Dynamics 365](../../integrating/using/d365-acs-configure-d365.md)屏幕上的步骤进行操作，以生成将粘贴到此屏幕的值。 下面介绍的输入将引用此屏幕。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL Client ID]**：在[本节](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)中了解如何引用您的客户端ID

* **[!UICONTROL Client Secret]**：在[本节](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)中了解如何生成您的客户端密钥

* **[!UICONTROL Tenant]**：在[此部分](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)中了解如何查找您的租户ID

* **[!UICONTROL URL]**： URL的格式为`https://&lt;servername&gt;.api.crm.dynamics.com/`

### Adobe API凭据

Adobe Campaign凭据是使用[Adobe I/O](https://www.adobe.io/)生成的。 您需要访问屏幕[配置Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md)并按照该屏幕上的说明进行操作，然后才能填写此部分中的输入内容。

* 选择身份验证类型作为Oauth，因为基于JWT的身份验证已被弃用。
* 下图将详细解释Adobe I/O与设置屏幕输入之间的映射。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *URL*：此值将符合模式https\：//mc.adobe.io/&lt;campaign-instance-name>。 集成应用程序的标头包括“Org”和“Instance”。 URL的“campaign-instance-name”部分只是此实例值中的名称。

## Adobe Campaign SFTP设置 {#ac-smtp-settings}

这些设置是可选的。 如果您计划使用Adobe Campaign SFTP实例从连接器输出日志，则需要定义它们。 如果您在集成运行时遇到问题，并且需要调试输出为何不符合您的预期，这将很有帮助。

设置SFTP服务器的另一个原因是，如果您计划运行选择加入/退出工作流，并且存在从Adobe Campaign到Microsoft Dynamics 365的数据流，即&#x200B;**[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**&#x200B;或&#x200B;**[!UICONTROL Bidirectional]**。

>[!IMPORTANT]
>
>您对从SFTP文件夹访问和下载的信息负责。 如果信息包含个人数据，则您有责任遵守任何适用的隐私法律和法规。 [了解详情](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy)。
>

要为Microsoft Dynamics 365集成定义Campaign SFTP设置，请访问以下部分：

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-sftp.png)

您需要指定：

* **SFTP主机**：此字段将包含&lt;campaign-instance-name>.campaign.adobe.com。 集成应用程序的标头同时包含&#x200B;**组织**&#x200B;和&#x200B;**实例**。 URL的“campaign-instance-name”部分只是此实例值中的名称。

* **SFTP用户**：如果您有SFTP用户，请将其添加到此处。 否则，请参阅[此部分](#ac-control-panel-settings)。 在该过程中，将向您显示用户名。

* **SFTP密钥**：如果您有SSH密钥，请在此处添加它。 否则，请参阅[此部分](#ac-control-panel-settings)。

* 需要将&#x200B;**IP范围**&#x200B;包含在您的Adobe Campaign SFTP配置中。 集成需要列入允许列表这些组件才能使用SFTP端点。

* **是否要将日志导出到Adobe Campaign SFTP？**&#x200B;允许您确定集成是否会将日志记录信息输出到SFTP端点。 如果Adobe Campaign或Microsoft Dynamics 365未显示您预期的信息，则可以使用此帮助进行调试。

## Adobe Campaign中的SFTP设置 {#ac-control-panel-settings}

在以下部分中了解使用[Campaign控制面板](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hans)进行SFTP管理：

* [关于 SFTP 管理](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html?lang=zh-Hans#sftp-management)

* [SFTP 存储管理](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html#installing-ssh-key)

* [添加IP范围](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html#sftp-management)

* [管理密钥](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html#sftp-management)

* [登录到您的SFTP服务器](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html#sftp-management)

配置完成后，使用私钥登录SFTP服务器并创建目录“d365_loads/exports”。

[访问此页面](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=zh-Hans#sftp-management)，以了解有关Adobe Campaign Standard SFTP服务器的信息。
