---
title: 订阅服务
description: 订阅服务活动允许您大量接收用户档案，并订阅服务或取消订阅服务。
page-status-flag: never-activated
uuid: 56637024-15ab-4145-9c48-3fbd27ab8af8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 74a6df0e-fd85-4404-a42c-9a7406512717
context-tags: setOfService,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e689e6bc362f4e948593c3b251f3825aab20ac
workflow-type: tm+mt
source-wordcount: '1110'
ht-degree: 0%

---


# 订阅服务 {#subscription-services}

## 说明 {#description}

![](assets/wf_subscription.png)

该 **[!UICONTROL Subscription Services]** 活动允许您大量购买用户档案，订阅服务或取消订阅服务。

>[!CAUTION]
>
>当在工作流的上下文中管理订阅时，订阅或未订阅用户档案不会接收在服务属性中定义的不同确认电子邮件。

## 使用环境 {#context-of-use}

活动 **[!UICONTROL Subscription Services]** 是唯一允许多个用户档案在单个操作中订阅或取消订阅服务的Adobe Campaign功能。

在进行定位或导入包含已识别数据的文件后，您可以使用此活动。

如果通过专用列在文件中指定，则此活动还允许您选择操作（订阅或取消订阅）以及要对其执行操作的服务。

**相关主题：**

* [用例： 从文件更新多个订阅状态](../../automating/using/updating-subscriptions-from-file.md)
* [用例： 将用户档案从文件订阅到特定服务](../../automating/using/subscribing-profiles-from-file.md)

## Configuration {#configuration}

1. 将活动拖放 **[!UICONTROL Subscription Services]** 到工作流中。
1. 在导入后将其连接到其他定位活动(如查询或对帐)之后。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮打开它。
1. 使用 **[!UICONTROL Service]** 以下选项之一选择要管理订阅的选项：

   * **[!UICONTROL Select a specific service]**: 手动选择服务。
   * **[!UICONTROL Select services from the inbound transition]**: 服务在入站过渡中指定。 例如，可以导入一个文件，该文件指定要为每行管理的服务。 如果选择此选项，请确保事先在数据和服务资源之间创 **建了链** 接，如本 [例所示](#example--updating-multiple-subscription-statuses-from-a-file)。

      然后，对每个记录动态选择要对其执行操作的服务。

1. 使用 **[!UICONTROL Operation type]** 以下选项之一选择要执行的选项：

   * **[!UICONTROL Select a specific operation type]**: 手动选择是要选择还 **[!UICONTROL Subscribe]** 是 **[!UICONTROL Unsubscribe]** 用户档案。
   * **[!UICONTROL Select an operation type from a path of inbound transition]**: 选择入站数据的列，该列指定要对每个记录执行的操作。

      在此列中，操作必须指定为布尔或整数。 使 **用** 0取消订阅记录， **使用** 1订阅。

      如果导入文件中包含的值与上述要求不匹配，您仍可以使用 [活动中可用的](../../automating/using/load-file.md#column-format) “值重新映射” **[!UICONTROL Load file]** 选项。

1. 如果入站订阅包含与服务的用户档案日期对应的列，请选择该列。 您可以将其留空，但运行工作流时不设置订阅日期。
1. 定义来源。 您可以通过选中该选项将其设置为入站数据的一个字段或所选的常数 **[!UICONTROL Set a constant as origin]** 值。 您可以将其留空，但在运行工作流时未设置来源。
1. 如果需要，您可以生成出站过渡。 此过渡包含与入站活动中完全相同的数据。
1. 确认活动的配置并保存工作流。

   现在可以执行。 一旦执行，您就可以在服务的详细信息中视图订阅或取消订阅服务的用户档案。

## 示例： 在导入文件后为特定服务订阅用户档案 {#example--subscribing-profiles-to-a-specific-service-after-importing-a-file}

此示例说明如何导入包含用户档案的文件并将其订阅到现有服务。 导入文件后，需要执行协调，以便将导入的数据标识为用户档案。 为确保文件不包含任何重复，将对数据执行外部重复数据删除活动。

工作流如下所示：

![](assets/subscription_activity_example1.png)

* 活动 **[!UICONTROL Load file]** 加载用户档案文件并定义导入列的结构。

   在此示例中，加载的文件采用。csv格式并包含以下数据：

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

* 活动 **[!UICONTROL Reconciliation]** 将文件中的数据标识为属于Adobe Campaign库的用户档案维。 只配置 **[!UICONTROL Identification]** 了选项卡。 它根据用户档案的电子邮件地址来标识文件数据。

   ![](assets/subscription_activity_example3.png)

* 根 **[!UICONTROL Deduplication]** 据临时资 **源的** “电子邮件”字段（由对帐产生）标识任何重复。 如果从文件导入的重复包含任何订阅，则对于所有数据，对服务的将失败。

   ![](assets/subscription_activity_example5.png)

* 活动 **[!UICONTROL Subscription Services]** 允许您选择用户档案必须订阅的服务、与订阅日期对应的字段以及订阅的来源。

   ![](assets/subscription_activity_example4.png)

## 示例： 从文件更新多个订阅状态 {#example--updating-multiple-subscription-statuses-from-a-file}

此示例说明如何导入包含用户档案的文件，并将其订阅更新为文件中指定的多个服务。 导入文件后，需要执行协调，以便将导入的数据标识为具有指向服务的链接的用户档案。 为确保文件不包含任何重复，将对数据执行外部重复数据删除活动。

工作流如下所示：

![](assets/subscription_activity_example1.png)

* 活动 **[!UICONTROL Load file]** 加载用户档案文件并定义导入列的结构。

   在此示例中，加载的文件采用。csv格式并包含以下数据：

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

   如您所注意的，该操作在文件中指定为“sub”或“nims”。 系统需要一个 **布尔** 或整 **数值来** 识别要执行的操作： “0”取消订阅，“1”取消订阅。 为满足此要求，将在“操作”列的详细信息中执行值的重新映射。

   ![](assets/subscription_example_remapping.png)

   如果文件已使用“0”和“1”来标识操作，则无需重新映射这些值。 仅确保在选项卡中将列作为 **布尔****或整数** 进行 **[!UICONTROL Column definition]** 处理。

* 活动 **[!UICONTROL Reconciliation]** 将文件中的数据标识为属于Adobe Campaign库的用户档案维。 通过选 **[!UICONTROL Identification]** 项卡， **文件的电子邮件** 字段与用户档案资 **源的电** 子邮件字段匹配。

   ![](assets/subscription_activity_example3.png)

   在选 **[!UICONTROL Relations]** 项卡中，将使用服务资源创建一个链接，以允 **许** 识别文件的服务字段。 在此示例中，这些值与服务 **资源** 的名称字段匹配。

   ![](assets/subscription_example_service_relation.png)

* 基 **[!UICONTROL Deduplication]** 于临时资 **源的** “电子邮件”字段（由对帐产生）标识重复。 消除重复很重要，因为在出现重复时，对服务的订阅将对所有数据失败。

   ![](assets/subscription_activity_example5.png)

* A标 **[!UICONTROL Subscription Services]** 识要更新的服务是来自过渡，通过活动中创建的链接 **[!UICONTROL Reconciliation]** 进行。

   该 **[!UICONTROL Operation type]** 文件标识为来自 **文件** 的操作字段。 此处只能选择布尔或整数字段。 如果列表中未显示包含要执行的操作的文件列，请确保已在活动中正确设置列格式，如本例前面所述。 **[!UICONTROL Load file]**

   ![](assets/subscription_activity_example_from_file.png)

