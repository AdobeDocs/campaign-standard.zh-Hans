---
solution: Campaign Standard
product: campaign
title: 编辑事务性消息
description: 了解如何访问、编辑和个性化事务性消息。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: 交易消息传递
role: 业务从业者
level: 中间
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 30%

---


# 编辑事务性消息 {#editing-transactional-message}

创建并发布事件<!--(the cart abandonment example as explained in [this section](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle))-->后，将自动创建相应的事务性消息。

配置和发布事件的步骤在[配置事务事件](../../channels/using/configuring-transactional-event.md)和[发布事务事件](../../channels/using/publishing-transactional-event.md)部分中介绍。

访问、编辑和个性化此消息的步骤如下所述。

>[!IMPORTANT]
>
>只有具有[管理](../../administration/using/users-management.md#functional-administrators)角色的用户才能访问和编辑事务性消息。

消息准备就绪后，即可对其进行测试和发布。 请参阅[测试事务性消息](../../channels/using/testing-transactional-message.md)和[事务性消息生命周期](../../channels/using/publishing-transactional-message.md)。

## 访问事务性消息{#accessing-transactional-messages}

要访问您创建的事务性消息:

1. 单击左上角的&#x200B;**[!UICONTROL Adobe Campaign]**&#x200B;徽标。
1. 选择&#x200B;**[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**。

   ![](assets/message-center_4.png)

1. 单击您选择的消息进行编辑。

   ![](assets/message-center_message-board.png)

您还可以通过位于相应事务性消息配置屏幕左侧区域的链接直接访问事件。 请参阅[预览和发布事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)

## 个性化事务型消息{#personalizing-a-transactional-message}

要编辑和个性化事务性消息，请执行以下步骤。

>[!NOTE]
>
>本节介绍如何编辑&#x200B;**基于事件的**&#x200B;事务性消息。 **基于用户档案的**&#x200B;事务性消息特性详细如下[。](#profile-transactional-message-specificities)
>
>创建基于事件的事务性消息的配置步骤显示在[本节](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages)中。

例如，您希望向已将产品添加到购物车并离开网站的网站用户发送通知，而不进行购买。 此示例在[Transactional messaging operating prinice](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)部分中介绍。

1. 单击 **[!UICONTROL Content]** 块以修改消息的主题和内容。对于本示例，可选择包含图像和文本的任意模板。有关电子邮件内容模板的详细信息，请参阅[使用模板设计电子邮件](../../designing/using/using-reusable-content.md#designing-templates)。

   ![](assets/message-center_6.png)

1. 根据需要，添加主题并编辑消息内容。

   >[!NOTE]
   >
   >指向放弃购物车的链接是指向外部 URL 的链接，会将用户重定向到其购物车。此参数不在 Adobe Campaign 中管理。

1. 在本例中，您要添加在[创建事件](../../channels/using/configuring-transactional-event.md)时定义的三个字段：名字、查看的最后一个产品、购物车总金额。要实现此目的，请在消息内容中[插入个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)。

1. 通过 **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** 浏览这些字段。

   ![](assets/message-center_7.png)

1. 您还可以丰富消息的内容。 为此，请从您链接到事件配置的表中添加字段(请参阅[丰富事件](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content))。 在此示例中，从&#x200B;**[!UICONTROL Profile]**&#x200B;表中选择&#x200B;**[!UICONTROL Title (salutation)]**&#x200B;字段，通过&#x200B;**[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**。

   ![](assets/message-center_7-enrichment.png)

1. 插入所有需要的字段。

   ![](assets/message-center_8.png)

1. 选择为此事件定义的用户档案，预览消息。

   有关预览消息的详细步骤，请参阅[预览消息](../../sending/using/previewing-messages.md)一节。

   ![](assets/message-center_9.png)

   您可以检查个性化字段是否与在测试用户档案中输入的信息匹配。有关详细信息，请参阅[定义特定测试用户档案](../../channels/using/testing-transactional-message.md#defining-specific-test-profile)。

<!--## Using product listings in a transactional message {#using-product-listings-in-a-transactional-message}

When editing the content of a transactional email, you can create product listings referencing one or more data collections. For example, in a cart abandonment email, you can include a list of all products that were in the users' carts when they left your website, with an image, the price, and a link to each product.

>[!IMPORTANT]
>
>Product listings are only available for the email channel, when editing transactional email content through the [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface) interface.

To add a list of abandoned products in a transactional message, follow the steps below.

You can also watch [this set of videos](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/designing-content/product-listings-in-transactional-email.html?lang=en#configure-product-listings-in-transactional-emails) explaining the steps that are required to configure product listings in a transactional email.

>[!NOTE]
>
>Adobe Campaign does not support nested product listings, meaning that you cannot include a product listing inside another one.

### Defining a product listing {#defining-a-product-listing}

Before being able to use a product listing in a transactional message, you need to define at the event level the list of products and the fields for each product of the list you want to display. For more on this, see [Defining data collections](../../channels/using/configuring-transactional-event.md#defining-data-collections).

1. In the transactional message, click the **[!UICONTROL Content]** block to modify the email content.
1. Drag and drop a structure component to the workspace. For more on this, see [Defining the email structure](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

   For example, select a one-column structure component and add a text component, an image component and a button component. For more on this, see [Using content components](../../designing/using/designing-from-scratch.md#about-content-components).

1. Select the structure component you just created and click the **[!UICONTROL Enable product listing]** icon from the contextual toolbar.

   ![](assets/message-center_loop_create.png)

   The structure component is highlighted with an orange frame and the **[!UICONTROL Product listing]** settings are displayed in the left palette.

   ![](assets/message-center_loop_palette.png)

1. Select how the elements of the collection will be displayed:

    * **[!UICONTROL Row]**: horizontally, meaning each element on one row under the other.
    * **[!UICONTROL Column]**: vertically, meaning each element next to the other on the same row.

   >[!NOTE]
   >
   >The **[!UICONTROL Column]** option is only available when using a multicolumn structure component ( **[!UICONTROL 2:2 column]**, **[!UICONTROL 3:3 column]** and **[!UICONTROL 4:4 column]** ). When editing the product listing, only fill in the first column: the other columns will not be taken into account. For more on selecting structure components, see [Defining the email structure](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

1. Select the data collection you created when configuring the event related to the transactional message. You can find it under the **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** node.

   ![](assets/message-center_loop_selection.png)

   For more on configuring the event, see [Defining data collections](../../channels/using/configuring-transactional-event.md#defining-data-collections).

1. Use the **[!UICONTROL First item]** drop-down list to select which element will start the list displayed in the email.

   For example, if you select 2, the first item of the collection will not be displayed in the email. The product listing will start on the second item.

1. Select the maximum number of items to display in the list.

   >[!NOTE]
   >
   >If you want the elements of your list to be displayed vertically ( **[!UICONTROL Column]** ), the maximum number of items is limited according to the selected structure component (2, 3 or 4 columns). For more on selecting structure components, see [Editing the email structure](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

### Populating the product listing {#populating-the-product-listing}

To display a list of products coming from the event linked to the transactional email, follow the steps below.

For more on creating a collection and related fields when configuring the event, see [Defining data collections](../../channels/using/configuring-transactional-event.md#defining-data-collections).

1. Select the image component you inserted, select **[!UICONTROL Enable personalization]** and click the pencil in the Settings pane.

   ![](assets/message-center_loop_image.png)

1. Select **[!UICONTROL Add personalization field]** in the **[!UICONTROL Image source URL]** window that opens.

   From the **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** node, open the node corresponding to the collection that you created (here **[!UICONTROL Product list]** ) and select the image field that you defined (here **[!UICONTROL Product image]** ). Click **[!UICONTROL Save]**.

   ![](assets/message-center_loop_product-image.png)

   The personalization field that you selected is now displayed in the Settings pane.

1. At the desired position, select **[!UICONTROL Insert personalization field]** from the contextual toolbar.

   ![](assets/message-center_loop_product.png)

1. From the **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** node, open the node corresponding to the collection that you created (here **[!UICONTROL Product list]** ) and select the field that you created (here **[!UICONTROL Product name]** ). Click **[!UICONTROL Confirm]**.

   ![](assets/message-center_loop_product_node.png)

   The personalization field that you selected is now displayed at the desired position in the email content.

1. Proceed similarly to insert the price.
1. Select some text and select **[!UICONTROL Insert link]** from the contextual toolbar.

   ![](assets/message-center_loop_link_insert.png)

1. Select **[!UICONTROL Add personalization field]** in the **[!UICONTROL Insert link]** window that opens.

   From the **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** node, open the node corresponding to the collection that you created (here **[!UICONTROL Product list]** ) and select the URL field that you created (here **[!UICONTROL Product URL]** ). Click **[!UICONTROL Save]**.

   >[!IMPORTANT]
   >
   >For security reasons, make sure you insert the personalization field inside a link starting with a proper static domain name.

   ![](assets/message-center_loop_link_select.png)

   The personalization field that you selected is now displayed in the Settings pane.

1. Select the structure component on which the product listing is applied and select **[!UICONTROL Show fallback]** to define a default content.

   ![](assets/message-center_loop_fallback_show.png)

1. Drag one or more content components and edit them as needed.

   ![](assets/message-center_loop_fallback.png)

   The fallback content will be displayed if the collection is empty when the event is triggered, for example if a customer has nothing in his cart.

1. From the Settings pane, edit the styles for the product listing. For more on this, see [Managing email styles](../../designing/using/styles.md).
1. Preview the email using a test profile linked to the relevant transactional event and for which you defined collection data. For example, add the following information in the **[!UICONTROL Event data]** section for the test profile you want to use:

   ![](assets/message-center_loop_test-profile_payload.png)

   For more on defining a test profile in a transactional message, see [this section](../../channels/using/testing-transactional-message.md#defining-specific-test-profile).-->

## 基于用户档案的事务性消息特性{#profile-transactional-message-specificities}

您可以根据客户营销用户档案发送事务性消息，这使您能够利用所有用户档案信息来个性化消息内容，使用退订链接，并应用[疲劳规则](../../sending/using/fatigue-rules.md)等营销类型规则。

* 有关基于事件的事务性消息和基于用户档案的之间差异的详细信息，请参阅[本节](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types)。

* 创建基于用户档案的事务性消息的配置步骤详见[本节](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages)。

创建、编辑和个性化用户档案事务性消息的步骤与创建事件事务性消息的步骤基本相同。

下方列出了两者之间的差异。

1. [请转至创建的事务型消息以对其进行编辑。](#accessing-transactional-messages)
1. 在事务型消息中，单击 **[!UICONTROL Content]** 部分。除了事务性电子邮件模板之外，您还可以选择任何面向&#x200B;**[!UICONTROL Profile]**&#x200B;资源的电子邮件模板。

   ![](assets/message-center_marketing_templates.png)

1. 选择默认电子邮件模板。与所有营销电子邮件类似，它包含&#x200B;**退订链接**。

   ![](assets/message-center_marketing_perso_unsubscription.png)

   有关模板的详细信息，请参阅[此部分](../../designing/using/using-reusable-content.md#content-templates)。

1. 此外，与基于实时事件的配置不同，您可以&#x200B;**直接访问所有用户档案信息**&#x200B;来个性化您的消息。 您可以像添加任何其他标准营销电子邮件一样添加[个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)。

1. 在发布消息之前保存更改。 有关更多信息，请参阅[发布事务型消息](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)。

<!--### Monitoring a profile transactional message delivery {#monitoring-a-profile-transactional-message-delivery}

Once the message is published and your site integration is done, you can monitor the delivery.

1. To view the message delivery log, click the icon at the bottom right of the **[!UICONTROL Deployment]** block.

1. Click the **[!UICONTROL Execution list]** tab.

   ![](assets/message-center_execution_tab.png)

1. Select the latest execution delivery.

   An **execution delivery** is a non-actionable and non-functional technical message created once a month for each transactional message, and each time a transactional message is edited and published again

1. Select the **[!UICONTROL Sending logs]** tab. In the **[!UICONTROL Status]** column, **[!UICONTROL Sent]** indicates that a profile has opted in.

   ![](assets/message-center_marketing_sending_logs.png)

1. Select the **[!UICONTROL Exclusions logs]** tab to view recipients who have been excluded from the message target, such as addresses on denylist.

   ![](assets/message-center_marketing_exclusion_logs.png)

>[!NOTE]
>
>For more information on accessing and using the logs, see [Monitoring a delivery](../../sending/using/monitoring-a-delivery.md).

For any profile that has opted out, the **[!UICONTROL Address on denylist]** typology rule excluded the corresponding recipient.

This rule is part of a specific typology that applies to all transactional messages based on the **[!UICONTROL Profile]** table.

![](assets/message-center_marketing_typology.png)

**Related topics**:

* [Integrate the event triggering](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)
* [About typologies and typology rules](../../sending/using/about-typology-rules.md)-->
