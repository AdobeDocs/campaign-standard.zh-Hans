---
title: SDK v4移动应用程序迁移到Adobe Experience Platform SDK
description: 了解如何将移动应用程序从SDK v4迁移到Adobe Experience Platform SDK
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: eb7a209e-069e-4068-966d-05344bd838c7
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '1193'
ht-degree: 1%

---

# 如何将移动应用程序从 SDK v4 迁移到 Adobe Experience Platform SDK {#sdkv4-migration}

>[!IMPORTANT]
>
> 迁移过程不可逆。
>
> 在开始将SDK V4移动应用程序迁移到Adobe Experience Platform SDK之前，请仔细阅读文档。

## 关于SDK V4迁移

Adobe Campaign Standard使用SDK V4处理移动应用程序，作为与Adobe Experience Platform SDK分开的应用程序。
将AdobeSDK版本从v4升级到Adobe Experience Platform后，移动应用程序需要继续使用现有的应用程序订阅者数据和营销活动：因此需要迁移。

>[!NOTE]
>
> 本页记录了SDK v4移动应用程序迁移到新创建的Adobe Experience Platform SDK应用程序的过程。 您的SDK v4移动应用程序不会与具有的Adobe Experience Platform SDK移动应用程序合并 **[!UICONTROL Configured]** **[!UICONTROL Property status]**.

| 迁移后不会更改的内容 |
|:-:|
| 使用迁移的SDK V4应用程序对现有投放和营销活动没有影响。 |
| 移动应用程序的名称将保持不变。 |
| 将保留iOS和Android的平台凭据。 |
| 将保留应用程序的所有订阅者及其数据。 |
| 现有的SDK v4移动应用程序将继续向Adobe Campaign Standard发送数据（PII数据、订阅者和令牌信息）。 |
| 此 **[!UICONTROL Organizational unit]** 移动应用程序的ID将保持不变。 |

| 迁移后有何变化 |
|:-:|
| 移动设备应用程序将在以下位置提供： **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**. 在迁移之前，它在 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**. |
| 此 **[!UICONTROL Collect PII Endpoint]** 应用程序的URL将更改。 较旧 **[!UICONTROL Collect PII Endpoint]** 将继续工作，发送的数据不会丢失。 |
| 应用程序将绑定到标记 **[!UICONTROL Mobile Property]**. 它将作为新创建的移动应用程序处理。 |
| 迁移中使用的原始Adobe Experience Platform SDK应用程序将不会作为单独的应用程序存在。 只有迁移的SDK v4应用程序可用。 |

## 将您的移动应用程序从SDK v4迁移到Adobe Experience Platform SDK {#how-to-migrate}

在迁移之前，您应该考虑以下建议：

* 迁移过程不可逆。
* 您不应同时运行多个应用程序的迁移。 您还应确保同一应用程序的迁移不会同时由多个窗口触发。
* 在迁移之前，请确保为您分配了 **[!UICONTROL Organizational unit]** 要迁移的移动应用程序，以及要用于迁移的Adobe Experience Platform应用程序。
* 迁移后，该应用程序将成为Adobe Experience Platform SDK应用程序。 其更改将链接到其相应的标记 **[!UICONTROL Mobile Property]**.

1. 新建 **[!UICONTROL Mobile property]** 在数据收集UI中。 有关详情，请参阅 [文档](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/).

1. 在Adobe Campaign Standard中，从高级菜单中，选择 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]** 然后打开 **[!UICONTROL syncWithLaunch]** 工作流。 检查工作流是否已结束且没有错误。

1. 工作流完成后，从 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]** 菜单，检查移动设备应用程序在Adobe Campaign Standard中是否可用以及是否位于 **[!UICONTROL Ready to Configure]** 省/州。

   ![](assets/aep_v4_2.png)

1. In **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**&#x200B;中，选择要迁移的SDK V4应用程序。

1. 选择 **[!UICONTROL Mobile application migration to AEP SDK]** 选项卡。

   ![](assets/aep_v4_3.png)

1. 从 **[!UICONTROL Select AEP SDK mobile application to merge current application with]** 从下拉列表中，选择之前创建的Adobe Experience Platform SDK移动应用程序。

1. 单击 **[!UICONTROL Migrate]**。

   ![](assets/aep_v4_4.png)

1. 从 **[!UICONTROL Migration application]** 窗口，单击 **[!UICONTROL Ok]**.

   ![](assets/aep_v4_5.png)

1. 成功完成窗口出现，单击 **[!UICONTROL Go to Adobe Experience Platform SDK Channel list]**.

1. 在Adobe Experience Platform SDK渠道列表页面中，检查是否将以前的V4移动应用程序设置为 **[!UICONTROL Ready To Configure]**.

1. 选择您的移动应用程序，然后单击 **[!UICONTROL Save]** 以完成迁移。

在此迁移后，由移动应用程序的V4版本收集的订阅者和由移动应用程序的AEP版本收集的新订阅者将在迁移的应用程序中可用。

要区分这两种不同类型的订阅者，您可以添加新的自定义字段 **[!UICONTROL Text]** 扩展自定义资源时键入 **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** 作为 `sdkversion` 或 `appVersion` 例如。 有关如何扩展自定义资源的更多信息，请参阅此 [页面](../../developing/using/creating-or-extending-the-resource.md).
然后，您需要配置关联的标记 **[!UICONTROL Mobile property]** 在收集PII调用中发送此自定义字段值，并相应地更改您的移动应用程序配置。

## 常见问题解答 {#faq}

### 问：在SDK v4移动应用程序中，“将移动应用程序迁移到Adobe Experience Platform SDK”选项卡不可见。 {#tab-not-visible}

答：从高级菜单中 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**，检查 **[!UICONTROL Enable migration of mobile app from SDK v4 to Adobe Experience Platform SDK option]** 选项。 默认情况下应将其设置为1并启用。 管理员可能已手动禁用它。

![](assets/aep_v4_1.png)

### 问：在将移动应用程序迁移到Adobe Experience Platform SDK选项卡中，会显示消息“无数据”。 {#no-data}

答：只有符合条件的申请，才能申请 **[!UICONTROL Organizational unit]** 将显示在列表中。 请确保您拥有适用于迁移的正确Adobe Experience Platform应用程序。 此 **[!UICONTROL Property Status]** Adobe Experience Platform的URL应设置为 **[!UICONTROL Ready to Configure]**  和 **[!UICONTROL Mobile app migration status]** 设置为 **[!UICONTROL Not Migrated]**.

![](assets/aep_v4_6.png)

### 问：为何无法使用“已配置的属性状态”的Adobe Experience Platform SDK应用程序进行迁移？ {#property-status}

答：迁移过程会保留SDK v4订阅者和属性。 它仅保留Adobe Experience Platform SDK应用程序中与标记相关的信息。 Adobe Experience Platform SDK应用程序中的订阅者和其他数据将丢失。 为避免任何数据丢失，请仅将Adobe Experience Platform SDK应用程序与 **[!UICONTROL Ready to Configure]** **[!UICONTROL Property Status]** 符合迁移条件。

### 问：迁移后，可在何处找到以前的SDK v4移动应用程序？ {#v4-app-not-visible}

答：迁移后的移动应用程序将从高级菜单中可见 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**.

### 问：迁移后，我可以在何处找到新创建的Adobe Experience Platform SDK应用程序？ {#aep-not-visible}

答：用于迁移的新创建的Adobe Experience Platform SDK应用程序将不会作为单独的应用程序存在。 只有迁移的SDK v4应用程序可用。

### 问：如果SDK v4移动应用程序组织单位设置为A（组织单位ALL的子项），并且Adobe Experience Platform SDK设置为ALL。 如何迁移移动应用程序？ {#v4-org-unit}

答：的管理员 **[!UICONTROL Organizational unit]** 所有人都将有权管理这两个移动应用程序，并将负责迁移。

### 问：如果将SDK v4移动应用程序组织单位设置为A，并将Adobe Experience Platform SDK应用程序设置为B（组织单位A的同级）。 如何迁移移动应用程序？ {#aep-org-unit}

答：Adobe Experience Platform SDK应用程序是同级资源的资源 **[!UICONTROL Organizational unit]**，则移动应用程序对的用户不可见 **[!UICONTROL Organizational unit]** A.移动设备应用程序将可供以下管理员使用： **[!UICONTROL Organizational unit]** 所有这些管理员，但我们不建议这些管理员迁移移动应用程序。
在这种情况下，您应该将移动设备应用程序移动到同一个 **[!UICONTROL Organizational unit]** 或在 **[!UICONTROL Organizational unit]** 具有父链接。
有关的详细信息 **[!UICONTROL Organizational unit]**，请参考此 [部分](../../administration/using/organizational-units.md).

### 问：在Adobe Experience Platform SDK移动应用程序（从v4移动应用程序迁移）页面的“推送渠道设置”下拉列表下，不会显示Android密钥或iOS证书的任何信息，例如上传日期/名称 {#no-information-v5}

答：在创建SDK V4移动应用程序时，系统不会存储此信息。 在将SDK V4移动应用程序迁移到Adobe Experience Platform SDK移动应用程序时，迁移后的移动应用程序也将不包含此类信息。 一旦用户将上传新的iOS证书或Android密钥，该密钥或证书的不同详细信息将正确存储和显示在下 **[!UICONTROL Push channel settings]** 下拉菜单。
