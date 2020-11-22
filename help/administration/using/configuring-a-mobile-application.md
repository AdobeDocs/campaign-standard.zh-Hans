---
solution: Campaign Standard
product: campaign
title: 配置移动应用程序
description: 了解如何配置Adobe Campaign以使用SDK V4或Experience PlatformSDK发送推送通知或应用程序内消息。
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1283'
ht-degree: 7%

---


# 配置移动应用程序{#configuring-a-mobile-application}

## Configuring a mobile application using Adobe Experience Platform SDKs {#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
>推送通知和应用程序内实施必须由专家用户执行。 如果需要协助，请与您的 Adobe 客户经理或专业服务合作伙伴联系。

要使用Experience PlatformSDK应用程序发送推送通知和应用程序内消息，必须在Adobe Experience PlatformExperience PlatformExperience Platform Launch中设置移动应用程序并在Adobe Campaign中配置。

有关已弃用功能移动版本4 SDK的更多信息，请参阅 [本页](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4-deprecated.html)。

设置移动应用程序后，您可以检索其收集的PII数据，以从数据库创建或更新用户档案。 有关此内容的详细信息，请参阅此部分： [创建和更新基于移动应用程序用户档案的信息](../../channels/using/updating-profile-with-mobile-app-data.md)。

要进一步了解Adobe Campaign Standard使用Adobe Experience PlatformSDK支持的不同移动用例，请参阅本 [页](https://helpx.adobe.com/cn/campaign/kb/configure-launch-rules-acs-use-cases.html)。

要完成配置，请完成以下步骤：

1. 在Adobe Campaign中，确保您可以访问以下内容：
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL In-App message]**
   * **[!UICONTROL Adobe Places]**

   如果没有，请联系您的帐户团队。

1. 检查您的用户是否在Adobe Campaign Standard和Experience Platform Launch拥有必要的权限。
   * 在Adobe Campaign Standard，确保IMS用户是标准用户和管理员产品用户档案的一部分。 此步骤允许用户登录Adobe Campaign Standard，导航到Experience PlatformSDK移动应用程序页面，并视图您在Experience Platform Launch中创建的移动应用程序属性。

   * 在Experience Platform Launch中，确保IMS用户是Experience Platform Launch产品用户档案的一部分。
此步骤允许用户登录Experience Platform Launch以创建和视图属性。 有关Experience Platform Launch中产品用户档案的更多信息，请参阅创建产品用户档案。 在产品用户档案中，公司或属性上不应设置任何权限，但用户仍应能够登录。

   要完成其他任务，如安装扩展、发布应用程序、配置环境等，您需要在产品用户档案中设置权限。

1. 在Experience Platform Launch中，创建 **[!UICONTROL Mobile property]**。 有关更多信息，请参阅[设置移动属性](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)。

1. 在Experience Platform Launch中，单 **[!UICONTROL Extensions]** 击选项卡，转 **[!UICONTROL Catalog]**&#x200B;到并搜索扩 **[!UICONTROL Adobe Campaign Standard]** 展。 有关详细信息，请参阅 [Adobe Campaign Standard](Https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)。

1. 要在Campaign Standard中支持位置用例，请安 **[!UICONTROL Places]** 装扩展和 **[!UICONTROL Places Monitor]** 扩展。
   * 以Experience Platform Launch **[!UICONTROL Places]** 安装扩展。 Refer to this [page](https://docs.adobe.com/content/help/zh-Hans/places/using/places-ext-aep-sdks/places-extension/places-extension.html).
   * 以Experience Platform Launch **[!UICONTROL Places Monitor]** 安装扩展。 Refer to this [page](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html)

1. 在 Adobe Campaign Standard 中，配置您在 Experience Platform Launch 中创建的移动属性。请参阅在 [Adobe Campaign中设置您的Adobe Experience Platform Launch应用程序](../../administration/using/configuring-a-mobile-application.md#set-up-campaign)。

1. 将特定于渠道的配置添加到您的移动应用设置中。有关更多信息，请参阅 [Adobe Campaign 中特定于渠道的应用程序配置](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)。

1. 如果需要，您可以删除Experience Platform Launch属性。
有关详细信息，请参 [阅删除Experience Platform Launch应用程序](../../administration/using/configuring-a-mobile-application.md#delete-app)。

## 从Launch技术工作流程同步移动应用程序AEPSDK {#aepsdk-workflow}

在Experience Platform Launch中创建和配置移动属性后，技 **[!UICONTROL Sync Mobile app AEPSDK from Launch]** 术工作流现在将同步在Adobe Campaign Standard导入的Adobe启动移动属性。

默认情况下，技术工作流每15分钟开始一次。 如果需要，可以手动重新启动它：

1. 在Adobe Campaign Standard，从高级菜单中，选择 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**。
1. 打开工 **[!UICONTROL Sync Mobile app AEPSDK from Launch (syncWithLaunch)]** 作流。

   ![](assets/launch_10.png)

1. Click on the **[!UICONTROL Scheduler]** activity.

1. 选择 **[!UICONTROL Immediate execution]**。

   ![](assets/launch_11.png)

您的工作流现在将重新启动并同步在Adobe Campaign Standard导入的Adobe启动移动属性。

## 在Adobe Campaign中设置您的Adobe Experience Platform Launch应用程序 {#set-up-campaign}

要在活动中使用Experience Platform Launch移动属性，您还需要在Adobe Campaign中配置此属性。 在Adobe Campaign中，确保IMS用户是标准用户和管理员产品用户档案的一部分。

您需要等待技术工作流程运行，并将Launch移动属性同步到Adobe Campaign。 然后，您可以在Adobe Campaign中配置它。

有关从Launch中同步移动应用程序AEPSDK的更多信息，请参阅此 [部分](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow)。

>[!NOTE]
>
>默认情况下，将组织单元设置为“全部”的管理员可以编辑移动应用程序。

1. 从高级菜单中，选择 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**。

   ![](assets/launch.png)

1. 选择您在Experience Platform Launch中创建的手机应用程序。
它 **[!UICONTROL Property Status]** 应该 **[!UICONTROL Ready to configure]**&#x200B;是。

   >[!NOTE]
   >
   >默认情况下，要检索在Adobe启动中创建的移动应用程序列表,Campaign Standard使用NmsServer_URL选项中定义的值来查找匹配的属性。
   >
   >在某些情况下，移动应用程序的活动端点可能与NmsServer_URL中定义的端点不同。 在这种情况下，在Launch_URL_活动选项中定义端点。 活动将使用此选项中的值在Adobe启动中查找匹配属性。

   ![](assets/launch_4.png)

1. 您可以在该部分更改移动应用程序的组织单位，以 **[!UICONTROL Access Authorization]** 将对此移动应用程序的访问权限限制为特定的组织单位。 有关详细信息，请参见此页面。

   在此，管理员可以从下拉列表中选择子组织单位来分配这些单位。

   ![](assets/launch_12.png)

1. 要在活动和Experience Platform Launch之间建立连接，请单击 **[!UICONTROL Save]**。

1. 验证移动应用程序的状态是否已从 **[!UICONTROL Ready to Configure]** 更改 **[!UICONTROL Configured]**。

   当Experience Platform Launch活动扩展显示密钥设置成功时，您还可以验证属性是否已在活动中成功设置。

   ![](assets/launch_5.png)

1. 要使此配置生效，需要以Experience Platform Launch发布更改。

   有关详细信息，请参阅 [发布配置](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-configuration)。

## 渠道特定的Adobe Campaign配置 {#channel-specific-config}

现在，您的移动应用程序可用于推送通知活动或应用程序内投放。 现在，如果需要，您可以进一步配置它，以创建将触发您的应用程序内消息和／或上传推送证书的事件。

1. 从高级菜单中，选择 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**。

1. 选择您在Experience Platform Launch中创建和配置的移动应用程序。

1. 在选项 **[!UICONTROL Mobile application properties]** 卡上，您可以开始添加移动应用程序中可用于应用程序内消息的事件。

1. 要配置事件，请单击 **[!UICONTROL Create Element]**。

   ![](assets/launch_6.png)

1. 键入名称和说明。

   ![](assets/launch_7.png)

1. 单击 **[!UICONTROL Add]**.

   现在，在创建应用程序内消息时，“触发器”选项卡上提供了事件。 有关详细信息，请 [参阅准备和发送应用程序内消息](../../channels/using/preparing-and-sending-an-in-app-message.md)。

1. 在移 **[!UICONTROL Device-specific settings]** 动应用程序仪表板的每个设备部分，提供应用程序详细信息，包括iOS证书和Android服务器密钥。

   上传证书后，将显示一条消息，通知您上载成功，并显示证书的过期日期。

   >[!NOTE]
   >
   >在Adobe Campaign Standard成功添加证书后，您将无法再更改回设置，因为只能向MCPNS应用程序添加一个APNS平台（生产平台或沙箱）。

   ![](assets/launch_8.png)

1. 单击该 **[!UICONTROL Mobile application subscribers]** 选项卡可查看订阅者的列表以及有关这些订阅者的其他信息，例如，他们是否选择退出通知。

## 删除您的Adobe Experience Platform Launch应用程序 {#delete-app}

无法删除Experience Platform Launch应用程序。

>[!CAUTION]
>
>无法删除Experience Platform Launch应用程序。

要删除Experience Platform Launch应用程序，请完成删除移动 [属性中的步骤](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#deleting-mobile-properties-in-experience-platform-launch)。

删除应用程序后，在Adobe Campaign中，验证应用程序的“属性”状态是否已正确更新为“在启动项中删除”。

通过在Adobe Campaign中单击应用程序，您可以通过单击从Adobe Campaign中删除来选择从活动中完全删除此应用程序。

![](assets/launch_9.png)
