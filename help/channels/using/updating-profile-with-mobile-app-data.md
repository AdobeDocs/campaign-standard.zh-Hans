---
title: 基于移动应用程序数据创建和更新用户档案信息
description: 了解如何根据移动应用程序数据创建和更新配置文件信息。
page-status-flag: 从未激活
uuid: 8cf74cad-b1ba-4aad-83bd-7289cb22d5f4
contentOwner: 勒梅特
products: SG_CAMPAIGN/STANDARD
audience: 频道
content-type: 参考
topic-tags: 推送通知
discoiquuid: dc944c85-2059-46df-b396-676fe3617dd1
context-tags: delivery,mobileAppContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 基于移动应用程序数据创建和更新用户档案信息

## 概述

本页介绍了开发工作流的步骤，该工作流在Mobile应用程序发送收集PII数据后按计划创建／更新配置文件数据。

* **PII代表** “个人身份识别信息”。 它可以是任何数据，包括Campaign数据库的“配置文件”表中未显示的信息，例如，Analytics for Mobile [Points of Interest](../../integrating/using/about-campaign-points-of-interest-data-integration.md)。 PII由移动应用程序开发人员定义，通常由营销人员定义。
* **Collect PII** is a HTTP-POST operation an to a Adobe Campaign Standard中的Rest API from a Mobile App.

此用例的目的是创建或更新Campaign Standard配置文件（如果移动应用程序返回的PII数据包含与配置文件相关的数据）。

## 先决条件

要在Campaign standard中启用推送通知，需要执行多个配置步骤，然后才能根据移动应用程序订阅数据创建或更新配置文件：

1. [创建移动应用程序](../../administration/using/configuring-a-mobile-application.md)
1. [将Adobe Mobile SDK与您的移动应用程序集成](https://helpx.adobe.com/campaign/kb/integrate-mobile-sdk.html)。
1. [配置Adobe Campaign以发送推送通知](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)。

## 第1步——扩展推送通知／订阅的配置文件资源

要能够使用PII数据创建或更新配置文件资源，您必须首先使用所需字段扩展配置文件资源。 操作步骤：

* 标识由移动应用程序发送的PII字段。
* 确定用于对帐的字段，以将PII数据与配置文件数据关联。

![](assets/update_profile1.png)

在此示例中，该部 **[!UICONTROL Fields]** 分反映由移动应用程序发送的PII数据。 该部 **[!UICONTROL Link to profiles]** 分指示用于将PII与配置文件数据关联的字段，其中cusEmail **映射到** @email ****。

扩展资源时的“配置文件数据” **[!UICONTROL Subscriptions to an Application]** 映射为“只读”。 用于和解。 必须将配置文件输入到系统中，并包含必要的数据，才能使配置文件与PII数据保持一致。 在我们的情况下，配置文件的电子邮件地址必须与来自Collect PII的电子邮件匹配，才能进行对帐：

* 收集PII是从移动应用程序接收的，其用户的名字为“Jane”，姓氏为“Doe”，电子邮件地址为janedoe@doe.com。
* 另外，配置文件数据必须存在（例如，必须手动输入数据或已来自某些其他资源），其中配置文件的电子邮件地址为janedoe@doe.com。

**相关主题：**

* [将订阅扩展到应用程序资源](../../developing/using/extending-the-subscriptions-to-an-application-resource.md).
* [创建或扩展现有资源](../../developing/using/key-steps-to-add-a-resource.md)。

## 第2步——创建工作流

使用Campaign standard中的工作流，管理员可以唯一地识别和同步AppSubscription（订阅者）数据与个人资料或收件人数据之间的数据。 虽然基于工作流的更新不会实时同步配置文件数据，但它不会造成任何不当的数据库锁定或开销。

构建工作流的主要步骤有：

1. 使用或 **[!UICONTROL Query]** 活 **[!UICONTROL Incremental query]** 动获取最新订阅的列表。
1. 使用活 **[!UICONTROL Reconciliation]** 动将PII数据与配置文件映射。
1. 添加一些验证过程。
1. 使用 **[!UICONTROL Update data]** 更新或创建包含PII数据的配置文件。

在此工作流中假定有以下要求：

* 已扩展的任何／所有字段应可用于创建／更新配置文件表。
* “配置文件”表可以扩展为支持本机不支持的字段（例如T恤衫大小）。
* AppSubscription表中的任何空白字段都不应在配置文件表中更新。
* AppSubscription表中已更新的任何记录都应包含在工作流的下一运行中。

要构建工作流，请执行以下步骤：

1. 将以下活动拖放到工作区中并将它们链接在一起：
   1. **[!UICONTROL Start]**
   1. **[!UICONTROL Scheduler]**
   1. **[!UICONTROL Incremental query]**
   1. **[!UICONTROL Update data]**
   ![](assets/update_profile0.png)

1. 配置活 **[!UICONTROL Scheduler]** 动。 在选 **[!UICONTROL General]** 项卡中，设置 **[!UICONTROL Execution frequency]** （例如，“每日”）、 **[!UICONTROL Time]** （例如，“上午1:00:00”）和 **[!UICONTROL Start]** （例如，今天的日期）。

   ![](assets/update_profile2.png)

1. 配置活 **[!UICONTROL Incremental query]** 动。
   1. 在选 **[!UICONTROL Properties]** 项卡中，单击字 **[!UICONTROL Select an element]** 段的图 **[!UICONTROL Resource]** 标，然后选择元 **[!UICONTROL Subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** 素。

      ![](assets/update_profile3.png)

   1. 在选项卡 **[!UICONTROL Target]** 中，拖动过滤器， **[!UICONTROL Mobile application]** 然后选择移动设备应用程序名称。

      ![](assets/update_profile4.png)

   1. 在选项卡 **[!UICONTROL Processed data]** 中，选择 **[!UICONTROL Use a date field]**，然后将字段 **[!UICONTROL Last modified (lastModified)]** 添加为 **[!UICONTROL Path to the date field]**。

      ![](assets/update_profile5.png)

1. 配置活 **[!UICONTROL Update data]** 动。
   1. 在选 **[!UICONTROL Identification]** 项卡中，确保字段设置 **[!UICONTROL Dimension to update]** 为“配置文件（配置文件）”，然后单击按钮 **[!UICONTROL Create element]** 以添加字段作为对帐标准。

      ![](assets/update_profile_createelement.png)

   1. 在字段 **[!UICONTROL Source]** 中，从appSubscriptionRcp表中选择一个字段作为对帐字段。 它可以是个人资料的电子邮件、crmId、marketingCloudId等。 在此示例中，我们将使用“电子邮件(cusEmail)”字段。
   1. 在字段 **[!UICONTROL Destination]** 中，从配置文件表中选择一个字段以协调appSubscriptionRcp表中的数据。 它可以是个人资料的电子邮件，也可以是任何扩展字段，如crmId、marketingCloudId等。 在此示例中，我们需要选择“电子邮件（电子邮件）”字段，以将其与appSubscriptionRcp表中的“电子邮件(cusEmail)”字段进行映射。

      ![](assets/update_profile7.png)

   1. 在选 **[!UICONTROL Fields to update]** 项卡中，单击按钮，然 **[!UICONTROL Create element]** 后将appSubscriptionRcp表（字段）中的字段与要在“配置文件”表（字段）中更新的字段(**[!UICONTROL Source]****[!UICONTROL Destination]** 字段)映射。
   1. 在字段 **[!UICONTROL Enabled if]** 中，添加一个表达式，以确保仅在源字段包含值时才更新“配置文件”表中的相应字段。 为此，请从列表中选择字段，然后添加“!="" expression(如果“源”字段在“表达式” `[target/@cusEmail]` 编辑器中，请确保键入 `[target/@cusEmail] != ''"`内容)。

      ![](assets/update_profile8.png)

      >[!NOTE]
      >
      >在这种情况下，工作流将执行UPSERT，但因为它基于增量查询数据，所以只会插入。 更改查询会影响要插入或更新的数据。
      >此外，“要更新的字段”选项卡中的设置决定了在特定条件下插入或更新哪些字段。 这些设置对于每个应用程序或客户都是唯一的。 在配置这些设置时要小心，因为可能会产生意外的后果，因为基于appSubscriptionRcp数据的配置文件中的更新记录可能会更改用户个人信息而无需验证。

   1. 在“配置文件”中添加要插入／更新的所有字段后，单击 **[!UICONTROL Confirm]**。

      ![](assets/update_profile9.png)

1. 保存工作流，然后单击开始以启动工作流进程。

   ![](assets/update_profile10.png)
