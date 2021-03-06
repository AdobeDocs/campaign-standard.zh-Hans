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
source-git-commit: f75df49e7957437df72c814aa9055d34770f22d6
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 4%

---

# 连接系统与集成应用程序

## 将凭据添加到集成应用程序

的 **[!UICONTROL Settings]** 屏幕允许您指定Microsoft Dynamics 365和AdobeAPI凭据。 您还可以配置与Adobe Campaign SFTP实例相关的设置。

### Microsoft Dynamics 365凭据

Microsoft Dynamics 365凭据为集成应用程序授予从Microsoft Dynamics 365提取数据的权限。  您必须首先执行屏幕上的步骤 [为Campaign集成配置Microsoft Dynamics 365](../../integrating/using/d365-acs-configure-d365.md) 以生成将粘贴到此屏幕中的值。 下面描述的输入将引用此屏幕。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL Client ID]**:了解如何在 [此部分](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)

* **[!UICONTROL Client Secret]**:了解如何在 [此部分](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)

* **[!UICONTROL Tenant]**:了解如何在 [此部分](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)

* **[!UICONTROL URL]**:URL的格式为 `https://&lt;servername&gt;.api.crm.dynamics.com/`

### AdobeAPI凭据

Adobe Campaign凭据是使用 [Adobe I/O](https://www.adobe.io/). 您需要访问屏幕 [配置Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md) 并按照此处的说明操作，您才能填写此部分中的输入内容。

下图将详细介绍Adobe I/O和设置屏幕输入之间的映射。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *私钥*:定义此密钥的过程首先通过单击“生成公共/私有密钥对”按钮进行。 这将创建一个必须下载的zip文件。 下载后，解压缩文件，该文件将生成两个名为certificate_pub.crt和private.key的文件。 确保将private.key放置在安全位置，并且不要共享它。 在文本编辑器中打开private.key文件。 在文本编辑器中复制整个值(在PC上依次复制ctrl-A和ctrl-C，或在Mac上复制cmd-A和cmd-C)。 这应当包括整条带有“BEGIN PRIVATE KEY”和“END PRIVATE KEY”的行。 将此整个多行文本粘贴到“设置”屏幕的“私钥”输入中。

* *URL*:此值将符合以下模式：/mc.adobe.io/&lt;campaign-instance-name>. 集成应用程序的标题包含“Org”和“Instance”。 URL的“campaign-instance-name”部分只是在此实例值中找到的名称。

## Adobe Campaign SFTP设置 {#ac-smtp-settings}

这些设置是可选的。 如果您计划使用Adobe Campaign SFTP实例从连接器输出日志，则需要定义这些事件。 如果您在集成运行时遇到问题，并且需要调试输出为何不符合您的预期，则此功能会很有帮助。

设置SFTP服务器的另一个原因是，如果您计划运行选择加入/退出工作流，并且存在从Adobe Campaign到Microsoft Dynamics 365的数据流 **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** 或 **[!UICONTROL Bidirectional]**.

>[!IMPORTANT]
>
>您负责从SFTP文件夹访问和下载的信息。 如果信息包含个人数据，您有责任遵守任何适用的隐私法律和法规。 [了解详情](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy)。

要为Microsoft Dynamics 365集成定义Campaign SFTP设置，请访问以下部分：

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-sftp.png)

您需要指定：

* **SFTP主机**:此字段将包含 &lt;campaign-instance-name>.campaign.adobe.com 。 集成应用程序的标题包含 **组织** 和 **实例**. URL的“campaign-instance-name”部分只是在此实例值中找到的名称。

* **SFTP用户**:如果您有SFTP用户，请将其添加到此处。 否则，请参阅 [此部分](#ac-control-panel-settings). 在该过程中，您将看到用户名。

* **SFTP密钥**:如果您有SSH密钥，请将其添加到此处。 否则，请参阅 [此部分](#ac-control-panel-settings).

* 的 **IP范围** 需要包含在Adobe Campaign SFTP配置中。 需要这列入允许列表些端点，以便集成能够使用SFTP端点。

* 的 **是否要将日志导出到Adobe Campaign SFTP?** 允许您确定集成是否会将日志记录信息输出到SFTP端点。 如果Adobe Campaign或Microsoft Dynamics 365未显示您期望的信息，则可以使用此选项帮助进行调试。

## 在Adobe Campaign中设置SFTP {#ac-control-panel-settings}

通过 [营销活动控制面板](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hans) 在以下部分中：

* [关于 SFTP 管理](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html?lang=zh-Hans#sftp-management)

* [SFTP 存储管理](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#installing-ssh-key)

* [添加IP范围](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html?lang=en#sftp-management)

* [管理密钥](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#sftp-management)

* [登录到SFTP服务器](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html?lang=en#sftp-management)

完成配置后，使用私钥登录SFTP服务器并创建目录“d365_loads/exports”。

[访问此页面](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=en#sftp-management) 有关Adobe Campaign Standard SFTP服务器的信息。
