---
title: SDK v4移动应用程序迁移到Adobe Experience Platform SDK
description: 了解如何将移动应用程序从SDK v4迁移到Adobe Experience Platform SDK
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: eb7a209e-069e-4068-966d-05344bd838c7
source-git-commit: 620ae1adc6f804e90c10daeb5fa4df42ce106885
workflow-type: tm+mt
source-wordcount: '1237'
ht-degree: 1%

---

# 如何将移动应用程序从 SDK v4 迁移到 Adobe Experience Platform SDK {#sdkv4-migration}


截至2021年8月31日，已终止对Adobe Experience Platform Mobile版本4 SDK的支持。 如果您仍在使用此旧版SDK，则必须在2024年6月底之前使用Adobe Experience Platform SDK **更新您的实施**。 请参阅本文以了解如何迁移到AdobeExperience Platform SDK。

>[!IMPORTANT]
>
> 在开始将SDK V4移动应用程序迁移到Adobe Experience Platform SDK之前，请仔细阅读文档。

## 关于SDK V4迁移

Adobe Campaign Standard使用SDK V4处理移动应用程序作为单独的应用程序，而不是使用Adobe Experience Platform SDK的应用程序。

将AdobeSDK版本从v4升级到Adobe Experience Platform后，移动应用程序需要继续使用现有的应用程序订阅者数据和营销活动：因此需要迁移。

>[!NOTE]
>
> 本页记录了SDK v4移动应用程序迁移到新创建的Adobe Experience Platform SDK应用程序的过程。 您的SDK v4移动应用程序将不会与具有&#x200B;**[!UICONTROL Configured]** **[!UICONTROL Property status]**&#x200B;的Adobe Experience Platform SDK移动应用程序合并。

| 迁移后不会更改的内容 |
|:-:|
| 使用迁移的SDK V4应用程序对现有投放和营销活动没有影响。 |
| 移动应用程序的名称将保持不变。 |
| 将保留iOS和Android的平台凭据。 |
| 将保留应用程序的所有订阅者及其数据。 |
| 现有SDK v4移动应用程序将继续向Adobe Campaign Standard发送数据（PII数据、订阅者和令牌信息）。 |
| 移动应用程序的&#x200B;**[!UICONTROL Organizational unit]**&#x200B;将保持不变。 |

| 迁移后有何变化 |
|:-:|
| 移动应用程序将在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**&#x200B;中可用。 在迁移之前，它在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**&#x200B;中可用。 |
| 应用程序的&#x200B;**[!UICONTROL Collect PII Endpoint]**&#x200B;将更改。 较旧的&#x200B;**[!UICONTROL Collect PII Endpoint]**&#x200B;将继续工作，发送的数据不会丢失。 |
| 应用程序将绑定到标记&#x200B;**[!UICONTROL Mobile Property]**。 它将作为新创建的移动应用程序处理。 |
| 迁移中使用的原始Adobe Experience Platform SDK应用程序将不会作为单独的应用程序存在。 只有迁移的SDK v4应用程序可用。 |

## 将您的移动应用程序从SDK v4迁移到Adobe Experience Platform SDK {#how-to-migrate}

在迁移之前，您应该考虑以下建议：

* 迁移过程不可逆。
* 您不应同时运行多个应用程序的迁移。 您还应确保同一应用程序的迁移不会同时由多个窗口触发。
* 在迁移之前，请确保为您分配了要迁移的移动应用程序以及用于迁移的Adobe Experience Platform应用程序的&#x200B;**[!UICONTROL Organizational unit]**。
* 迁移后，该应用程序将变为Adobe Experience Platform SDK应用程序。 其更改将链接到其相应的标记&#x200B;**[!UICONTROL Mobile Property]**。

1. 在数据收集UI中创建新的&#x200B;**[!UICONTROL Mobile property]**。 有关此内容的更多信息，请参阅[文档](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/)。

1. 在Adobe Campaign Standard中，从高级菜单中选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**，然后打开&#x200B;**[!UICONTROL syncWithLaunch]**&#x200B;工作流。 检查工作流是否已结束且未出现错误。

1. 工作流完成后，从&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**&#x200B;菜单中，检查移动设备应用程序在Adobe Campaign Standard中是否可用以及是否处于&#x200B;**[!UICONTROL Ready to Configure]**&#x200B;状态。

   ![](assets/aep_v4_2.png)

1. 在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**&#x200B;中，选择要迁移的SDK V4应用程序。

1. 选择 **[!UICONTROL Mobile application migration to AEP SDK]** 选项卡。

   ![](assets/aep_v4_3.png)

1. 从&#x200B;**[!UICONTROL Select AEP SDK mobile application to merge current application with]**&#x200B;下拉列表中，选择之前创建的Adobe Experience Platform SDK移动应用程序。

1. 单击 **[!UICONTROL Migrate]**。

   ![](assets/aep_v4_4.png)

1. 从&#x200B;**[!UICONTROL Migration application]**&#x200B;窗口，单击&#x200B;**[!UICONTROL Ok]**。

   ![](assets/aep_v4_5.png)

1. 出现成功完成窗口，单击&#x200B;**[!UICONTROL Go to Adobe Experience Platform SDK Channel list]**。

1. 在Adobe Experience Platform SDK渠道列表页面中，检查以前的V4移动应用程序是否设置为&#x200B;**[!UICONTROL Ready To Configure]**。

1. 选择您的移动应用程序，然后单击&#x200B;**[!UICONTROL Save]**&#x200B;以完成迁移。

在此迁移后，由移动应用程序的V4版本收集的订阅者和由移动应用程序的AEP版本收集的新订阅者将在迁移的应用程序中可用。

为了区分这两种不同类型的订阅者，例如，在扩展自定义资源&#x200B;**[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**&#x200B;时可以添加&#x200B;**[!UICONTROL Text]**&#x200B;类型的新自定义字段，例如`sdkversion`或`appVersion`。 有关如何扩展自定义资源的更多信息，请参阅此[页面](../../developing/using/creating-or-extending-the-resource.md)。
然后，您需要配置关联的标记**[!UICONTROL Mobile property]**&#x200B;以在“收集PII”调用中发送此自定义字段值，并相应地更改您的移动应用程序配置。

## 常见问题解答 {#faq}

### 问：在SDK v4移动应用程序中，“将移动应用程序迁移到Adobe Experience Platform SDK”选项卡不可见。 {#tab-not-visible}

答：从高级菜单&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**&#x200B;中，检查&#x200B;**[!UICONTROL Enable migration of mobile app from SDK v4 to Adobe Experience Platform SDK option]**&#x200B;选项的值。 它应设置为1并默认启用。 管理员可能已手动禁用它。

![](assets/aep_v4_1.png)

### 问：在迁移到Adobe Experience Platform SDK的移动应用程序选项卡中，会显示消息“无数据” 。 {#no-data}

答：列表中只显示您的&#x200B;**[!UICONTROL Organizational unit]**&#x200B;的合格应用程序。 请确保您拥有用于迁移的正确Adobe Experience Platform应用程序。 Adobe Experience Platform应用程序的&#x200B;**[!UICONTROL Property Status]**&#x200B;应设置为&#x200B;**[!UICONTROL Ready to Configure]**，**[!UICONTROL Mobile app migration status]**&#x200B;应设置为&#x200B;**[!UICONTROL Not Migrated]**。

![](assets/aep_v4_6.png)

### 问：为何无法使用状态为“已配置”属性的Adobe Experience Platform SDK应用程序进行迁移？ {#property-status}

答：迁移过程会保留SDK v4订阅者和属性。 它仅保留Adobe Experience Platform SDK应用程序中与标记相关的信息。 Adobe Experience Platform SDK应用程序中的订阅者和其他数据将丢失。 为避免任何数据丢失，只有具有&#x200B;**[!UICONTROL Ready to Configure]** **[!UICONTROL Property Status]**&#x200B;的Adobe Experience Platform SDK应用程序才有资格迁移。

### 问：迁移后，我可以在何处找到以前的SDK v4移动应用程序？ {#v4-app-not-visible}

答：迁移后的移动设备应用程序将从高级菜单&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**&#x200B;中可见。

### 问：迁移后，我可以在哪里找到新创建的Adobe Experience Platform SDK应用程序？ {#aep-not-visible}

答：用于迁移的新创建的Adobe Experience Platform SDK应用程序将不会作为单独的应用程序存在。 只有迁移的SDK v4应用程序可用。

### 问：如果SDK v4移动应用程序组织单位设置为（组织单位ALL的子项），并且Adobe Experience Platform SDK设置为“全部”。 如何迁移移动应用程序？ {#v4-org-unit}

答： **[!UICONTROL Organizational unit]** ALL的管理员将有权管理这两个移动设备应用程序，并将负责迁移。

### 问：如果SDK v4移动应用程序组织单位设置为A，Adobe Experience Platform SDK应用程序设置为B（组织单位A的同级）。 如何迁移移动应用程序？ {#aep-org-unit}

答：Adobe Experience Platform SDK应用程序是同级&#x200B;**[!UICONTROL Organizational unit]**&#x200B;的资源，因此移动应用程序对&#x200B;**[!UICONTROL Organizational unit]** A的用户不可见。**[!UICONTROL Organizational unit]** ALL的管理员可以使用移动应用程序，但我们不建议这些管理员迁移移动应用程序。
在这种情况下，您应将移动应用程序移到同一**[!UICONTROL Organizational unit]**&#x200B;中或带有父链接的&#x200B;**[!UICONTROL Organizational unit]**中。
有关**[!UICONTROL Organizational unit]**&#x200B;的详细信息，请参阅此[部分](../../administration/using/organizational-units.md)。

### 问：在Adobe Experience Platform SDK移动应用程序（从v4移动应用程序迁移）页面的“推送渠道设置”下拉列表下，不会显示Android密钥或iOS证书的上传日期/名称等信息 {#no-information-v5}

答：创建SDK V4移动应用程序时，系统不会存储此信息。 在将SDK V4移动应用程序迁移到Adobe Experience Platform SDK移动应用程序时，迁移后的移动应用程序也将不包含此类信息。 用户一旦上传新的iOS证书或Android密钥，该密钥或证书的不同详细信息将立即在&#x200B;**[!UICONTROL Push channel settings]**&#x200B;下拉菜单下正确存储和显示。
