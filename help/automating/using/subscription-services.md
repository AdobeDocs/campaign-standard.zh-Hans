---
title: 订阅服务
seo-title: 订阅服务
description: 订阅服务
seo-description: 通过订阅服务活动，您可以将配置文件放置在大量资产中，并将其订阅服务或取消订阅服务。
page-status-flag: 从未激活
uuid: 56637024-15ab-4145-9c48-3fbd27ab8af8
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 数据管理活动
discoiquuid: 74a6df0e-fd85-4404-a42 c-9a7406512717
context-tags: setFofservice，workflow，main
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Subscription Services{#subscription-services}

## Description {#description}

![](assets/wf_subscription.png)

**[!UICONTROL Subscription Services]** 通过该活动，您可以将配置文件放置在大量资产中，并将其订阅服务或取消订阅服务。

>[!CAUTION]
>
>在工作流上下文中管理订阅时，订阅或取消订阅的配置文件不会接收服务属性中定义的不同确认电子邮件。

## Context of use {#context-of-use}

**[!UICONTROL Subscription Services]** 该活动是唯一一项Adobe Campaign功能，它允许通过单一操作订阅或取消订阅服务。

在执行定位或导入包含已识别数据的文件后，您可以使用此活动。

如果在文件中通过专用列指定，则此活动还允许您选择操作(订阅或取消订阅)以及执行操作所在的服务。

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Subscription Services]** activity into your workflow.
1. 在导入之后的其他定位活动之后连接它，如查询或排序。
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the **[!UICONTROL Service]** for which you would like to manage the subscriptions using one of the following options:

   * **[!UICONTROL Select a specific service]**：手动选择服务。
   * **[!UICONTROL Select services from the inbound transition]**：在入站过渡中指定服务。例如，您可以导入一个文件，它指定要为每一行管理的服务。If you choose this option, make sure a link has been created beforehand between the data and the **Service** resource, as shown in [this example](../../automating/using/subscription-services.md#example--updating-multiple-subscription-statuses-from-a-file).

      然后，为每个记录动态选择执行操作的服务。

1. Select the **[!UICONTROL Operation type]** to execute using one of the following options:

   * **[!UICONTROL Select a specific operation type]**：根据需要手动选择或 **[!UICONTROL Subscribe]****[!UICONTROL Unsubscribe]** 配置文件。
   * **[!UICONTROL Select an operation type from a path of inbound transition]**：选择用于指定每个记录执行操作的入站数据列。

      在此列中，必须将操作指定为布尔或整数。Use **0** to unsubscribe a record and **1** to subscribe.

      In case the values contained in an imported file do not match the above requirements, you can still use the [Remapping of values](../../automating/using/load-file.md#column-format) option available in the **[!UICONTROL Load file]** activity

1. 如果入站数据包含与配置文件的订阅日期对应的列，则将其选中。您可以将其留空，但在运行工作流时不设置订阅日期。
1. 定义订阅的来源。You can set it to one of the fields of the inbound data or to a constant value of your choice by checking the **[!UICONTROL Set a constant as origin]** option. 您可以将其留空，但在运行工作流时没有设置源。
1. 如果需要，您可以生成出站过渡。此过渡的数据与入站活动中的数据完全相同。
1. 确认活动的配置并保存工作流。

   现在可以执行此操作。执行后，您可以查看服务详细信息中订阅或取消订阅服务的配置文件。

## Example: Subscribing profiles to a specific service after importing a file {#example--subscribing-profiles-to-a-specific-service-after-importing-a-file}

此示例说明如何导入包含配置文件的文件并将其订阅现有服务。导入文件后，需要执行一个对帐，以便将所导入的数据识别为配置文件。为确保文件不包含任何重复项，将对数据执行取消删除活动。

此时将显示工作流：

![](assets/subscription_activity_example1.png)

* **[!UICONTROL Load file]** 活动将加载配置文件文件并定义导入列的结构。

   对于此示例，加载的文件为. csv格式，并且包含以下数据：

   ```
   lastname;firstname;email;birthdate;subdate
   jackman;megan;megan.jackman@testmail.com;07/08/1975;10/08/2017
   phillips;edward;phillips@testmail.com;09/03/1986;10/08/2017
   weaver;justin;justin_w@testmail.com;11/15/1990;10/08/2017
   martin;babeth;babeth_martin@testmail.net;11/25/1964;10/08/2017
   reese;richard;rreese@testmail.com;02/08/1987;11/08/2017
   cage;nathalie;cage.nathalie227@testmail.com;07/03/1989;11/08/2017
   xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992;11/08/2017
   grimes;daryl;daryl_890@testmail.com;12/06/1979;12/08/2017
   tycoon;tyreese;tyreese_t@testmail.net;10/08/1971;12/08/2017
   ```

   ![](assets/subscription_activity_example2.png)

* **[!UICONTROL Reconciliation]** 活动会将文件中的数据识别为Adobe Campaign数据库的配置文件维度。Only the **[!UICONTROL Identification]** tab is configured. 它会根据配置文件的电子邮件地址识别文件数据。

   ![](assets/subscription_activity_example3.png)

* A **[!UICONTROL Deduplication]** based on the **email** field of the temporary resource (resulting from the reconciliation) identifies any duplicates. 如果从文件导入的数据包含任何重复项，则订阅服务的订阅将失败。

   ![](assets/subscription_activity_example5.png)

* **[!UICONTROL Subscription Services]** 活动允许您选择要订阅的服务、对应于订阅日期的字段以及订阅源。

   ![](assets/subscription_activity_example4.png)

## Example: Updating multiple subscription statuses from a file {#example--updating-multiple-subscription-statuses-from-a-file}

此示例说明如何导入包含配置文件的文件，并将其订阅更新到文件中指定的多个服务。导入文件后，需要执行一个对帐，以便将导入的数据识别为配置文件，并提供指向服务的链接。为确保文件不包含任何重复项，将对数据执行取消删除活动。

此时将显示工作流：

![](assets/subscription_activity_example1.png)

* **[!UICONTROL Load file]** 活动将加载配置文件文件并定义导入列的结构。

   对于此示例，加载的文件为. csv格式，并且包含以下数据：

   ```
   lastname;firstname;email;birthdate;service;operation
   jackman;megan;megan.jackman@testmail.com;07/08/1975;SVC2;sub
   phillips;edward;phillips@testmail.com;09/03/1986;SVC3;unsub
   weaver;justin;justin_w@testmail.com;11/15/1990;SVC3;sub
   martin;babeth;babeth_martin@testmail.net;11/25/1964;SVC3;unsub
   reese;richard;rreese@testmail.com;02/08/1987;SVC3;sub
   cage;nathalie;cage.nathalie227@testmail.com;07/03/1989;SVC3;sub
   xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992;SVC4;sub
   grimes;daryl;daryl_890@testmail.com;12/06/1979;SVC3;unsub
   tycoon;tyreese;tyreese_t@testmail.net;10/08/1971;SVC2;sub
   ```

   ![](assets/subscription_example_load_file.png)

   如您所注意，该操作在文件中指定为“sub”或“unsub”。The system expects a **Boolean** or **Integer** value to recognize the operation to perform: "0" to unsubscribe and "1" to subscribe. 为了符合此要求，将在“操作”列的详细信息中执行值的重新映射。

   ![](assets/subscription_example_remapping.png)

   如果文件已经使用“0”和“1”识别操作，则无需重新映射这些值。Only make sure that the column is processed as a **Boolean** or **Integer** in the **[!UICONTROL Column definition]** tab.

* **[!UICONTROL Reconciliation]** 活动会将文件中的数据识别为Adobe Campaign数据库的配置文件维度。Through the **[!UICONTROL Identification]** tab, the **email** field of the file is matched to the **email** field of the profile resource.

   ![](assets/subscription_activity_example3.png)

   **[!UICONTROL Relations]** 在选项卡中，将使用服务资源创建链接，以允许识别文件的 **服务** 字段。In this example, the values match the **name** field of the service resource.

   ![](assets/subscription_example_service_relation.png)

* A **[!UICONTROL Deduplication]** based on the **email** field of the temporary resource (resulting from the reconciliation) identifies duplicates. 消除重复项很重要，因为在重复的情况下，订阅服务的订阅将失败。

   ![](assets/subscription_activity_example5.png)

* A **[!UICONTROL Subscription Services]** identifies the services to update as coming from the transition, through the link created in the **[!UICONTROL Reconciliation]** activity.

   The **[!UICONTROL Operation type]** is identified as coming from the **operation** field of the file. 此处只能选择Boolean或整数字段。If the column of your file that contains the operation to perform does not appear in the list, make sure that you have correctly set your column format in the **[!UICONTROL Load file]** activity, as explained earlier in this example.

   ![](assets/subscription_activity_example_from_file.png)

