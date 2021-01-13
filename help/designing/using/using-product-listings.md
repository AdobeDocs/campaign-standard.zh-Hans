---
solution: Campaign Standard
product: campaign
title: 在事务型消息中使用产品清单
description: 了解如何在事务性消息内容中使用产品列表。
audience: designing
content-type: reference
topic-tags: editing-email-content
context-tags: null
translation-type: tm+mt
source-git-commit: 5758e5f0f6811a97f51e995fa3c378a7c7117ff5
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 82%

---


# 在事务型消息中使用产品清单{#using-product-listings}

>[!IMPORTANT]
>
>产品列表仅可用于通过[电子邮件设计器](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface)界面的&#x200B;**事务电子邮件**。

在编辑交易电子邮件的内容时，您可以创建引用一个或多个数据集合的产品列表。 例如，在购物车废弃电子邮件中，您可以包含用户离开网站时购物车中的所有产品的列表，以及图像、价格和指向每个产品的链接。

要在事务型消息中添加已放弃产品的清单，请执行以下步骤。

您还可以观看[此视频集](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/designing-content/product-listings-in-transactional-email.html?lang=en#configure-product-listings-in-transactional-emails)，说明在交易电子邮件中配置产品列表所需的步骤。

>[!NOTE]
>
>Adobe Campaign 不支持嵌套产品清单，这意味着您不能将一个产品清单包含在另一个产品清单中。

## 定义产品清单{#defining-a-product-listing}

在事务型消息中使用产品清单之前，您需要在事件层级定义产品清单以及要显示的清单中各个产品的字段。有关更多信息，请参阅[定义数据集合](../../channels/using/configuring-transactional-event.md#defining-data-collections)。

1. 在事务型消息中，单击 **[!UICONTROL Content]** 块以修改电子邮件的内容。
1. 将结构组件拖放到工作区。有关此内容的详细信息，请参阅[定义电子邮件结构](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

   例如，选择一列结构组件并添加文本组件、图像组件和按钮组件。有关此内容的详细信息，请参阅[使用内容组件](../../designing/using/designing-from-scratch.md#about-content-components)。

1. 选择之前创建的结构组件，然后单击上下文工具栏中的 **[!UICONTROL Enable product listing]** 图标。

   ![](assets/message-center_loop_create.png)

   结构组件以橙色框突出显示，且 **[!UICONTROL Product listing]** 设置显示在左侧面板中。

   ![](assets/message-center_loop_palette.png)

1. 选择集合元素的显示方式：

   * **[!UICONTROL Row]**：水平，表示每行显示一个元素，逐行排列。
   * **[!UICONTROL Column]**: 垂直，表示使用同一行将各个元素邻近放置。

   >[!NOTE]
   >
   >仅当使用多列结构组件（**[!UICONTROL 2:2 column]**、**[!UICONTROL 3:3 column]** 和 **[!UICONTROL 4:4 column]**）时，才可使用 **[!UICONTROL Column]** 选项。编辑产品清单时，仅填写第一列：不考虑其他列。有关选择结构组件的详细信息，请参阅[定义电子邮件结构](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

1. 选择配置与事务型消息相关的事件时创建的数据集合。您可以通过 **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** 节点找到该数据集合。

   ![](assets/message-center_loop_selection.png)

   有关配置事件的更多信息，请参阅[定义数据集合](../../channels/using/configuring-transactional-event.md#defining-data-collections)。

1. 使用 **[!UICONTROL First item]** 下拉列表选择电子邮件中显示清单的开头元素。

   例如，如果您选择“2”，则集合的第一个项将不会显示在电子邮件中。产品清单将从第二项开始。

1. 选择要在清单中显示的最大项数。

   >[!NOTE]
   >
   >如果希望垂直显示清单中的元素 (**[!UICONTROL Column]**)，则最大项数将根据选则的结构组件（2 列、3 列或 4 列）而有所限制。有关选择结构组件的更多信息，请参阅[编辑电子邮件结构](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

## 填充产品清单{#populating-the-product-listing}

要显示来自事务型电子邮件所链接事件的产品清单，请执行以下步骤。

有关在配置事件时创建集合和相关字段的更多信息，请参阅[定义数据集合](../../channels/using/configuring-transactional-event.md#defining-data-collections)。

1. 选择要插入的图像组件，选择 **[!UICONTROL Enable personalization]** 并单击 Settings 窗格中的铅笔。

   ![](assets/message-center_loop_image.png)

1. 在打开的 **[!UICONTROL Image source URL]** 窗口中选择 **[!UICONTROL Add personalization field]**。

   前往 **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** 节点，打开与您创建的集合对应的节点（此处为 **[!UICONTROL Product list]**），然后选择之前定义的图像字段（此处为 **[!UICONTROL Product image]**）。单击 **[!UICONTROL Save]**。

   ![](assets/message-center_loop_product-image.png)

   现在，您选择的个性化字段即已显示在设置窗格中。

1. 在所需位置，从上下文工具栏中选择&#x200B;**[!UICONTROL Insert personalization field]** 

   ![](assets/message-center_loop_product.png)

1. 前往 **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** 节点，打开与您创建的集合对应的节点（此处为 **[!UICONTROL Product list]**），然后选择之前创建的字段（此处为 **[!UICONTROL Product name]**）。单击 **[!UICONTROL Confirm]**。

   ![](assets/message-center_loop_product_node.png)

   现在，您选择的个性化字段即已显示在电子邮件内容中所需的位置。

1. 接下来以类似方式插入价格。
1. 选择一些文本，然后从上下文工具栏中选择&#x200B;**[!UICONTROL Insert link]** 

   ![](assets/message-center_loop_link_insert.png)

1. 在打开的 **[!UICONTROL Insert link]** 窗口中选择 **[!UICONTROL Add personalization field]**。

   前往 **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** 节点，打开与您创建的集合对应的节点（此处为 **[!UICONTROL Product list]**），然后选择之前创建的 URL 字段（此处为 **[!UICONTROL Product URL]**）。单击 **[!UICONTROL Save]**。

   >[!IMPORTANT]
   >
   >出于安全原因，请确保将个性化字段插入以适当静态域名开头的链接中。

   ![](assets/message-center_loop_link_select.png)

   现在，您选择的个性化字段即已显示在设置窗格中。

1. 选择应用产品清单的结构组件，然后选择 **[!UICONTROL Show fallback]** 以定义默认内容。

   ![](assets/message-center_loop_fallback_show.png)

1. 拖动一个或多个内容组件并根据需要对其进行编辑。

   ![](assets/message-center_loop_fallback.png)

   如果触发事件时集合为空（例如，如果客户购物车中没有任何内容），将显示回退内容。

1. 在“设置”窗格中，编辑产品清单的样式。有关此方面的详细信息，请参阅[管理电子邮件样式](../../designing/using/styles.md)。
1. 使用链接了相关事务型事件并为其定义了集合数据的测试用户档案，预览电子邮件。例如，在要使用的测试用户档案的 **[!UICONTROL Event data]** 部分中添加以下信息：

   ![](assets/message-center_loop_test-profile_payload.png)

   有关定义事务型消息中的测试用户档案的更多信息，请参阅[本章节](../../channels/using/testing-transactional-message.md#defining-specific-test-profile)。