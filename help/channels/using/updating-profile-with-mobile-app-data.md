---
title: 基于移动应用程序数据创建和更新用户档案信息
description: 了解如何根据移动应用程序数据创建和更新用户档案信息。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: delivery,mobileAppContent,back
feature: Push
role: User
level: Intermediate
exl-id: 1b48456e-9aae-485c-a7c4-7e3e2f53cbca
source-git-commit: 21bcc9818b881212985988ef3377687069a1dbea
workflow-type: tm+mt
source-wordcount: '1000'
ht-degree: 2%

---

# 基于移动应用程序数据创建和更新用户档案信息

## 概述

本页介绍了开发工作流的步骤，该工作流会在移动设备应用程序按计划发送收集PII数据之后创建/更新用户档案数据。

* **PII**&#x200B;表示“个人身份信息”。 它可以是任何数据，包括未出现在Campaign数据库“用户档案”表中的信息，例如Analytics for Mobile [目标点](../../integrating/using/about-campaign-points-of-interest-data-integration.md)。 PII由移动设备应用程序开发人员定义，通常由营销人员定义。
* **收集PII**&#x200B;是从移动应用程序对Adobe Campaign Standard中的Rest API进行HTTPPOST的操作。

此用例的目标是创建或更新Campaign Standard配置文件（如果移动应用程序返回的PII数据包含与配置文件相关的数据）。

## 先决条件

在Campaign Standard中启用推送通知需要执行多个配置步骤，然后才能根据移动应用程序订阅数据创建或更新用户档案：

1. [创建移动应用程序](../../administration/using/configuring-a-mobile-application.md)
1. [将Adobe移动SDK与您的移动应用程序集成](../../administration/using/supported-mobile-use-cases.md)。
1. [配置Adobe Campaign以发送推送通知](../../administration/using/configuring-a-mobile-application.md)。

## 步骤1 — 扩展推送通知/订阅的用户档案资源

要使用PII数据创建或更新用户档案资源，您必须首先使用所需字段扩展用户档案资源。 操作步骤：

* 标识由移动设备应用程序发送的PII字段。
* 确定用于协调以将PII数据与用户档案数据关联的字段。

![](assets/update_profile1.png)

在此示例中，**[!UICONTROL Fields]**&#x200B;部分反映由移动设备应用程序发送的PII数据。 **[!UICONTROL Link to profiles]**&#x200B;部分指示用于将PII与配置文件数据关联的字段，其中&#x200B;**cusEmail**&#x200B;映射到&#x200B;**@email**。

扩展&#x200B;**[!UICONTROL Subscriptions to an Application]**&#x200B;资源时配置文件数据的映射是只读的。 用于协调。 必须将用户档案输入到系统中，并输入必要的数据才能将用户档案与PII数据进行协调。 在本例中，用户档案的电子邮件地址必须与收集PII中的电子邮件匹配，才能进行协调：

* 从移动设备应用程序接收用户的收集PII，其名字为“Jane，姓氏为“Doe”，电子邮件地址为janedoe@doe.com。
* 另外，用户档案的数据必须存在（例如，数据必须手动输入或来自其他某个资源），其中用户档案的电子邮件地址为janedoe@doe.com。

**相关主题：**

* [将订阅扩展到应用程序资源](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)。
* [正在创建或扩展现有资源](../../developing/using/key-steps-to-add-a-resource.md)。

## 第2步 — 创建工作流

在Campaign Standard中使用工作流可让管理员唯一地标识并同步AppSubscription（订阅者）数据和配置文件或收件人数据之间的数据。 虽然基于工作流的更新不会实时同步配置文件数据，但它不应导致任何不必要的数据库锁定或开销。

构建工作流的主要步骤包括：

1. 使用&#x200B;**[!UICONTROL Query]**&#x200B;或&#x200B;**[!UICONTROL Incremental query]**&#x200B;活动获取最新订阅的列表。
1. 使用&#x200B;**[!UICONTROL Reconciliation]**&#x200B;活动将PII数据与配置文件进行映射。
1. 添加一些验证流程。
1. 使用&#x200B;**[!UICONTROL Update data]**&#x200B;更新或创建包含PII数据的配置文件。

此工作流中假定有以下要求：

* 已扩展的任何/所有字段应该可用于创建/更新用户档案表。
* 可以扩展配置文件表以支持本身不受支持的字段（例如，T恤尺寸）。
* AppSubscription表中任何为空的字段都不应在配置文件表中更新。
* AppSubscription表中更新的任何记录都应包含在工作流下次运行中。

要构建工作流，请将以下活动拖放到工作区中并将它们链接在一起： **[!UICONTROL Start]**、**[!UICONTROL Scheduler]**、**[!UICONTROL Incremental query]**、**[!UICONTROL Update data]**。

![](assets/update_profile0.png)

然后按照以下步骤配置每个活动。

### 配置&#x200B;**[!UICONTROL Scheduler]**&#x200B;活动

在&#x200B;**[!UICONTROL General]**&#x200B;选项卡中，设置&#x200B;**[!UICONTROL Execution frequency]**（例如，“每日”）、**[!UICONTROL Time]**（例如，“1:00:00 AM”）和&#x200B;**[!UICONTROL Start]**（例如，今天的日期）。

![](assets/update_profile2.png)

### 配置&#x200B;**[!UICONTROL Incremental query]**&#x200B;活动。

1. 在&#x200B;**[!UICONTROL Properties]**&#x200B;选项卡中，单击&#x200B;**[!UICONTROL Resource]**&#x200B;字段的&#x200B;**[!UICONTROL Select an element]**&#x200B;图标，然后选择&#x200B;**[!UICONTROL Subscriptions to an application (`nms:appSubscriptionRcp:appSubscriptionRcpDetail`)]**&#x200B;元素。

   ![](assets/update_profile3.png)

1. 在&#x200B;**[!UICONTROL Target]**&#x200B;选项卡中，拖动&#x200B;**[!UICONTROL Mobile application]**&#x200B;筛选器，然后选择移动设备应用程序名称。

   ![](assets/update_profile4.png)

1. 在&#x200B;**[!UICONTROL Processed data]**&#x200B;选项卡中，选择&#x200B;**[!UICONTROL Use a date field]**，然后将&#x200B;**[!UICONTROL Last modified (lastModified)]**&#x200B;字段添加为&#x200B;**[!UICONTROL Path to the date field]**。

   ![](assets/update_profile5.png)

### 配置&#x200B;**[!UICONTROL Update data]**&#x200B;活动。

1. 在&#x200B;**[!UICONTROL Identification]**&#x200B;选项卡中，确保&#x200B;**[!UICONTROL Dimension to update]**&#x200B;字段设置为“Profiles (profile)”，然后单击&#x200B;**[!UICONTROL Create element]**&#x200B;按钮添加字段作为协调条件。

   ![](assets/update_profile_createelement.png)

1. 在&#x200B;**[!UICONTROL Source]**&#x200B;字段中，从appSubscriptionRcp表中选择一个字段作为协调字段。 它可以是用户档案的电子邮件、crmId、marketingCloudId等。 在此示例中，使用“电子邮件(cusEmail)”字段。

1. 在&#x200B;**[!UICONTROL Destination]**&#x200B;字段中，从配置文件表中选择一个字段以协调appSubscriptionRcp表中的数据。 它可以是用户档案的电子邮件，也可以是任何扩展字段，如crmId、marketingCloudId等。 在此示例中，我们需要选择“电子邮件(email)”字段，以将其映射到appSubscriptionRcp表中的“电子邮件(cusEmail)”字段。

   ![](assets/update_profile7.png)

1. 在&#x200B;**[!UICONTROL Fields to update]**&#x200B;选项卡中，单击&#x200B;**[!UICONTROL Create element]**&#x200B;按钮，然后将来自appSubscriptionRcp表的字段（**[!UICONTROL Source]**&#x200B;字段）映射到要在配置文件表中更新的字段（**[!UICONTROL Destination]**&#x200B;字段）。

1. 在&#x200B;**[!UICONTROL Enabled if]**&#x200B;字段中，添加表达式，以确保仅当源字段包含值时，才能更新用户档案表中的相应字段。 要执行此操作，请从列表中选择字段，然后添加“！=&quot;&quot;表达式(如果Source字段在表达式编辑器中为`[target/@cusEmail]`，请确保键入`[target/@cusEmail] != ''"`)。

   ![](assets/update_profile8.png)

>[!NOTE]
>
>在这种情况下，工作流会执行UPSERT，但由于它基于&#x200B;**[!UICONTROL Incremental query]**&#x200B;数据，因此仅插入。 更改查询会影响插入或更新的数据。
>此外，要更新的字段选项卡中的设置确定在特定条件下插入或更新哪些字段。 这些设置对于每个应用程序或客户可能都是唯一的。
>配置这些设置时请务必小心，可能会产生意想不到的结果，因为根据appSubscriptionRcp数据更新配置文件中的记录可能会更改用户的个人信息，而无需进行验证。

添加要在配置文件中插入/更新的所有字段后，单击&#x200B;**[!UICONTROL Confirm]**。

![](assets/update_profile9.png)

保存工作流，然后单击&#x200B;**[!UICONTROL Start]**&#x200B;以执行工作流。

![](assets/update_profile10.png)
