---
title: 订阅服务
seo-title: 订阅服务
description: 订阅服务
seo-description: 订阅服务活动允许您批量接收配置文件并将其订阅到服务或取消订阅服务。
page-status-flag: 从未激活
uuid: 56637024-15ab-4145-9c48-3fbd27ab8af8
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 数据管理活动
discoiquuid: 74a6df0e-fd85-4404-a42c-9a7406512717
context-tags: setOfService，工作流，主
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# 订阅服务{#subscription-services}

## 说明 {#description}

![](assets/wf_subscription.png)

该活 **[!UICONTROL Subscription Services]** 动允许您批量获取配置文件，并将其订阅到服务或取消订阅服务。

>[!CAUTION]
>
>当在工作流的上下文中管理订阅时，订阅或取消订阅的配置文件不会接收在服务属性中定义的不同的确认电子邮件。

## 使用环境 {#context-of-use}

该活 **[!UICONTROL Subscription Services]** 动是唯一一项Adobe Campaign功能，它允许在单个操作中订阅或取消订阅服务的多个配置文件。

在进行定位或导入了包含已识别数据的文件后，您可以使用此活动。

如果通过专用列在文件中指定，则此活动还允许您选择操作（订阅或取消订阅）以及执行该操作的服务。

## 配置 {#configuration}

1. 将活动拖放 **[!UICONTROL Subscription Services]** 到工作流中。
1. 在导入后的查询或对帐等其他定位活动之后连接它。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮将其打开。
1. 使用 **[!UICONTROL Service]** 以下选项之一选择要管理其订阅的选项：

   * **[!UICONTROL Select a specific service]**:手动选择服务。
   * **[!UICONTROL Select services from the inbound transition]**:服务在入站过渡中指定。 例如，可以导入一个文件，该文件指定要为每行管理的服务。 如果选择此选项，请确保数据与服务资源之间已预先创建了链接，如本 **例所示**[](#example--updating-multiple-subscription-statuses-from-a-file)。

      然后，为每个记录动态地选择要执行操作的服务。

1. 使用 **[!UICONTROL Operation type]** 以下选项之一选择要执行的选项：

   * **[!UICONTROL Select a specific operation type]**:手动选择是要选择配置 **[!UICONTROL Subscribe]** 文件还 **[!UICONTROL Unsubscribe]** 是配置。
   * **[!UICONTROL Select an operation type from a path of inbound transition]**:选择入站数据的列，该列指定对每个记录执行的操作。

      在此列中，必须将操作指定为Boolean或Integer。 使用 **0** 可取消订阅记录， **使用** 1可订阅。

      如果导入文件中包含的值与上述要求不匹配，您仍可以使用活动中可用的“重 [新映射值](../../automating/using/load-file.md#column-format) ”选项 **[!UICONTROL Load file]** 。

1. 如果入站数据包含一列，该列与服务的配置文件的订阅日期相对应，请选择该列。 您可以将其留空，但运行工作流时不会设置订阅日期。
1. 定义订阅的源。 您可以通过选中该选项将其设置为入站数据的一个字段或您选择的常数 **[!UICONTROL Set a constant as origin]** 值。 可以将其留空，但运行工作流时不设置源。
1. 如果需要，您可以生成出站过渡。 此过渡包含的数据与入站活动中的数据完全相同。
1. 确认活动的配置并保存工作流。

   现在可以执行。 一旦执行，您就可以在服务的详细信息中查看订阅或取消订阅服务的配置文件。

## 示例：在导入文件后将配置文件订阅到特定服务 {#example--subscribing-profiles-to-a-specific-service-after-importing-a-file}

此示例说明了如何导入包含配置文件的文件并将其订阅到现有服务。 导入文件后，需要执行协调，以便将导入的数据标识为配置文件。 为确保文件不包含任何重复项，将对数据执行重复数据消除活动。

该工作流如下所示：

![](assets/subscription_activity_example1.png)

* 活动 **[!UICONTROL Load file]** 加载配置文件并定义导入的列的结构。

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

* 活 **[!UICONTROL Reconciliation]** 动会将文件中的数据标识为属于Adobe Campaign数据库的配置文件维度。 只配置 **[!UICONTROL Identification]** 了选项卡。 它根据配置文件的电子邮件地址来标识文件数据。

   ![](assets/subscription_activity_example3.png)

* 根据 **[!UICONTROL Deduplication]** 临时资源 **的电子邮件** （由对帐产生）字段识别任何副本。 如果从文件导入的数据包含任何重复项，则对服务的订阅将失败以获取所有数据。

   ![](assets/subscription_activity_example5.png)

* 通过 **[!UICONTROL Subscription Services]** 活动，您可以选择配置文件必须订阅的服务、与订阅日期对应的字段以及订阅的源。

   ![](assets/subscription_activity_example4.png)

## 示例：从文件更新多个订阅状态 {#example--updating-multiple-subscription-statuses-from-a-file}

此示例说明如何导入包含配置文件的文件，并将其订阅更新到文件中指定的多个服务。 导入文件后，需要执行协调，以便将导入的数据标识为具有指向服务的链接的配置文件。 为确保文件不包含任何重复项，将对数据执行重复数据消除活动。

该工作流如下所示：

![](assets/subscription_activity_example1.png)

* 活动 **[!UICONTROL Load file]** 加载配置文件并定义导入的列的结构。

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

   正如您所注意的，操作在文件中指定为“sub”或“nimbust”。 系统需要一个 **Boolean** 或 **** Integer值来识别要执行的操作：“0”可取消订阅，“1”可订阅。 为了满足此要求，将在“operation”列的详细信息中执行值的重新映射。

   ![](assets/subscription_example_remapping.png)

   如果您的文件已使用“0”和“1”来标识操作，则无需重新映射这些值。 仅确保在选项卡中将列作为 **Boolean****或Integer** 进行 **[!UICONTROL Column definition]** 处理。

* 活 **[!UICONTROL Reconciliation]** 动会将文件中的数据标识为属于Adobe Campaign数据库的配置文件维度。 通过选 **[!UICONTROL Identification]** 项卡，文件的 **电子邮件字段与配置文件资源** 的电子邮件字段相匹配 **** 。

   ![](assets/subscription_activity_example3.png)

   在选 **[!UICONTROL Relations]** 项卡中，使用服务资源创建一个链接，以允许 **识别文件的** “服务”字段。 在此示例中，这些值与服务资 **源的名称** 字段相匹配。

   ![](assets/subscription_example_service_relation.png)

* 根据 **[!UICONTROL Deduplication]** 临时资源 **的电子邮件** （由对帐产生）字段识别重复项。 消除重复项很重要，因为在出现重复项的情况下，对服务的订阅将失败。

   ![](assets/subscription_activity_example5.png)

* A标 **[!UICONTROL Subscription Services]** 识要更新的服务是通过活动中创建的链接从过渡中来 **[!UICONTROL Reconciliation]** 的。

   该 **[!UICONTROL Operation type]** 字段标识为来自 **文件的** operation字段。 此处只能选择布尔或整数字段。 如果包含要执行的操作的文件列未出现在列表中，请确保您已在活动中正确设置了列格式，如本示例前面所述。 **[!UICONTROL Load file]**

   ![](assets/subscription_activity_example_from_file.png)

