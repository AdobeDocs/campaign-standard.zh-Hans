---
title: 配置移动应用程序
description: 了解如何使用SDK V4或Experience PlatformSDK配置Adobe Campaign以发送推送通知或应用程序内消息。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 5f9a8e84-a362-42b6-8bd2-e5d56214c1db
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '1273'
ht-degree: 5%

---

# 配置移动应用程序{#configuring-a-mobile-application}

## 使用Adobe Experience Platform SDK配置移动应用程序 {#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
>推送通知和应用程序内实施必须由专家用户执行。 如需帮助，请联系您的Adobe客户经理或专业服务合作伙伴。

要使用Experience PlatformSDK应用程序发送推送通知和应用程序内消息，必须在Adobe Experience PlatformExperience PlatformExperience Platform Launch中设置移动应用程序，并在Adobe Campaign中进行配置。

有关已弃用的功能Mobile版本4 SDK的更多信息，请参阅此[页面](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4-deprecated.html)。

设置移动应用程序后，您可以检索其收集的PII数据，以从数据库中创建或更新用户档案。 有关更多信息，请参阅此章节：[基于移动应用程序数据创建和更新用户档案信息](../../channels/using/updating-profile-with-mobile-app-data.md)。

要了解有关使用Adobe Experience Platform SDK在Adobe Campaign Standard中支持的不同移动使用案例的更多信息，请参阅此[页面](https://helpx.adobe.com/cn/campaign/kb/configure-launch-rules-acs-use-cases.html)。

要完成配置，请完成以下步骤：

1. 在Adobe Campaign中，确保您可以访问以下内容：
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL In-App message]**
   * **[!UICONTROL Adobe Places]**

   如果没有，请联系您的客户团队。

1. 检查您的用户是否在Adobe Campaign Standard和Experience Platform Launch中拥有必要的权限。
   * 在Adobe Campaign Standard中，确保IMS用户是标准用户和管理员产品配置文件的一部分。 此步骤允许用户登录Adobe Campaign Standard，导航到Experience PlatformSDK移动设备应用程序页面，然后查看您在Experience Platform Launch中创建的移动设备应用程序属性。

   * 在Experience Platform Launch中，确保您的IMS用户是Experience Platform Launch产品配置文件的一部分。
此步骤允许用户登录以Experience Platform Launch创建和查看属性。 有关Experience Platform Launch中产品配置文件的更多信息，请参阅创建产品配置文件。 在产品配置文件中，不应对公司或资产设置任何权限，但用户仍应能够登录。

   要完成其他任务（如安装扩展、发布应用程序、配置环境等），您需要在产品配置文件中设置权限。

1. 在Experience Platform Launch中，创建&#x200B;**[!UICONTROL Mobile property]**。 有关更多信息，请参阅[设置移动属性](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)。

1. 在Experience Platform Launch中，单击&#x200B;**[!UICONTROL Extensions]**&#x200B;选项卡，转到&#x200B;**[!UICONTROL Catalog]**，然后搜索&#x200B;**[!UICONTROL Adobe Campaign Standard]**&#x200B;扩展。 有关更多信息，请参阅[Adobe Campaign Standard](Https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)。

1. 要支持Campaign Standard中的位置用例，请安装&#x200B;**[!UICONTROL Places]**&#x200B;扩展和&#x200B;**[!UICONTROL Places Monitor]**&#x200B;扩展。
   * 在Experience Platform Launch中安装&#x200B;**[!UICONTROL Places]**&#x200B;扩展。 请参见此[页面](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-extension/places-extension.html)。
   * 在Experience Platform Launch中安装&#x200B;**[!UICONTROL Places Monitor]**&#x200B;扩展。 请参见此[页面](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html)

1. 在 Adobe Campaign Standard 中，配置您在 Experience Platform Launch 中创建的移动属性。请参阅[在Adobe Campaign中设置Adobe Experience Platform Launch应用程序](../../administration/using/configuring-a-mobile-application.md#set-up-campaign)。

1. 将特定于渠道的配置添加到您的移动应用设置中。有关更多信息，请参阅 [Adobe Campaign 中特定于渠道的应用程序配置](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)。

1. 如果需要，您可以删除Experience Platform Launch资产。
有关更多信息，请参阅[删除Experience Platform Launch应用程序](../../administration/using/configuring-a-mobile-application.md#delete-app)。

## 从Launch技术工作流同步移动设备应用程序AEPSDK {#aepsdk-workflow}

在Experience Platform Launch中创建和配置移动资产后，**[!UICONTROL Sync Mobile app AEPSDK from Launch]**&#x200B;技术工作流现在将同步在Adobe Campaign Standard中导入的AdobeLaunch移动资产。

默认情况下，技术工作流每15分钟启动一次。 如果需要，可以手动重新启动：

1. 在Adobe Campaign Standard的高级菜单中，选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**。
1. 打开&#x200B;**[!UICONTROL Sync Mobile app AEPSDK from Launch (syncWithLaunch)]**&#x200B;工作流。

   ![](assets/launch_10.png)

1. 单击&#x200B;**[!UICONTROL Scheduler]**&#x200B;活动。

1. 选择 **[!UICONTROL Immediate execution]**。

   ![](assets/launch_11.png)

您的工作流现在将重新启动并同步在Adobe Campaign Standard中导入的AdobeLaunch移动资产。

## 在Adobe Campaign中设置Adobe Experience Platform Launch应用程序 {#set-up-campaign}

要在Campaign中使用Experience Platform Launch移动属性，您还必须在Adobe Campaign中配置此属性。 在Adobe Campaign中，确保IMS用户是标准用户和管理员产品配置文件的一部分。

您必须等待技术工作流运行并将Launch移动资产同步到Adobe Campaign。 然后，您可以在Adobe Campaign中对其进行配置。

有关从Launch技术工作流同步移动设备应用程序AEPSDK的更多信息，请参阅此[部分](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow)。

>[!NOTE]
>
>默认情况下，将组织单位设置为“全部”的管理员可以编辑移动应用程序。

1. 从高级菜单中，选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**。

   ![](assets/launch.png)

1. 选择您在Experience Platform Launch中创建的移动设备应用程序。
其**[!UICONTROL Property Status]**&#x200B;应为&#x200B;**[!UICONTROL Ready to configure]**。

   >[!NOTE]
   >
   >默认情况下，要检索在Launch中创建的移动Adobe应用程序列表，Campaign Standard会使用NmsServer_URL选项中定义的值来查找匹配的属性。
   >
   >在某些情况下，移动应用程序的Campaign端点可能与NmsServer_URL中定义的端点不同。 在这种情况下，在Launch_URL_Campaign选项中定义端点。 Campaign将使用此选项中的值在Launch中查找匹配的属性Adobe。

   ![](assets/launch_4.png)

1. 您可以在&#x200B;**[!UICONTROL Access Authorization]**&#x200B;部分下更改移动应用程序的组织单位，以将此移动应用程序的访问权限限制为特定的组织单位。 有关详细信息，请参见此页面。

   在此，管理员可以通过从下拉列表中选择子组织单位来分配子组织单位。

   ![](assets/launch_12.png)

1. 要在Campaign和Experience Platform Launch之间建立连接，请单击&#x200B;**[!UICONTROL Save]**。

1. 确认移动设备应用程序的状态已从&#x200B;**[!UICONTROL Ready to Configure]**&#x200B;更改为&#x200B;**[!UICONTROL Configured]**。

   当Experience Platform Launch营销活动扩展显示密钥已成功设置时，您还可以验证属性是否已在Campaign中成功设置。

   ![](assets/launch_5.png)

1. 要使此配置生效，需要以Experience Platform Launch发布更改。

   有关更多信息，请参阅[发布配置](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-configuration)。

## Adobe Campaign中特定于渠道的应用程序配置 {#channel-specific-config}

您的移动应用程序现已准备就绪，可在Campaign中用于推送通知或应用程序内投放。 现在，如果需要，您可以进一步配置，以创建将触发应用程序内消息和/或上传推送证书的事件。

1. 从高级菜单中，选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**。

1. 选择您在Experience Platform Launch中创建和配置的移动应用程序。

1. 在&#x200B;**[!UICONTROL Mobile application properties]**&#x200B;选项卡上，您可以开始添加移动设备应用程序中可用于应用程序内消息的事件。

1. 要配置事件，请单击&#x200B;**[!UICONTROL Create Element]**。

   ![](assets/launch_6.png)

1. 键入名称和描述。

   ![](assets/launch_7.png)

1. 单击 **[!UICONTROL Add]**。

   现在，当您创建应用程序内消息时，“触发器”选项卡上会显示您的事件。 有关更多信息，请参阅[准备和发送应用程序内消息](../../channels/using/preparing-and-sending-an-in-app-message.md)。

1. 在移动设备应用程序仪表板的&#x200B;**[!UICONTROL Device-specific settings]**&#x200B;部分中，针对每个设备提供应用程序详细信息，包括iOS证书和Android服务器密钥。

   上传证书后，系统会显示一条消息，通知您上传成功，并显示证书的过期日期。

   >[!NOTE]
   >
   >在Adobe Campaign Standard中成功添加证书后，您将无法再重新更改设置，因为只能向MCPNS应用程序添加一个APNS平台（生产或沙盒）。

   ![](assets/launch_8.png)

1. 单击&#x200B;**[!UICONTROL Mobile application subscribers]**&#x200B;选项卡可查看订阅者列表以及有关这些订阅者的其他信息，例如，他们是否退出了通知。

## 删除Adobe Experience Platform Launch应用程序 {#delete-app}

删除Experience Platform Launch应用程序时，无法撤销。

>[!CAUTION]
>
>删除Experience Platform Launch应用程序时，无法撤销。

要删除Experience Platform Launch应用程序，请完成[删除移动属性](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#deleting-mobile-properties-in-experience-platform-launch)中的步骤。

删除应用程序后，在Adobe Campaign中，验证应用程序的资产状态是否已在Launch中正确更新为“已删除”。

通过在Adobe Campaign中单击您的应用程序，您可以选择通过单击从Campaign中删除，从Adobe Campaign中完全删除此应用程序。

![](assets/launch_9.png)
