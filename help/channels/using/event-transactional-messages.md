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
source-git-commit: efb1f14e0094e200d186423f98bfad65d25cfab2

---


# 事件交易消息{#event-transactional-messages}

您可以发送事件事务性消息以事件为目标。 此类事务性消息不包含用户档案信息：投放目标由事件本身包含的数据定义。

创建并发布事件后(本节中所述的放弃购物 [车](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle))，将自动创建相应的事务性消息。

配置事件以发送事务性消息部 [分中介绍了配置步骤](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) 。

要使事件触发发送事务性消息，您必须个性化消息，然后测试并发布消息。

>[!NOTE]
>
>要访问事务性消息，您必须是安全组的一 **[!UICONTROL Administrators (all units)]** 部分。
>
>事件事务性消息不包含用户档案信息，因此它们与疲劳规则不兼容(即使与用户档案扩充时)。 请参阅 [疲劳规则](../../sending/using/fatigue-rules.md#choosing-the-channel)。

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

1. 创建之后，将在事务性消息中预先指定测试用户档案。 单击 **[!UICONTROL Test profiles]** 消息块以检查验证的目标。

   ![](assets/message-center_5.png)

### 在事务性消息之外创建测试用户档案 {#creating-a-test-profile-outside-the-transactional-----------message}

您还可以创建新的测试用户档案，或使用菜单中已存在的测试 **[!UICONTROL Test profiles]** 。

1. 单击左 **[!UICONTROL Adobe Campaign]** 上角的徽标，然后选择 **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**。
1. 在您 **[!UICONTROL Event]** 选择的测试用户档案页面的部分中，选择您刚刚创建的事件。 在此示例中，选择“购物车放弃(EVTcartEligation)”。
1. 在文本框中指定要以JSON格式发送 **[!UICONTROL Event data]** 的信息。

   ![](assets/message-center_3.png)

1. 保存更改。

您现在可以访问您创建的消息并选择更新的测试用户档案。

**相关主题：**

* [管理测试用户档案](../../audiences/using/managing-test-profiles.md)
* [定义受众](../../audiences/using/creating-audiences.md)

## 个性化事务性消息 {#personalizing-a-transactional-message}

要在事务性消息中设置个性化，请执行以下步骤：

1. 单击 **[!UICONTROL Content]** 该块以修改邮件的主题和内容。 在此示例中，选择包含图像和文本的任何模板。 有关电子邮件内容模板的详细信息，请参 [阅使用模板设计](../../designing/using/using-reusable-content.md#designing-templates)。

   ![](assets/message-center_6.png)

1. 添加主题并编辑消息内容以满足您的需求。

   >[注意]
   >
   >指向放弃购物车的链接是指向外部URL的链接，该URL会将访客重定向到其购物车。 此参数在Adobe Campaign中不受管理。

1. 在此示例中，您要添加您在创建事件时定义的 [三个字段](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message):first name, last product cansfired, total cart amount. 为此，请在消 [息内容中插入个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field) 。

1. 通过 **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** >浏览到这些字段 **[!UICONTROL Event context]**。

   ![](assets/message-center_7.png)

1. 要丰富消息的内容，请从您与事件链接的表中选择字段，以添加这些字段。 在我们的示例中，通 **[!UICONTROL Title (salutation)]** 过> **[!UICONTROL Profile]** >选择表中的字段 **[!UICONTROL Context]****[!UICONTROL Real-time event]****[!UICONTROL Event context]**。

   ![](assets/message-center_7-enrichment.png)

1. 插入所有所需字段。

   ![](assets/message-center_8.png)

1. 预览消息，方法是选择您为此事件定义的用户档案。

   预览消息的步骤在预览消息部分有 [详细介绍](../../sending/using/previewing-messages.md) 。

   ![](assets/message-center_9.png)

   您可以检查个性化字段是否与在测试用户档案中输入的信息匹配。 有关此问题的详细信息，请 [参阅在事务性消息中定义测试用户档案](#defining-a-test-profile-in-a-transactional-message)。

## 在事务性消息中使用产品列表 {#using-product-listings-in-a-transactional-message}

您可以创建引用交易电子邮件内容中的一个或多个数据集合的产品列表。 例如，在购物车放弃电子邮件中，您可以包含用户离开网站时购物车中的所有产品的列表，以及图像、价格和每个产品的链接。

>[!IMPORTANT]
>
>只有在通过“电子邮件设计器”界面编辑交易电子邮件时，产品列 [表才可用](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface) 。

要在事务性消息中添加已放弃产品的列表，请执行以下步骤。

您还可以观看一组视频，其中介绍了在交易电子邮件中配置产品列表所需的步骤。 For more on this, see [this page](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/product-listings-in-transactional-email.html).

>[!NOTE]
>
>Adobe Campaign不支持嵌套的产品列表，这意味着您不能将产品列表包含在另一个产品列表中。

### 定义产品列表 {#defining-a-product-listing}

在事务性消息中使用产品列表之前，您需要在事件级别定义产品的列表以及要显示的列表的每个产品的字段。 有关此功能的详细信息，请参 [阅定义数据集合](../../administration/using/configuring-transactional-messaging.md#defining-data-collections)。

1. 在事务性消息中，单击该 **[!UICONTROL Content]** 块以修改电子邮件内容。
1. 将结构组件拖放到工作区。 有关此内容的详细信息，请参 [阅编辑电子邮件结构](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

   例如，选择一列结构组件并添加文本组件、图像组件和按钮组件。 有关此方面的详细信息，请参 [阅添加片段和组件](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

1. 选择刚刚创建的结构组件，然后单击上 **[!UICONTROL Enable product listing]** 下文工具栏中的图标。

   ![](assets/message-center_loop_create.png)

   结构组件以橙色框架高亮显示，设 **[!UICONTROL Product listing]** 置显示在左侧调色板中。

   ![](assets/message-center_loop_palette.png)

1. 选择集合元素的显示方式：

   * **[!UICONTROL Row]**:水平，表示位于另一行下的一行上的每个元素。
   * **[!UICONTROL Column]**:垂直，即同一行上的每个元素相邻。
   >[!NOTE]
   >
   >仅 **[!UICONTROL Column]** 当使用多列结构组件（、和）时， **[!UICONTROL 2:2 column]**&#x200B;此选项 **[!UICONTROL 3:3 column]****[!UICONTROL 4:4 column]** 才可用。 编辑产品列表时，仅填写第一列：其他列将不被考虑在内。 有关选择结构组件的详细信息，请参 [阅编辑电子邮件结构](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

1. 选择配置与事件相关的事务性消息时创建的数据收集。 您可以在 **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** >节点下 **[!UICONTROL Event context]** 找到。

   ![](assets/message-center_loop_selection.png)

   有关配置事件的详细信息，请参 [阅定义数据集合](../../administration/using/configuring-transactional-messaging.md#defining-data-collections)。

1. 使用下 **[!UICONTROL First item]** 拉列表选择将开始电子邮件中显示的列表的元素。

   例如，如果选择2，则集合的第一个项目将不会显示在电子邮件中。 产品列表将开始于第二个项目。

1. 选择要在列表中显示的最大项目数。

   >[!NOTE]
   >
   >如果希望垂直显示列表的元素( **[!UICONTROL Column]** )，则根据选定的结构组件（2、3或4列）限制最大项目数。 有关选择结构组件的详细信息，请参 [阅编辑电子邮件结构](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

### 填充产品列表 {#populating-the-product-listing}

要显示来自链接到交易电子邮件的事件的产品列表，请执行以下步骤。

有关在配置事件时创建集合和相关字段的详细信息，请参阅定 [义数据集合](../../administration/using/configuring-transactional-messaging.md#defining-data-collections)。

1. 选择您插入的图像组件，选择 **[!UICONTROL Enable personalization]** 并单击“设置”窗格中的铅笔。

   ![](assets/message-center_loop_image.png)

1. 在打 **[!UICONTROL Add personalization field]** 开的窗 **[!UICONTROL Image source URL]** 口中选择。

   从 **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** >节点 **[!UICONTROL Event context]** 中，打开与您创建的集合对应的节点(此处 **[!UICONTROL Product list]** )，然后选择您定义的图像字段(此处 **[!UICONTROL Product image]** )。 单击 **[!UICONTROL Save]**.

   ![](assets/message-center_loop_product-image.png)

   您选择的个性化字段现在显示在“设置”窗格中。

1. 在所需位置，从上下文工 **[!UICONTROL Insert personalization field]** 具栏中选择。

   ![](assets/message-center_loop_product.png)

1. 从 **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** >节点 **[!UICONTROL Event context]** 中，打开与您创建的集合对应的节点(此处 **[!UICONTROL Product list]** )，然后选择您创建的字段(此处 **[!UICONTROL Product name]** )。 单击 **[!UICONTROL Confirm]**.

   ![](assets/message-center_loop_product_node.png)

   您选择的个性化字段现在显示在电子邮件内容中的所需位置。

1. 以类似方式继续插入价格。
1. 选择一些文本，然后从上 **[!UICONTROL Insert link]** 下文工具栏中进行选择。

   ![](assets/message-center_loop_link_insert.png)

1. 在打 **[!UICONTROL Add personalization field]** 开的窗 **[!UICONTROL Insert link]** 口中选择。

   从 **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** >节点 **[!UICONTROL Event context]** 中，打开与您创建的集合对应的节点(此处 **[!UICONTROL Product list]** )，然后选择您创建的URL字段(此处 **[!UICONTROL Product URL]** )。 单击 **[!UICONTROL Save]**.

   >[!IMPORTANT]
   >
   >出于安全原因，请确保将个性化字段插入以正确的静态域名开头的链接中。

   ![](assets/message-center_loop_link_select.png)

   您选择的个性化字段现在显示在“设置”窗格中。

1. 选择应用产品列表的结构组件，然后选择以 **[!UICONTROL Show fallback]** 定义默认内容。

   ![](assets/message-center_loop_fallback_show.png)

1. 拖动一个或多个内容组件，并根据需要编辑它们。

   ![](assets/message-center_loop_fallback.png)

   当事件被触发时，如果集合为空，将显示回退内容，例如，如果客户购物车中没有任何内容。

1. 从“设置”窗格中，编辑产品列表的样式。 有关此内容的详细信息，请参阅 [编辑电子邮件样式](../../designing/using/styles.md)。
1. 预览电子邮件时，请使用链接到相关交易事件且您为其定义了收集数据的测试用户档案。 例如，在要使用的测试 **[!UICONTROL Event data]** 用户档案的部分中添加以下信息：

   ![](assets/message-center_loop_test-profile_payload.png)

   有关在事务性消息中定义测试用户档案的详细信息，请参 [阅此部分](#defining-a-test-profile-in-a-transactional-message)。

## 测试事务性消息 {#testing-a-transactional-message}

保存事务性消息后，您现在可以发送验证来测试它。

![](assets/message-center_10.png)

发送验证的步骤在发送验证部分 [中有详细介绍](../../sending/using/sending-proofs.md) 。

## 发布事务性消息 {#publishing-a-transactional-message}

检查事务性消息后，即可发布它。

![](assets/message-center_12.png)

现在，一旦触发“购物车放弃”事件，它会自动提示一条消息，其中包含收件人的标题和姓氏、购物车URL、上次咨询的产品或产品列表（如果您定义了产品列表）以及要发送的购物车总数。

要访问有关事务性消息的报告，请使用该 **[!UICONTROL Reports]** 按钮。 请参阅 [报告](../../reporting/using/about-dynamic-reports.md)。

![](assets/message-center_13.png)

## 暂停事务性消息发布 {#suspending-a-transactional-message-publication}

例如，可以使用按钮暂停发 **[!UICONTROL Pause]** 布事务性消息，以修改消息中包含的数据。 因此，事件不再被处理，而是保留在Adobe Campaign数据库的队列中。

排队的事件会在REST API中定义的时间段(请参阅 [REST API文档](../../api/using/about-campaign-standard-apis.md))内保留，如果您使用触发器核心服务，则会保留在触发器事件中(请参阅 [使用活动和Experience Cloud触发器](../../integrating/using/about-adobe-experience-cloud-triggers.md))。

![](assets/message-center_pause.png)

单击时， **[!UICONTROL Resume]**&#x200B;将处理所有已排队的事件（前提是它们未过期）。 现在，它们包含暂停模板发布时执行的所有修改。

## 取消发布事务性消息 {#unpublishing-a-transactional-message}

单 **[!UICONTROL Unpublish]** 击可取消事务性消息发布，也可取消相应事件的发布，该发布从REST API中删除与您先前创建的事件对应的资源。

![](assets/message-center_unpublish-template.png)

现在，即使事件是通过您的网站触发的，相应的消息也不再发送，也不会存储在数据库中。

>[!NOTE]
>
>要再次发布消息，您需要返回到相应的事件配置，发布消息，然后发布消息。 有关此内容的详细信息，请参 [阅发布事务性消息](#publishing-a-transactional-message)。

如果取消发布已暂停的事务性消息，则可能必须等待最多24小时，才能再次发布它。 这样，该工作流 **[!UICONTROL Database cleanup]** 便可清除发送到队列的所有事件。

暂停消息的步骤在暂停事务性消息发布部 [分中有详细介绍](#suspending-a-transactional-message-publication) 。

每 **[!UICONTROL Database cleanup]** 天凌晨4点运行的工作流可通过 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** >访问 **[!UICONTROL Workflows]**。

## 删除事务性消息 {#deleting-a-transactional-message}

事务性消息取消发布后，或者事务性消息尚未发布后，您可以从事务性消息列表中删除该。 操作步骤：

1. 单击左 **[!UICONTROL Adobe Campaign]** 上角的标志，然后选择 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**。
1. 将鼠标悬停在您选择的消息上。
1. Click the **[!UICONTROL Delete element]** button.

![](assets/message-center_delete-template.png)

但是，只有在某些情况下才能删除事务性消息:

* 确保事务性消息具有状 **[!UICONTROL Draft]** 态，否则您将无法删除它。 状 **[!UICONTROL Draft]** 态适用于尚未发布或已取消发布(且未暂停 [](#unpublishing-a-transactional-message) )的 [消息](#suspending-a-transactional-message-publication)。

* **事务性消息**:除非将其他事务性消息链接到相应的事件，否则如果事务性消息已取消发布，则还需要取消发布事件配置才能成功删除事务性消息。 有关此内容的详细信息，请参 [阅取消发布事件](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event)。

   >[!IMPORTANT]
   >
   >删除已发送通知的事务性消息也会删除其发送和跟踪日志。

* **事务性消息自现成事件模板(内部事务性消息)**:如果内部事务性消息是与相应内部事件关联的唯一一个，则无法删除该内部。 必须首先通过复制事务性消息或通过> **[!UICONTROL Resources]****[!UICONTROL Templates]** >菜单创建其他 **[!UICONTROL Transactional message templates]** 。

## 事务性消息重试过程 {#transactional-message-retry-process}

临时未交付的事务性消息受到自动重试的约束，该自动投放在过期之前一直执行。 有关投放持续时间的详细信息，请参 [阅有效性期间参数](../../administration/using/configuring-email-channel.md#validity-period-parameters)。

当事务性消息无法发送时，有两个重试系统：

* 在事务消息处理级别，事务性消息在被分配到执行投放之前可以失败，这意味着在事件接收和投放准备之间。 请参阅 [事件处理重试过程](#event-processing-retry-process)。
* 在发送进程级别，一旦将事件分配给执行投放，该事务性消息就可能因临时错误而失败。 请参阅 [消息发送重试过程](#message-sending-retry-process)。

### 事件处理重试过程 {#event-processing-retry-process}

如果事件不能被分配给执行投放，则事件处理被延迟。 然后执行重试，直到将其分配给新的执行投放。

>[!NOTE]
>
>延迟的事件不会显示在事务性消息发送日志中，因为它尚未分配给执行投放。

例如，无法将事件分配给执行投放，因为其内容不正确，存在访问权限或品牌问题，在应用类型规则等时检测到错误。 在这种情况下，您可以暂停消息，编辑该消息以解决问题，然后再次发布它。 然后，重试系统会将其分配给新的执行投放。

### 消息发送重试进程 {#message-sending-retry-process}

将事件分配给执行投放后，例如，如果收件人邮箱已满，则事务性消息可能会因临时错误而失败。 有关详细信息，请参阅 [投放临时故障后的重试](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)。

>[!NOTE]
>
>将事件分配给执行投放后，该会显示在此执行投放的发送日志中，并且仅在此时显示。 失败的投放显示在事务性消息 **[!UICONTROL Execution list]** 的选项卡中。

### 限制 {#limitations}

**发送日志更新**

在重试过程中，不会立即更新新执行投放的发送日志（更新是通过计划的工作流执行的）。 这意味着即使事务事件已经由 **[!UICONTROL Pending]** 新的执行投放处理，消息也可能处于状态。

**执行投放失败**

无法停止执行投放。 但是，如果当前执行投放失败，则在收到新事件后立即创建新事件，并且所有新都由此新执行投放处理。 失败的执行事件不会处理任何新投放。

如果已分配给执行投放的某些事件已被延迟，并且如果该执行投放失败，则重试系统不会将延迟的事件分配给新的执行投放，这意味着这些事件丢失。
