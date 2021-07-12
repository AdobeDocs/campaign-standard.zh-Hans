---
solution: Campaign Standard
product: campaign
title: 将SDK v4移动应用程序迁移到Adobe Experience Platform SDK
description: 本文档允许您将移动应用程序从SDK v4迁移到Adobe Experience Platform SDK
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: 实例设置
role: Admin
level: Experienced
exl-id: eb7a209e-069e-4068-966d-05344bd838c7
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '1204'
ht-degree: 1%

---

# 如何将移动应用程序从 SDK v4 迁移到 Adobe Experience Platform SDK {#sdkv4-migration}

>[!IMPORTANT]
>
> 迁移过程是不可逆的。
>
> 在开始将SDK V4移动应用程序迁移到Adobe Experience Platform SDK之前，请仔细阅读此文档。

## 关于SDK V4迁移

Adobe Campaign Standard使用SDK V4处理移动应用程序，将其作为与使用Adobe Experience Platform SDK的应用程序分开处理。
将AdobeSDK版本从v4升级到Adobe Experience Platform后，移动设备应用程序需要继续使用现有应用程序订阅者数据和营销活动：因此需要迁移。

>[!NOTE]
>
> 本页记录了如何将SDK v4移动应用程序迁移到新创建的Adobe Experience Platform SDK应用程序。 您的SDK v4移动应用程序不会与&#x200B;**[!UICONTROL Configured]** **[!UICONTROL Property status]**&#x200B;的Adobe Experience Platform SDK移动应用程序合并。

| 迁移后不会更改的内容 |
|:-:|
| 对使用迁移的SDK V4应用程序的现有投放和营销活动没有影响。 |
| 移动应用程序的名称将保持不变。 |
| 将保留iOS和Android的平台凭据。 |
| 应用程序的所有订阅者及其数据都将保留。 |
| 现有的SDK v4移动应用程序将继续向Adobe Campaign Standard发送数据（PII数据、订阅者和令牌信息）。 |
| 移动应用程序的&#x200B;**[!UICONTROL Organizational unit]**&#x200B;将保持不变。 |

| 迁移后将发生哪些更改 |
|:-:|
| 移动设备应用程序将在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**&#x200B;中提供。 在迁移之前，它位于&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**&#x200B;中。 |
| 应用程序的&#x200B;**[!UICONTROL Collect PII Endpoint]**&#x200B;将发生更改。 旧版&#x200B;**[!UICONTROL Collect PII Endpoint]**&#x200B;将继续工作，发送的数据不会丢失。 |
| 应用程序将绑定到Adobe Experience Platform Launch **[!UICONTROL Mobile Property]**。 它将作为新创建的移动应用程序进行处理。 |
| 迁移中使用的原始Adobe Experience Platform SDK应用程序将不作为单独的应用程序存在。 只有迁移的SDK v4应用程序才可用。 |

## 将您的移动应用程序从SDK v4迁移到Adobe Experience Platform SDK {#how-to-migrate}

在迁移之前，您应考虑以下建议：

* 迁移过程是不可逆的。
* 您不应同时运行多个应用程序的迁移。 您还应确保同一应用程序的迁移不会同时被多个窗口触发。
* 在迁移之前，请确保为您分配了要迁移的移动应用程序的&#x200B;**[!UICONTROL Organizational unit]**&#x200B;以及要用于迁移的Adobe Experience Platform应用程序。
* 迁移后，应用程序将成为Adobe Experience Platform SDK应用程序。 其更改将链接到其相应的Launch **[!UICONTROL Mobile Property]**。

1. 在Adobe Experience Platform Launch中创建新的&#x200B;**[!UICONTROL Mobile property]**。 有关此内容的更多信息，请参阅[Adobe Experience Platform Launch文档](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-mobile-property)。

1. 在Adobe Campaign Standard中，从高级菜单中，选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**&#x200B;并打开&#x200B;**[!UICONTROL syncWithLaunch]**&#x200B;工作流。 检查工作流是否已结束且没有错误。

1. 完成工作流后，从&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**&#x200B;菜单中，检查移动应用程序是否在Adobe Campaign Standard中可用，并且处于&#x200B;**[!UICONTROL Ready to Configure]**&#x200B;状态。

   ![](assets/aep_v4_2.png)

1. 在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**&#x200B;中，选择要迁移的SDK V4应用程序。

1. 选择 **[!UICONTROL Mobile application migration to AEP SDK]** 选项卡。

   ![](assets/aep_v4_3.png)

1. 从&#x200B;**[!UICONTROL Select AEP SDK mobile application to merge current application with]**&#x200B;下拉列表中，选择之前创建的Adobe Experience Platform SDK移动应用程序。

1. 单击 **[!UICONTROL Migrate]**。

   ![](assets/aep_v4_4.png)

1. 在&#x200B;**[!UICONTROL Migration application]**&#x200B;窗口中，单击&#x200B;**[!UICONTROL Ok]**。

   ![](assets/aep_v4_5.png)

1. 出现成功完成窗口，单击&#x200B;**[!UICONTROL Go to Adobe Experience Platform SDK Channel list]**。

1. 在Adobe Experience Platform SDK渠道列表页面中，检查您之前的V4移动应用程序是否设置为&#x200B;**[!UICONTROL Ready To Configure]**。

1. 选择您的移动应用程序并单击&#x200B;**[!UICONTROL Save]**&#x200B;以完成迁移。

进行此迁移后，由V4版本的移动设备应用程序收集的订阅者以及由AEP版本的移动设备应用程序收集的新订阅者，将会在迁移的应用程序中可用。

为了区分两种不同类型的订阅者，例如，在将自定义资源&#x200B;**[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**&#x200B;扩展为`sdkversion`或`appVersion`时，可以添加新的类型为&#x200B;**[!UICONTROL Text]**&#x200B;的自定义字段。 有关如何扩展自定义资源的更多信息，请参阅此[page](../../developing/using/creating-or-extending-the-resource.md)。
然后，您需要配置关联的Launch **[!UICONTROL Mobile property]**&#x200B;以在Collect PII调用中发送此自定义字段值，并相应地更改移动应用程序配置。

## 常见问题解答 {#faq}

### 问：在SDK v4移动应用程序中，将移动应用程序迁移到Adobe Experience Platform SDK选项卡时不可见。 {#tab-not-visible}

答：从高级菜单&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**&#x200B;中，检查&#x200B;**[!UICONTROL Enable migration of mobile app from SDK v4 to Adobe Experience Platform SDK option]**&#x200B;选项的值。 该参数应设置为1，并默认启用。 管理员可能已手动禁用它。

![](assets/aep_v4_1.png)

### 问：从将移动应用程序迁移到Adobe Experience Platform SDK选项卡中，会显示消息无数据。 {#no-data}

答：列表中只显示符合&#x200B;**[!UICONTROL Organizational unit]**&#x200B;条件的应用程序。 请确保您具有正确的Adobe Experience Platform迁移应用程序。 您的Adobe Experience Platform应用程序的&#x200B;**[!UICONTROL Property Status]**&#x200B;应设置为&#x200B;**[!UICONTROL Ready to Configure]**,**[!UICONTROL Mobile app migration status]**&#x200B;应设置为&#x200B;**[!UICONTROL Not Migrated]**。

![](assets/aep_v4_6.png)

### 问：为何无法使用已配置资产状态的Adobe Experience Platform SDK应用程序进行迁移？ {#property-status}

答：迁移过程会保留SDK v4订阅者和属性。 它只会从Adobe Experience Platform SDK应用程序中保留与Launch相关的信息。 来自Adobe Experience Platform SDK应用程序的订阅者和其他数据将丢失。 为避免任何数据丢失，只有具有&#x200B;**[!UICONTROL Ready to Configure]** **[!UICONTROL Property Status]**&#x200B;的Adobe Experience Platform SDK应用程序才有资格进行迁移。

### 问：迁移后，我在哪里可以找到之前的SDK v4移动应用程序？ {#v4-app-not-visible}

答：迁移后的移动应用程序将从高级菜单&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**&#x200B;中看到。

### 问：迁移后，在哪里可以找到新创建的Adobe Experience Platform SDK应用程序？ {#aep-not-visible}

答：新创建的用于迁移的Adobe Experience Platform SDK应用程序将不作为单独的应用程序存在。 只有迁移的SDK v4应用程序才可用。

### 问：如果SDK v4移动应用程序组织单位设置为A（组织单位ALL的子代），而Adobe Experience Platform SDK设置为ALL。 如何迁移移动应用程序？ {#v4-org-unit}

答：**[!UICONTROL Organizational unit]** ALL的管理员将有权管理两个移动应用程序，并负责迁移。

### 问：如果SDK v4移动设备应用程序组织单位设置为A，而Adobe Experience Platform SDK应用程序设置为B（组织单位A的同级）。 如何迁移移动应用程序？ {#aep-org-unit}

答：Adobe Experience Platform SDK应用程序是同级&#x200B;**[!UICONTROL Organizational unit]**&#x200B;的资产，则&#x200B;**[!UICONTROL Organizational unit]** A的用户将看不到该移动应用程序。该移动应用程序将可供&#x200B;**[!UICONTROL Organizational unit]** ALL的管理员使用，但我们不建议这些管理员迁移移动应用程序。
在这种情况下，您应将移动设备应用程序移动到同一个**[!UICONTROL Organizational unit]**&#x200B;或具有父链接的&#x200B;**[!UICONTROL Organizational unit]**中。
有关**[!UICONTROL Organizational unit]**&#x200B;的详细信息，请参阅此[部分](../../administration/using/organizational-units.md)。

### 问：从您的Adobe Experience Platform SDK移动应用程序（从v4移动应用程序迁移）页面的推送渠道设置下拉列表下，Android密钥或iOS证书不会显示任何上传日期/名称等信息 {#no-information-v5}

答：创建SDK V4移动应用程序后，系统不会存储此信息。 将SDK V4移动应用程序迁移到Adobe Experience Platform SDK移动应用程序时，迁移的移动应用程序也将没有此类信息。 用户一旦上传新的iOS证书或Android密钥，该密钥或证书的不同详细信息就会存储并正确显示在&#x200B;**[!UICONTROL Push channel settings]**&#x200B;下拉列表下。
