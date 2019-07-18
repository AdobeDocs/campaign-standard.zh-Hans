---
title: “示例：电子邮件个性化”
seo-title: “示例：电子邮件个性化”
description: “示例：电子邮件个性化”
seo-description: 请参阅一个完整的示例，了解如何根据档案的年龄使用动态内容和文本来个性化电子邮件。
page-status-flag: 从未激活
uuid: 3d30213c-474f-4e5f-8688-9260ea2e2583
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 设计
content-type: reference
topic-tags: 个性化内容
discoiquuid: d1b618ac-a842-41e8-9ba6-7a50 f7315 b02
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Example: Email personalization{#example-email-personalization}

在此示例中，营销服务团队的某个成员创建了一封电子邮件，通知部分客户只针对他们提供了一个特别优惠。团队成员决定根据客户的不同年龄个性化电子邮件。年龄在18到27岁之间的客户将收到一封电子邮件，其中包含与27岁以上的客户的图像和标语不同的电子邮件。

电子邮件的创建如下：

* 动态内容应用于图像，这些动态内容根据年龄范围进行配置。

   ![](assets/delivery_content_43.png)

   Adding and configuring dynamic content is detailed in the [Defining dynamic content in an email](../../designing/using/defining-dynamic-content-in-an-email.md) section.

* 个性化字段和动态内容应用于文本。根据配置文件的年龄范围，电子邮件以配置文件的名字或配置文件的标题和姓氏开头。

   ![](assets/delivery_content_44.png)

   Adding and configuring the personalization fields is detailed in the [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md) section.

## Configuring images {#configuring-images}

在此示例中，应用于图像的动态内容的配置如下：

**To target18-27-year-old：**

1. Select the dynamic content in the **[!UICONTROL Properties]** palette and click the **[!UICONTROL Edit]** button.

   ![](assets/delivery_content_48.png)

1. Edit the label then select the **[!UICONTROL Age]** field from the **[!UICONTROL Profile]** node.

   ![](assets/delivery_content_49.png)

1. Select the **Greater than or equal to** operator then enter **18** to create the **older than 18** expression.

   ![](assets/delivery_content_50.png)

1. Add a new **[!UICONTROL Age]** condition.

   Select the **Less than or equal to** operator followed by 27 in the value field to create the **younger than 27** expression.

   ![](assets/delivery_content_51.png)

1. 确认所做的更改。

**对于旧版本27及以上的配置文件：**

1. 从调色板中选择动态内容并对其进行编辑。
1. Edit the label then select the **[!UICONTROL Age]** field from the **[!UICONTROL Profile]** node.
1. Add the **Greater than** operator followed by 27 in the value field to create the **older than 27** expression.

   ![](assets/delivery_content_52.png)

1. 确认所做的更改。

您的动态内容将得到正确配置。

## Configuring text {#configuring-text}

在此示例中，应用于文本的动态内容如下所示：

**要在18-27之间定位档案，请执行以下操作：**

1. 选择所需的结构组件并添加动态内容。
1. 编辑动态内容并配置定位表达式。Refer to [Configuring images](../../designing/using/example--email-personalization.md#configuring-images).
1. In the structure component, at the desired position, click the **[!UICONTROL Personalize]** icon from the contextual toolbar and select **[!UICONTROL Insert personalization field]**.

   ![](assets/delivery_content_53.png)

1. In the list that appears, select the **[!UICONTROL First name]** field and confirm.

   ![](assets/delivery_content_54.png)

1. 您的个性化字段随后会完美插入选定的动态内容中。

**对于旧版本27及以上的配置文件：**

1. 选择所需的结构组件并添加动态内容。
1. 编辑动态内容并配置定位表达式。Refer to [Configuring images](../../designing/using/example--email-personalization.md#configuring-images).
1. In the structure component, at the desired position, click the **[!UICONTROL Personalize]** icon from the contextual toolbar and select **[!UICONTROL Insert personalization field]**.
1. **[!UICONTROL Title]** 从下拉列表中进行选择。
1. Proceed similarly to add the **[!UICONTROL Last name]** field.

   ![](assets/delivery_content_56.png)

您的个性化字段现在应该完全插入选定的动态内容中。

## Previewing emails {#previewing-emails}

Previewing allows you to check that the personalization fields and the dynamic contents are configured correctly before sending the **[!UICONTROL Proofs]**. 在预览过程中，您可以选择与电子邮件目标对应的不同测试配置文件。

如果没有测试配置文件，默认情况下显示的电子邮件为：

![](assets/delivery_content_45.png)

电子邮件中没有个性化字段，并且使用默认图像。

第一个测试配置文件与在18到27之间的客户端相对应。通过选择此配置文件，将显示以下电子邮件：

![](assets/delivery_content_46.png)

与18-27年表达式对应的个性化字段(尤其是配置文件的名字)可以正确配置，并且图像也会根据配置文件进行更改。

第二个配置文件对应于超过27周岁的客户端，并生成以下电子邮件：

![](assets/delivery_content_47.png)

图像因动态内容而异，而出现的标语是为此目标公开定义的更正式的口号。

**相关主题：**

* [创建受众](../../audiences/using/creating-audiences.md)
* [准备发送](../../sending/using/preparing-the-send.md)

