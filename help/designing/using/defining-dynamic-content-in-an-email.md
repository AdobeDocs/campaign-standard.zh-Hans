---
title: 在电子邮件中定义动态内容
seo-title: 在电子邮件中定义动态内容
description: 在电子邮件中定义动态内容
seo-description: 按照这些步骤，根据通过Adobe Campaign表达式编辑器定义的条件动态显示电子邮件中的不同内容。
page-status-flag: 从未激活
uuid: b1c5013f-3201-4239-8202-511a6902d604
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 设计
content-type: reference
topic-tags: 定义条件内容
discoiquuid: d0d009a5-6022-433e-acdf-2b51 a243 a5 c9
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Defining dynamic content in an email{#defining-dynamic-content-in-an-email}

在电子邮件中，您可以定义不同内容，这些内容将根据通过表达式编辑器定义的条件动态显示给收件人。例如，通过同一电子邮件，您可以确保每个配置文件根据其年龄范围接收不同的消息。

Defining dynamic content is different from [defining visibility conditions](../../designing/using/defining-a-visibility-condition.md).

1. 选择片段、组件或元素。在此示例中，选择一幅图像。
1. Click the **[!UICONTROL Dynamic content]** icon from the contextual toolbar.

   ![](assets/dynamic_content_2.png)

   **[!UICONTROL Dynamic content]** 该部分显示在左侧调色板中。

   ![](assets/dynamic_content_3.png)

   默认情况下，此部分包含两个元素：默认变体和新变体。

   >[!NOTE]
   >
   >内容必须始终具有默认变体。无法删除它。

1. Click the **[!UICONTROL Edit]** button to define the display conditions for the first alternative variant.

   ![](assets/dynamic_content_4.png)

1. 指定标签并选择要设置为条件的字段。For example, from the **[!UICONTROL General]** node, select the **[!UICONTROL Age]** field

   ![](assets/dynamic_content_5.png)

1. 设置过滤条件。例如，您希望向年龄在18到25岁之间的用户显示不同的内容。

   ![](assets/dynamic_content_6.png)

1. 设置所有条件后，定义将在其中应用条件的优先级顺序并保存更改。

   ![](assets/dynamic_content_7.png)

   内容将按优先级顺序显示在调色板中，从上到下。For more on priorities, refer to [this section](../../designing/using/defining-dynamic-content-in-an-email.md#order-of-priority).

1. 为刚刚定义的变体上传新图像。

   ![](assets/dynamic_content_8.png)

   年龄在18到25岁之间的收件人将看到新图像。

   ![](assets/dynamic_content_10.png)

1. Click **[!UICONTROL Add a condition]** to add a new content and its linked rule.

   ![](assets/dynamic_content_9.png)

   例如，您可以向年龄在26到35岁之间的用户添加其他图像。

1. 对于要动态显示的电子邮件的任何其他元素继续进行同样的操作。它可以是文本、按钮、片段等。保存更改。

>[!CAUTION]
>
>准备好消息并在发送之前，使用证据测试它。否则，可能无法检测到某些错误，并且可能无法发送电子邮件。

**相关主题：**

* [发送校样](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs)
* [高级表达式编辑](../../automating/using/editing-queries.md#about-query-editor)

## Order of priority {#order-of-priority}

在表达式编辑器中，定义动态内容时，优先级顺序如下所示。

1. You define two different dynamic contents with **two different conditions**, for example:

   **条件1：** 个人资料的性别是骗局，

   **条件2：** 配置文件在20到30年之间。

   ![](assets/delivery_content_61.png)

   数据库中的某些配置文件与两个条件相对应，但只能发送含有一个动态内容的一个电子邮件。

1. 因此，您必须定义动态内容的优先级。A condition with an order of priority of **1** (and therefore the corresponding dynamic content) will be sent to a profile even if another condition whose priority order is **2** or **3** is also met by this profile.

   ![](assets/delivery_content_62.png)

每个动态内容只能定义一个优先级顺序。
