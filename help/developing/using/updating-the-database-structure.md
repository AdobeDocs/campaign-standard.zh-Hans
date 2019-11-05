---
title: 更新数据库结构
description: 了解如何更新Adobe Campaign数据库。
page-status-flag: 从未激活
uuid: 6c802f4f-d298-4ca4-acdb-09f2ad3865b9
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 开发
content-type: 参考
topic-tags: adding-or-extending-a-resource
discoiquuid: 2448b126-66b8-4608-aa6c-8028fb1902a4
context-tags: deploy,main;eventCusResource，概述
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 更新数据库结构{#updating-the-database-structure}

要使您对数据模型的修改有效并能够使用它们，需要更新数据库结构。

>[!NOTE]
>
>自定义资源在Adobe执行的自动更新期间自动刷新。

## 发布自定义资源 {#publishing-a-custom-resource}

要应用对资源所做的更改，必须执行数据库更新。

>[!NOTE]
>
>如果修改或删除了在事件上使用的自定义资源的字段，则相应的事件将自动取消发布。 See [Configuring Transactional messaging](../../administration/using/configuring-transactional-messaging.md).

1. 从高级菜单中，通过Adobe Campaign徽标，选择 **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]**，然后 **[!UICONTROL Publishing]**。
1. 默认情况下，选 **[!UICONTROL Determine modifications since the last publication]** 中此选项，这意味着将仅应用自上次更新以来执行的更改。

   >[!NOTE]
   >
   >如果 **[!UICONTROL Repair database structure]** 发布在完成之前失败，则会重新建立正确的配置。 将删除直接在数据库中执行的、不使用自定义资源的任何修改。

   ![](assets/schema_extension_12.png)

1. 单击 **[!UICONTROL Prepare publication]** 按钮以开始分析。 请注意，当实例不因工作流而忙得很多时，应进行大表更新。

   要进一步了解对Profiles &amp; Services API执行的操作，请参阅 [发布带API扩展的资源](#publishing-a-resource-with-api-extension)。

   ![](assets/schema_extension_13.png)

1. 执行发布后，单击按钮以应 **[!UICONTROL Publish]** 用您的新配置。
1. 发布后，每 **[!UICONTROL Summary]** 个资源的窗格将指示状态现在为 **[!UICONTROL Published]** 状态并指定上次发布的日期。

   >[!NOTE]
   >
   >如果对资源进行了新更改，则必须对要应用的更改重复此操作。

   如果资源在发 **[!UICONTROL Pending re-draft]** 布之前处于状态，则会显示另一条消息，邀请您检查您的操作，因为发布将导致最终更改（删除列、表……）。 为帮助您执行上次更改，可使 **[!UICONTROL SQL Script]** 用选项卡。 它提供将在发布过程中执行的SQL命令。

   ![](assets/schema_extension_scriptsql.png)

   >[!NOTE]
   >
   >单击该按钮可停止“重绘”过 **[!UICONTROL Cancel re-draft]** 程。 此操作会将资源的状态还原回其原始状态。

1. 如果发布失败，您始终可以通过单击返回到上一个发布 **[!UICONTROL Back to latest successful publication]**。

   请注意，如果将出版物保留为失败状态，您登录实例后将立即打开一个弹出窗口，提醒您修复此出版物。 在您的发布被修复之前，您的实例不会升级为新产品版本。

   ![](assets/schema_extension_31.png)

## 使用API扩展发布资源 {#publishing-a-resource-with-api-extension}

在以下情况下，您可以创建Profile和Services API:

* 扩展自定义资源时， **[!UICONTROL Profiles]** 或 **[!UICONTROL Services]**&#x200B;者，您可以执行Profiles and Services API的更新，以集成在自定义资源扩展中声明的字段。
* 定义自定义资源并在资源或自定义资源之间创建 **[!UICONTROL Profiles]** 链 **[!UICONTROL Services]** 接时，可以执行更新以将新资源包含在API中。

您可以在发布屏幕中选择此选项。

* 如果API尚未发布（即，如果您从未扩展过资源，或者您尚未为此资源或其他资源选中此选项），则可以选择是否创建它。

   ![](assets/create-profile-and-services-api.png)

* 如果API已发布（即，如果您已扩展资源并选中此选项一次），则将强制进行API更新。

   事实上，一旦创建了API,API会在您每次再次发布时自动更新。 这是为了避免破坏此API的配置文件或服务资源并损害实例。

请注意，默认情况下，自定义资源是集成的，但是，对于特定行为，如果您不想发布此资源，则可以在中选择可 **[!UICONTROL Hide this resource from APIs]** 用的选项 **[!UICONTROL Resource Properties]**。

![](assets/removefromextoption.png)

执行此步 **[!UICONTROL Prepare Publication]** 骤后，Adobe Campaign会在选项卡中显示API的当前版本与发布后的将来版本之间的增量 **[!UICONTROL Profiles & Services API Preview]**。 如果您是第一次扩展API，则增量将比较现成的自定义资源定义与您的扩展。

选项卡中显示的信息分为三个部分：添加、删除和修改的元素。

![](assets/extendpandsapi_diff.png)

对delta的分析是一个必需步骤，因为发布步骤将修改API行为，并且极有可能在多米诺效应下影响周围的开发。

>[!NOTE]
>
>此出版物更新 **[!UICONTROL profilesAndServicesExt]** API。 不 **[!UICONTROL profilesAndServices]** 更新API。

有关Adobe Campaign API的详细信息，请查阅有关 [Adobe IO的专用Adobe Campaign文档](https://docs.campaign.adobe.com/doc/standard/en/adobeio.html)。
