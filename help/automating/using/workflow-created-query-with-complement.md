---
title: “工作流程使用案例：以补充方式创建交付内容”
seo-title: “工作流程使用案例：以补充方式创建交付内容”
description: “工作流程使用案例：以补充方式创建交付内容”
seo-description: “工作流程使用案例：以补充方式创建交付内容”
page-status-flag: 从未激活
uuid: 396a3de1-6ffa-4385-ac9 f-15fdeae5 a366
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 执行活动
discoiquuid: 377821e6-69f8-41cc-a1 ad-8a2 f5 ed4 d409
context-tags: 工作流程，用例，细分
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: e77c8a65834009f2f7157d9535ae8e12e59244ff

---


# 工作流使用案例：通过补充创建交付 {#deliveries-with-complement}

您可以向客户发送电子邮件：一个针对创建不到一年的客户，一年为客户创建一个。

1. 在中 **[!UICONTROL Marketing Activities]**，单击 **[!UICONTROL Create]** 并选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]** 工作流类型，然后单击 **[!UICONTROL Next]**。
1. 输入工作流的属性并单击 **[!UICONTROL Create]**。

## 创建查询活动 {#create-a-query-activity}

1. 在 **[!UICONTROL Activities]** &gt;中 **[!UICONTROL Targeting]**，拖放a **[!UICONTROL Query activity]**![](assets/query.png)。
1. 双击活动。
1. 在中 **[!UICONTROL Shortcuts]**，拖放 **[!UICONTROL Profiles]** 并 **[!UICONTROL email]** 与操作符进行选择 **[!UICONTROL is not empty]**。
1. 在中 **[!UICONTROL Shortcuts]**，拖放 **[!UICONTROL Profiles]** 并使用 **[!UICONTROL no longer contact by email]** 该值进行选择 **[!UICONTROL no]**。
1. Click **[!UICONTROL Confirm]**.

## 创建分段活动 {#create-a-segmentation-activity}

1. 在 **[!UICONTROL Activities]** &gt;中 **[!UICONTROL Targeting]**，拖放某个 **[!UICONTROL Segmentation]** 活动并双击它。
1. 将鼠标悬停在区段上，然后单击 ![](assets/edit_darkgrey-24px.png) 定位在数据库中今年添加的目标客户。
1. 拖放 **[!UICONTROL Profiles]** 并 **[!UICONTROL Created]** 使用过滤器类型进行选择 **[!UICONTROL Relative]**。
1. 更改 **[!UICONTROL Level of precision]** to **[!UICONTROL Year]** and select **[!UICONTROL This year]**。
1. 点击 **[!UICONTROL Confirm]** 两次。
1. 在中 **[!UICONTROL Advanced Options]**，检查 **[!UICONTROL Generate complement]** 以创建定位其余收件人的区段。
1. Click **[!UICONTROL Confirm]**.
1. Click **[!UICONTROL Save]**.

>[!NOTE]
>
>要观察规则的结构，请单击 **[!UICONTROL Advanced Mode]**。

## 创建电子邮件分发 {#create-an-email-delivery}

1. 在 **[!UICONTROL Activities]** &gt;中 **[!UICONTROL Channels]**，在每个区段之后拖放电子邮件。
1. 单击活动并选择 ![](assets/edit_darkgrey-24px.png) 编辑。
1. 选择 **[!UICONTROL Single send email]** 并单击 **[!UICONTROL Next]**。
1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件的布局，请单击 **[!UICONTROL Email Designer]**。
1. 插入元素或选择现有模板。
1. 通过特定于每个分发的选件个性化您的电子邮件。
1. 单击 **[!UICONTROL Preview]** 以检查布局。
1. Click **[!UICONTROL Save]**.

有关更多信息，请参阅 [设计电子邮件](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch)。

**相关主题：**

* [Query](../../automating/using/query.md)
* [分段活动](../../automating/using/segmentation.md)
* [电子邮件发送](../../automating/using/email-delivery.md)
