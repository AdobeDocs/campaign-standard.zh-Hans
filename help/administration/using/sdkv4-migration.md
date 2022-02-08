---
title: 将SDK v4移动应用程序迁移到Adobe Experience Platform SDK
description: 了解如何将移动应用程序从SDK v4迁移到Adobe Experience Platform SDK
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: eb7a209e-069e-4068-966d-05344bd838c7
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '1200'
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
> 本页记录了如何将SDK v4移动应用程序迁移到新创建的Adobe Experience Platform SDK应用程序。 您的SDK v4移动应用程序不会与Adobe Experience Platform SDK移动应用程序 **[!UICONTROL Configured]** **[!UICONTROL Property status]**.

| 迁移后不会更改的内容 |
|:-:|
| 对使用迁移的SDK V4应用程序的现有投放和营销活动没有影响。 |
| 移动应用程序的名称将保持不变。 |
| 将保留iOS和Android的平台凭据。 |
| 应用程序的所有订阅者及其数据都将保留。 |
| 现有的SDK v4移动应用程序将继续向Adobe Campaign Standard发送数据（PII数据、订阅者和令牌信息）。 |
| 的 **[!UICONTROL Organizational unit]** 移动应用程序的数量将保持不变。 |

| 迁移后将发生哪些更改 |
|:-:|
| 移动应用程序将在 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**. 在迁移之前，它在 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**. |
| 的 **[!UICONTROL Collect PII Endpoint]** 应用程序的更改。 年长 **[!UICONTROL Collect PII Endpoint]** 将继续工作，发送的数据将不会丢失。 |
| 应用程序将绑定到Adobe Experience Platform Launch **[!UICONTROL Mobile Property]**. 它将作为新创建的移动应用程序进行处理。 |
| 迁移中使用的原始Adobe Experience Platform SDK应用程序将不作为单独的应用程序存在。 只有迁移的SDK v4应用程序才可用。 |

## 将您的移动应用程序从SDK v4迁移到Adobe Experience Platform SDK {#how-to-migrate}

在迁移之前，您应考虑以下建议：

* 迁移过程是不可逆的。
* 您不应同时运行多个应用程序的迁移。 您还应确保同一应用程序的迁移不会同时被多个窗口触发。
* 在迁移之前，请确保为您分配了 **[!UICONTROL Organizational unit]** 要迁移的移动应用程序，以及要用于迁移的Adobe Experience Platform应用程序。
* 迁移后，应用程序将成为Adobe Experience Platform SDK应用程序。 其更改将链接到其相应的Launch **[!UICONTROL Mobile Property]**.

1. 新建 **[!UICONTROL Mobile property]** 在Adobe Experience Platform Launch。 有关此内容的详细信息，请参阅 [Adobe Experience Platform Launch文档](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-mobile-property).

1. 在Adobe Campaign Standard中，从高级菜单中，选择 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]** 打开 **[!UICONTROL syncWithLaunch]** 工作流。 检查工作流是否已结束且没有错误。

1. 工作流完成后，从 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]** ，检查移动应用程序是否在Adobe Campaign Standard中可用，以及是否在 **[!UICONTROL Ready to Configure]** 状态。

   ![](assets/aep_v4_2.png)

1. 在 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**，选择要迁移的SDK V4应用程序。

1. 选择 **[!UICONTROL Mobile application migration to AEP SDK]** 选项卡。

   ![](assets/aep_v4_3.png)

1. 从 **[!UICONTROL Select AEP SDK mobile application to merge current application with]** 下拉列表，选择之前创建的Adobe Experience Platform SDK移动应用程序。

1. 单击 **[!UICONTROL Migrate]**。

   ![](assets/aep_v4_4.png)

1. 从 **[!UICONTROL Migration application]** 窗口，单击 **[!UICONTROL Ok]**.

   ![](assets/aep_v4_5.png)

1. 出现成功完成窗口，单击 **[!UICONTROL Go to Adobe Experience Platform SDK Channel list]**.

1. 从Adobe Experience Platform SDK渠道列表页面中，检查您之前的V4移动应用程序是否设置为 **[!UICONTROL Ready To Configure]**.

1. 选择您的移动应用程序并单击 **[!UICONTROL Save]** 以完成迁移。

进行此迁移后，由V4版本的移动设备应用程序收集的订阅者以及由AEP版本的移动设备应用程序收集的新订阅者，将会在迁移的应用程序中可用。

要区分两种不同类型的订阅者，可以添加新的自定义字段： **[!UICONTROL Text]** 扩展自定义资源时键入 **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** as `sdkversion` 或 `appVersion` 例如。 有关如何扩展自定义资源的更多信息，请参阅此 [页面](../../developing/using/creating-or-extending-the-resource.md).
然后，您将需要配置关联的Launch **[!UICONTROL Mobile property]** 要在Collect PII调用中发送此自定义字段值，请相应地更改移动应用程序配置。

## 常见问题解答 {#faq}

### 问：在SDK v4移动应用程序中，将移动应用程序迁移到Adobe Experience Platform SDK选项卡时不可见。 {#tab-not-visible}

答：从高级菜单 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**，请检查 **[!UICONTROL Enable migration of mobile app from SDK v4 to Adobe Experience Platform SDK option]** 选项。 该参数应设置为1，并默认启用。 管理员可能已手动禁用它。

![](assets/aep_v4_1.png)

### 问：从将移动应用程序迁移到Adobe Experience Platform SDK选项卡中，会显示消息无数据。 {#no-data}

答：仅适用于 **[!UICONTROL Organizational unit]** 中。 请确保您具有正确的Adobe Experience Platform迁移应用程序。 的 **[!UICONTROL Property Status]** 的Adobe Experience Platform应用程序应设置为 **[!UICONTROL Ready to Configure]**  和 **[!UICONTROL Mobile app migration status]** 设置为 **[!UICONTROL Not Migrated]**.

![](assets/aep_v4_6.png)

### 问：为何无法使用已配置资产状态的Adobe Experience Platform SDK应用程序进行迁移？ {#property-status}

答：迁移过程会保留SDK v4订阅者和属性。 它只会从Adobe Experience Platform SDK应用程序中保留与Launch相关的信息。 来自Adobe Experience Platform SDK应用程序的订阅者和其他数据将丢失。 为避免任何数据丢失，请仅将Adobe Experience Platform SDK应用程序与 **[!UICONTROL Ready to Configure]** **[!UICONTROL Property Status]** 符合迁移条件。

### 问：迁移后，我在哪里可以找到之前的SDK v4移动应用程序？ {#v4-app-not-visible}

答：迁移后的移动设备应用程序将从高级菜单中可见 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**.

### 问：迁移后，在哪里可以找到新创建的Adobe Experience Platform SDK应用程序？ {#aep-not-visible}

答：新创建的用于迁移的Adobe Experience Platform SDK应用程序将不作为单独的应用程序存在。 只有迁移的SDK v4应用程序才可用。

### 问：如果SDK v4移动应用程序组织单位设置为A（组织单位ALL的子代），而Adobe Experience Platform SDK设置为ALL。 如何迁移移动应用程序？ {#v4-org-unit}

答：的管理员 **[!UICONTROL Organizational unit]** 所有人员都将有权管理移动应用程序，并负责迁移。

### 问：如果SDK v4移动设备应用程序组织单位设置为A，而Adobe Experience Platform SDK应用程序设置为B（组织单位A的同级）。 如何迁移移动应用程序？ {#aep-org-unit}

答：Adobe Experience Platform SDK应用程序是同级应用程序的资产 **[!UICONTROL Organizational unit]**，则移动应用程序的用户将不可见 **[!UICONTROL Organizational unit]** A.移动设备应用程序将可供 **[!UICONTROL Organizational unit]** 但我们不建议这些管理员迁移移动应用程序。
在这种情况下，您应将移动应用程序移动到同一 **[!UICONTROL Organizational unit]** 或 **[!UICONTROL Organizational unit]** 具有父链接。
有关 **[!UICONTROL Organizational unit]**，请参阅 [部分](../../administration/using/organizational-units.md).

### 问：从您的Adobe Experience Platform SDK移动应用程序（从v4移动应用程序迁移）页面的推送渠道设置下拉列表下，不会显示Android密钥或iOS证书的上传日期/名称等信息 {#no-information-v5}

答：创建SDK V4移动应用程序后，系统不会存储此信息。 将SDK V4移动应用程序迁移到Adobe Experience Platform SDK移动应用程序时，迁移的移动应用程序也将没有此类信息。 用户一旦上传新的iOS证书或Android密钥，则该密钥或证书的不同详细信息将会存储在 **[!UICONTROL Push channel settings]** 下拉菜单。
