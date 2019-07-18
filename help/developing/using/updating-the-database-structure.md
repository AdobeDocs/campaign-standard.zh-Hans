---
title: 更新数据库结构
seo-title: 更新数据库结构
description: 更新数据库结构
seo-description: 了解如何更新Adobe Campaign数据库。
page-status-flag: 从未激活
uuid: 6c802f4f-d298-4ca4-acdb-09f2 ad3865 b9
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 2448b126-66b8-4608-aa6 c-8028fb1902 a4
context-tags: 部署，主要；EventCusResource，概述
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Updating the database structure{#updating-the-database-structure}

为了使您对数据模型的修改生效并能够使用它们，需要更新数据库结构。

>[!NOTE]
>
>自定义资源在Adobe执行的自动更新期间自动刷新。

## Publishing a custom resource {#publishing-a-custom-resource}

要应用对资源所执行的更改，必须执行数据库更新。

>[!NOTE]
>
>如果修改或删除在活动上使用的自定义资源字段，相应的活动将自动取消发布。See [Configuring Transactional messaging](../../administration/using/configuring-transactional-messaging.md).

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]**, then **[!UICONTROL Publishing]**.
1. By default, the option **[!UICONTROL Determine modifications since the last publication]** is checked, which means that only the changes carried out since the last update will be applied.

   >[!NOTE]
   >
   >The **[!UICONTROL Repair database structure]** reestablishes a correct configuration if the publication failed before completing. 直接在数据库中执行且不使用自定义资源的任何修改都将被删除。

   ![](assets/schema_extension_12.png)

1. Click the **[!UICONTROL Prepare publication]** button to start the analysis. 请注意，当实例不有意忙于工作时，应进行大表更新。

   To learn more on the action to perform on the Profiles &amp; Services API, refer to [Publishing a resource with API extension](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension).

   ![](assets/schema_extension_13.png)

1. Once the publication has been carried out, click the **[!UICONTROL Publish]** button to apply your new configurations.
1. Once published, the **[!UICONTROL Summary]** pane of each resource indicates that the status is now **[!UICONTROL Published]** and specifies the date of the last publication.

   >[!NOTE]
   >
   >如果对资源进行了新更改，则必须重复此操作以应用更改。

   If resources have the **[!UICONTROL Pending re-draft]** status before publishing, then an additional message will appear inviting you to check your actions because publishing will result in definitive changes (deleting columns, tables...). To help you carry out this last change, an **[!UICONTROL SQL Script]** tab is available. 它提供将在发布期间执行的SQL命令。

   ![](assets/schema_extension_scriptsql.png)

   >[!NOTE]
   >
   >You can stop the Re-draft process by clicking the **[!UICONTROL Cancel re-draft]** button. 此操作会将资源的状态还原回原来的状态。

1. If your publication failed, you can always go back to the previous publication by clicking **[!UICONTROL Back to latest successful publication]**.

   请注意，如果将出版物保留为失败状态，将在登录实例后打开一个弹出窗口，以提醒您修复此发布。在修复发布之前，不会使用新产品版本升级您的实例。

   ![](assets/schema_extension_31.png)

## Publishing a resource with API extension {#publishing-a-resource-with-api-extension}

在下列情况下，您可以创建配置文件和服务API：

* When you extend the custom resources **[!UICONTROL Profiles]** or **[!UICONTROL Services]**, you can perform an update of the Profiles and Services API to integrate the fields declared in the custom resources extension.
* When you define a custom resource and you create a link between the resources **[!UICONTROL Profiles]** or **[!UICONTROL Services]** and the custom resource, you can perform an update to include the new resource in the API.

您可以在发布屏幕中选择此选项。

* 如果API尚未发布(意味着您从未扩展过资源，或者您从未对此资源或其他资源检查过此选项)，您可以选择创建或不使用。

   ![](assets/create-profile-and-services-api.png)

* 如果API已发布(意味着您已经延长了资源并选中了此选项)，则会强制执行API更新。

   事实上，一旦创建完毕，API会在您每次再次发布它时自动更新。这是为了避免破坏此API的配置文件或服务资源，并使您的实例损坏。

Note that by default, the custom resource is integrated, but, for a specific behavior, if you don't want to publish this resource, you can select the option **[!UICONTROL Hide this resource from APIs]** available in the **[!UICONTROL Resource Properties]**.

![](assets/removefromextoption.png)

After the **[!UICONTROL Prepare Publication]** step, Adobe Campaign displays the delta between the current version of the API and the future version after the publication in the tab **[!UICONTROL Profiles & Services API Preview]**. 如果您第一次扩展API，delta会将现成的自定义资源定义与扩展进行比较。

选项卡中显示的信息分为三部分：添加、删除和修改元素。

![](assets/extendpandsapi_diff.png)

delta的分析是一个强制步骤，因为发布步骤将修改API行为，而且极有可能影响周围的多米诺开发。

>[!NOTE]
>
>This publication updates the **[!UICONTROL profilesAndServicesExt]** API. **[!UICONTROL profilesAndServices]** API不会更新。

For more information on the Adobe Campaign API, consult the dedicated Adobe Campaign documentation on [Adobe IO](https://docs.campaign.adobe.com/doc/standard/en/adobeio.html).
