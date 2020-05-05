---
title: 事件交易消息
description: 了解如何创建和发布事件事务性消息。
page-status-flag: never-activated
uuid: d747feb5-58fb-4e12-a176-404f0eca5391
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: 4f6317a1-9dfe-4714-bc1c-393629d855cd
context-tags: deliveryTransactionalTemplate,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 816d550d8bd0de085a47f97c1f6cc2fbb5e7acb9

---


# 事件交易消息{#event-transactional-messages}

您可以发送事件事务性消息，瞄准事件。 此类事务性消息不包含用户档案信息： 投放目标由事件本身包含的数据定义。

创建并发布事件后(如本节所述，放弃购 [物车](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle))，将自动创建相应的事务性消息。

配置事件以发送 [事务性消息部分中介绍了配置步骤](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) 。

为了让事件触发发送事务性消息，您必须对消息进行个性化设置，然后测试并发布消息。

>[!NOTE]
>
>要访问事务性消息，您必须是安全组的一 **[!UICONTROL Administrators (all units)]** 部分。
>
>事件事务性消息不包含用户档案信息，因此它们与疲劳规则不兼容(即使是与用户档案扩充的)。 请参 [阅疲劳规则](../../sending/using/fatigue-rules.md#choosing-the-channel)。

## 在事务性消息中定义测试用户档案 {#defining-a-test-profile-in-a-transactional-message}

定义一个经过调整的测试用户档案，它允许您预览消息并发送验证来检查消息。

### 在事务性消息中创建测试用户档案 {#creating-a-test-profile-within-the-transactional-----------message}

1. 要访问您创建的消息，请单击左 **[!UICONTROL Adobe Campaign]** 上角的标志，然后选择 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**。

   ![](assets/message-center_4.png)

1. 创建将链接到您的用户档案的测试事件。

   ![](assets/message-center_test-profile.png)

1. 在部分中指定要以JSON格式发送的 **[!UICONTROL Event data used for personalization]** 信息。 这是预览消息和测试用户档案收到验证时将使用的内容。

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >您还可以输入与用户档案表相关的信息。 请参 [阅丰富事务性消息内容](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)。

1. 创建后，将在用户档案中预先指定测试事务性消息。 单击 **[!UICONTROL Test profiles]** 消息块检查验证的目标。

   ![](assets/message-center_5.png)

### 在事务性消息之外创建测试用户档案 {#creating-a-test-profile-outside-the-transactional-----------message}

您还可以创建新的测试用户档案，或使用菜单中已存在的测 **[!UICONTROL Test profiles]** 试。

1. 单击左 **[!UICONTROL Adobe Campaign]** 上角的标志，然后选择 **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**。
1. 在您 **[!UICONTROL Event]** 选择的测试用户档案页的部分，选择您刚刚创建的事件。 在此示例中，选择“购物车放弃(EVTcartElication)”。
1. 在文本框中指定要以JSON格式发送 **[!UICONTROL Event data]** 的信息。

   ![](assets/message-center_3.png)

1. 保存更改。

您现在可以访问您创建的消息并选择更新的测试用户档案。

**相关主题：**

* [管理测试用户档案](../../audiences/using/managing-test-profiles.md)
* [定义受众](../../audiences/using/creating-audiences.md)

## 个性化事务性消息 {#personalizing-a-transactional-message}

要在事务性消息中设置个性化，请按照以下步骤操作：

1. 单击 **[!UICONTROL Content]** 该块以修改邮件的主题和内容。 对于此示例，选择包含图像和文本的任何模板。 有关电子邮件内容模板的详细信息，请参 [阅使用模板进行设计](../../designing/using/using-reusable-content.md#designing-templates)。

   ![](assets/message-center_6.png)

1. 添加主题并编辑消息内容以满足您的需求。

   >[注意]
   >
   >指向放弃购物车的链接是指向外部URL的链接，该URL会将用户重定向到其购物车。 此参数未在Adobe Campaign中管理。

1. 在此示例中，您要添加您在创建事件时定义 [的三个字段](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message): first name, last product confisured, total cart amount. 为此，请在 [邮件内容中插入](../../designing/using/personalization.md#inserting-a-personalization-field) “个性化”字段。

1. 通过> >浏览到这 **[!UICONTROL Context]** 些 **[!UICONTROL Real-time event]** 字段 **[!UICONTROL Event context]**。

   ![](assets/message-center_7.png)

1. 要丰富消息内容，请从您与事件链接的表中选择字段来添加字段。 在我们的示例中， **[!UICONTROL Title (salutation)]** 通过> **[!UICONTROL Profile]** >选择表 **[!UICONTROL Context]** 中的字 **[!UICONTROL Real-time event]** 段 **[!UICONTROL Event context]**。

   ![](assets/message-center_7-enrichment.png)

1. 插入所有所需字段。

   ![](assets/message-center_8.png)

1. 预览消息，方法是选择您为此事件定义的用户档案。

   预览消息的步骤在预览消息部分 [中有详细介绍](../../sending/using/previewing-messages.md) 。

   ![](assets/message-center_9.png)

   您可以检查个性化字段是否与在测试用户档案中输入的信息匹配。 有关此内容的详细信息，请 [参阅在事务性消息中定义测试用户档案](#defining-a-test-profile-in-a-transactional-message)。

## 在事务性消息中使用产品列表 {#using-product-listings-in-a-transactional-message}

您可以在交易电子邮件的内容中创建引用一个或多个数据收集的产品列表。 例如，在购物车废弃电子邮件中，您可以包含用户离开网站时购物车中的所有产品的列表，以及图像、价格和指向每个产品的链接。

>[!IMPORTANT]
>
>只有在通过电子邮件设计器界面编辑交易电子邮件时，产品 [列表才可](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface) 用。

要在事务性消息中添加已放弃产品的列表，请执行以下步骤。

您还可以观看一组视频，说明在交易电子邮件中配置产品列表所需的步骤。 For more on this, see [this page](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/product-listings-in-transactional-email.html).

>[!NOTE]
>
>Adobe Campaign不支持嵌套产品列表，这意味着您不能将产品列表包含在另一个产品列表中。

### 定义产品列表 {#defining-a-product-listing}

在事务性消息中使用产品列表之前，您需要在事件层定义产品列表以及要显示的列表的每个产品的字段。 有关此方面的详细信息，请参 [阅定义数据集](../../administration/using/configuring-transactional-messaging.md#defining-data-collections)。

1. 在事务性消息中，单击 **[!UICONTROL Content]** 块以修改电子邮件内容。
1. 将结构组件拖放到工作区。 有关此方面的详细信息，请 [参阅编辑电子邮件结构](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

   例如，选择一列结构组件并添加文本组件、图像组件和按钮组件。 有关此方面的详细信息，请 [参阅添加片段和组件](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

1. 选择刚刚创建的结构组件，然后单击上 **[!UICONTROL Enable product listing]** 下文工具栏中的图标。

   ![](assets/message-center_loop_create.png)

   结构组件以橙色框架高亮显示，设 **[!UICONTROL Product listing]** 置显示在左侧调色板中。

   ![](assets/message-center_loop_palette.png)

1. 选择集合元素的显示方式：

   * **[!UICONTROL Row]**: 水平，表示一行中另一行的每个元素。
   * **[!UICONTROL Column]**: 垂直，即同一行中相邻的每个元素。
   >[!NOTE]
   >
   >仅当 **[!UICONTROL Column]** 使用多列结构组件（、和） **[!UICONTROL 2:2 column]**&#x200B;时， **[!UICONTROL 3:3 column]** 此选项才 **[!UICONTROL 4:4 column]** 可用。 编辑产品列表时，仅填写第一列： 其他列将不被考虑在内。 有关选择结构组件的详细信息，请参 [阅编辑电子邮件结构](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

1. 选择配置与事件相关的事务性消息时创建的数据收集。 您可以在> >节点 **[!UICONTROL Context]** 下 **[!UICONTROL Real-time event]** 找到 **[!UICONTROL Event context]** 它。

   ![](assets/message-center_loop_selection.png)

   有关配置事件的详细信息，请参 [阅定义数据集](../../administration/using/configuring-transactional-messaging.md#defining-data-collections)。

1. 使用下 **[!UICONTROL First item]** 拉列表选择将开始电子邮件中显示的列表的元素。

   例如，如果您选择2，则集合的第一个项目将不会显示在电子邮件中。 产品列表将开始第二个项目。

1. 选择要在列表中显示的最大项目数。

   >[!NOTE]
   >
   >如果希望垂直显示列表的元素( **[!UICONTROL Column]** )，则最大项数会根据选定的结构组件（2列、3列或4列）而有所限制。 有关选择结构组件的详细信息，请参 [阅编辑电子邮件结构](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

### 填充产品列表 {#populating-the-product-listing}

要显示来自链接到交易电子邮件的列表的事件的产品，请执行以下步骤。

有关在配置事件时创建集合和相关字段的详细信息，请参 [阅定义数据集合](../../administration/using/configuring-transactional-messaging.md#defining-data-collections)。

1. 选择您插入的图像组件，选 **[!UICONTROL Enable personalization]** 择并单击“设置”窗格中的铅笔。

   ![](assets/message-center_loop_image.png)

1. 在打 **[!UICONTROL Add personalization field]** 开的 **[!UICONTROL Image source URL]** 窗口中选择。

   从> **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** 节点 **[!UICONTROL Event context]** 中，打开与您创建的集合（此处）对应的节点，然后 **[!UICONTROL Product list]** 选择您定义的图像字段(此处 **[!UICONTROL Product image]** )。 单击 **[!UICONTROL Save]**.

   ![](assets/message-center_loop_product-image.png)

   您选择的个性化字段现在显示在设置窗格中。

1. 在所需位置，从上下文 **[!UICONTROL Insert personalization field]** 工具栏中进行选择。

   ![](assets/message-center_loop_product.png)

1. 从> **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** 节点 **[!UICONTROL Event context]** 中，打开与您创建的集合（此处）对应的节点，然后 **[!UICONTROL Product list]** 选择您创建的字段(此处 **[!UICONTROL Product name]** )。 单击 **[!UICONTROL Confirm]**.

   ![](assets/message-center_loop_product_node.png)

   您选择的个性化字段现在显示在电子邮件内容中的所需位置。

1. 以类似方式继续插入价格。
1. 选择一些文本，然后从上 **[!UICONTROL Insert link]** 下文工具栏中进行选择。

   ![](assets/message-center_loop_link_insert.png)

1. 在打 **[!UICONTROL Add personalization field]** 开的 **[!UICONTROL Insert link]** 窗口中选择。

   从> **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** 节点 **[!UICONTROL Event context]** 中，打开与您创建的集合（此处）对应的节点，然 **[!UICONTROL Product list]** 后选择您创建的URL字段(此处 **[!UICONTROL Product URL]** )。 单击 **[!UICONTROL Save]**.

   >[!IMPORTANT]
   >
   >出于安全原因，请确保将个性化字段插入以正确静态域名开头的链接中。

   ![](assets/message-center_loop_link_select.png)

   您选择的个性化字段现在显示在设置窗格中。

1. 选择应用产品列表的结构组件，然后选 **[!UICONTROL Show fallback]** 择以定义默认内容。

   ![](assets/message-center_loop_fallback_show.png)

1. 拖动一个或多个内容组件并根据需要进行编辑。

   ![](assets/message-center_loop_fallback.png)

   如果事件被触发时集合为空，将显示回退内容，例如，如果客户购物车中没有任何内容。

1. 在“设置”窗格中，编辑产品列表的样式。 有关此方面的详细信息，请参阅 [编辑电子邮件样式](../../designing/using/styles.md)。
1. 使用链接至相关事务预览的测试用户档案事件电子邮件，您为其定义了收集数据。 例如，在要使用的测试用户档案 **[!UICONTROL Event data]** 的部分中添加以下信息：

   ![](assets/message-center_loop_test-profile_payload.png)

   有关在事务性消息中定义测试用户档案的详细信息，请参 [阅本节](#defining-a-test-profile-in-a-transactional-message)。

## 测试事务性消息 {#testing-a-transactional-message}

保存事务性消息后，现在可以发送验证进行测试。

![](assets/message-center_10.png)

发送验证的步骤详见发送 [验证部分](../../sending/using/sending-proofs.md) 。

## 发布事务性消息 {#publishing-a-transactional-message}

检查事务性消息后，即可发布。

![](assets/message-center_12.png)

现在，一旦触发“购物车废弃”事件，它会自动提示一条消息，其中包含收件人的标题和姓氏、购物车URL、最后咨询的产品或列表产品（如果您定义了产品列表）以及要发送的购物车总金额。

要访问有关事务性消息的报告，请使用 **[!UICONTROL Reports]** 按钮。 请参阅 [报告](../../reporting/using/about-dynamic-reports.md)。

![](assets/message-center_13.png)

## 暂停事务性消息发布 {#suspending-a-transactional-message-publication}

例如，可以使用按钮来 **[!UICONTROL Pause]** 暂停发布事务性消息，以修改消息中包含的数据。 因此，事件不再被处理，而是保留在Adobe Campaign数据库的队列中。

排队的事件在REST API中定义的时间段(请参阅 [REST API文档](../../api/using/get-started-apis.md))内保留，如果您使用触发器核心服务 [，则保留在触发器事件中(请参阅](../../integrating/using/about-adobe-experience-cloud-triggers.md)使用活动和Experience Cloud触发器)。

![](assets/message-center_pause.png)

单击时 **[!UICONTROL Resume]**，将处理所有已排队的事件（前提是它们未过期）。 它们现在包含暂停模板发布时执行的所有修改。

## 取消发布事务性消息 {#unpublishing-a-transactional-message}

单 **[!UICONTROL Unpublish]** 击可取消事务性消息发布，也可取消相应事件的发布，从REST API中删除与之前创建的事件对应的资源。

![](assets/message-center_unpublish-template.png)

现在，即使事件是通过您的网站触发的，相应的消息也不再发送，也不会存储在数据库中。

>[!NOTE]
>
>要再次发布消息，您需要返回到相应的事件配置，发布消息，然后发布消息。 有关此内容的详细信息，请 [参阅发布事务性消息](#publishing-a-transactional-message)。

如果取消发布已暂停的事务性消息，则可能需要等待最多24小时，才能再次发布它。 这样，该工作流 **[!UICONTROL Database cleanup]** 将清理发送到队列的所有事件。

暂停消息的步骤详见暂停 [事务性消息发布部分](#suspending-a-transactional-message-publication) 。

每 **[!UICONTROL Database cleanup]** 天凌晨4点运行的工作流可通过> > **[!UICONTROL Administration]** 访 **[!UICONTROL Application settings]** 问 **[!UICONTROL Workflows]**。

## 删除事务性消息 {#deleting-a-transactional-message}

事务性消息取消发布后，或者事务性消息尚未发布，您可以从事务性消息列表中删除它。 操作步骤：

1. 单击左 **[!UICONTROL Adobe Campaign]** 上角的标志，然后选择 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**。
1. 将鼠标悬停在您选择的消息上。
1. Click the **[!UICONTROL Delete element]** button.

![](assets/message-center_delete-template.png)

但是，删除事务性消息只能在某些条件下完成：

* 确保事务性消息具有 **[!UICONTROL Draft]** 状态，否则您将无法删除它。 状态 **[!UICONTROL Draft]** 适用于尚未发布或已取消发布(且未暂 [停](#unpublishing-a-transactional-message) )的 [消息](#suspending-a-transactional-message-publication)。

* **事务性消息**: 除非将其他事务性消息链接到相应的事件，否则如果事务性消息已取消发布，则还需要取消发布事件配置以成功删除事务性消息。 有关此内容的详细信息，请参 [阅取消发布事件](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event)。

   >[!IMPORTANT]
   >
   >删除已发送通知的事务性消息也会删除其发送和跟踪日志。

* **事务性消息来自现成事件模板(内部事务性消息)**: 如果内部事务性消息是与相应内部事件关联的唯一一个，则无法删除该内部。 必须首先复制事务性消息或通过> >菜单创建 **[!UICONTROL Resources]** 其 **[!UICONTROL Templates]** 他 **[!UICONTROL Transactional message templates]** 。

## 事务性消息重试过程 {#transactional-message-retry-process}

临时未交付的事务性消息受到自动重试的约束，这些自动投放会一直执行到过期为止。 有关投放持续时间的详细信息，请参 [阅有效性期间参数](../../administration/using/configuring-email-channel.md#validity-period-parameters)。

当事务性消息无法发送时，有两个重试系统：

* 在事务性消息传递级别，事务性消息在被分配给执行投放之前可能失败，这意味着在事件接收和投放准备之间。 请参 [阅事件处理重试过程](#event-processing-retry-process)。
* 在发送进程级别，一旦事件被分配给执行投放,事务性消息可能因临时错误而失败。 请参 [阅消息发送重试过程](#message-sending-retry-process)。

### 事件处理重试过程 {#event-processing-retry-process}

如果事件无法分配给执行投放，则延迟事件处理。 然后执行重试，直到将其分配给新的执行投放。

>[!NOTE]
>
>延迟的事件不会显示在事务性消息发送日志中，因为尚未将其分配给执行投放。

例如，无法将事件分配给执行投放，因为其内容不正确，存在访问权限或品牌问题，在应用类型规则等时检测到错误。 在这种情况下，您可以暂停消息，编辑该消息以修复问题，然后再次发布它。 然后，重试系统会将其分配给新的执行投放。

### 消息发送重试进程 {#message-sending-retry-process}

一旦事件被分配给执行投放,事务性消息就可能因临时错误而失败，例如，如果收件人邮箱已满。 有关详细信息，请参 [阅投放临时故障后的重试](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)。

>[!NOTE]
>
>将事件分配给执行投放后，该会显示在此执行投放的发送日志中，并且仅在此时显示。 失败的投放显示在 **[!UICONTROL Execution list]** 事务性消息的选项卡中。

### 限制 {#limitations}

**发送日志更新**

在重试过程中，不会立即更新新执行投放的发送日志（更新是通过计划的工作流执行的）。 这意味着即使事务事件已 **[!UICONTROL Pending]** 经由新的执行投放处理，消息也可能处于状态。

**执行投放失败**

无法停止执行投放。 但是，如果当前执行投放失败，则在收到新事件后立即创建新事件，所有新都由此新执行投放处理。 失败的执行事件不会处理任何新投放。

如果已分配给执行投放的某些事件已被延迟，并且如果该执行投放失败，则重试系统不会将延迟的事件分配给新的执行投放，这意味着这些事件丢失。
