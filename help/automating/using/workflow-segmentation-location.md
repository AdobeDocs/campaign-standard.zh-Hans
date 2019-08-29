---
title: “工作流程使用案例：关于位置的分段”
seo-title: “工作流程使用案例：关于位置的分段”
description: “工作流程使用案例：关于位置的分段”
seo-description: “工作流程使用案例：关于位置的分段”
page-status-flag: 从未激活
uuid: 396a3de1-6ffa-4385-ac9 f-15fdeae5 a366
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 执行活动
discoiquuid: 377821e6-69f8-41cc-a1 ad-8a2 f5 ed4 d409
context-tags: '工作流，用例，查询，分段，交付 '
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: e77c8a65834009f2f7157d9535ae8e12e59244ff

---


# 工作流使用案例：关于位置的分段 {#segmentation-on-location}

您可以在本地商店向客户发送定位电子邮件。

1. 在中 **[!UICONTROL Marketing Activities]**，单击 **[!UICONTROL Create]** 并选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]** 工作流类型，然后单击 **[!UICONTROL Next]**。
1. 输入工作流的属性并单击 **[!UICONTROL Create]**。

## 通过电子邮件选择收件人联系{#selecting-recipients-contactable-via-email}

1. 在 **[!UICONTROL Activities]** &gt;中 **[!UICONTROL Targeting]**，拖放a **[!UICONTROL Query activity]**![](assets/query.png)。
1. 双击活动。
1. 在中 **[!UICONTROL Shortcuts]**，拖放 **[!UICONTROL Profiles]** 并选择 **[!UICONTROL email]** 操作符 **[!UICONTROL is not empty]**。
1. 在中 **[!UICONTROL Shortcuts]**，拖放 **[!UICONTROL Profiles]** 并选择具有该值 **[!UICONTROL no longer contact by email]****[!UICONTROL no]**&#x200B;的字段。
1. 点击 **[!UICONTROL Confirm]** 两次。

## 创建分段活动{#creating-a-segmentation-activity}

1. 拖放某个 **[!UICONTROL Segmentation]** 活动，然后双击它。
1. 单击区段，然后打开过渡以定位第一个城市的人员。波士顿。
1. 拖放 **[!UICONTROL Location]** 并 **[!UICONTROL City]** 使用运算符 **[!UICONTROL equals to]** 和值进行选择 **[!UICONTROL Boston]**。
注意：要触及进入波士顿的所有人员，不考虑案例可取消选中区分大小写的选项。
1. Click **[!UICONTROL Confirm]**.
1. 在中 **[!UICONTROL List of outbound segments]**，单击 **[!UICONTROL Add an element]** 并单击 ![](assets/edit_darkgrey-24px.png) 以创建定位第二个城市中的人员的区段。芝加哥。
1. 拖放 **[!UICONTROL Location]** 并 **[!UICONTROL City]** 使用运算符 **[!UICONTROL equals to]** 进行选择，然后输入 **[!UICONTROL Chicago]** 值。
1. 为了接触进入芝加哥的所有人员，不考虑案例可取消选中区分大小写的选项。
1. Click **[!UICONTROL Confirm]**.

## 创建电子邮件分发{#creating-an-email-delivery}

1. 在 **[!UICONTROL Activities]** &gt;中 **[!UICONTROL Channels]**，拖放每个区段 **[!UICONTROL Email Delivery]** 之后的一个。
1. 单击活动并选择 ![](assets/edit_darkgrey-24px.png) 编辑。
1. 选择 **[!UICONTROL Simple email]** 并单击 **[!UICONTROL Next]**。
1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件的布局，请单击 **[!UICONTROL Email Designer]**。
1. 插入元素或选择现有模板。
1. 通过特定于每个位置的选件个性化您的电子邮件。

有关更多信息，请参阅 [设计电子邮件](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch)。

1. 单击 **[!UICONTROL Preview]** 以检查布局。
1. Click **[!UICONTROL Save]**.

**相关主题：**

* [查询活动](../../automating/using/query.md)
* [分段活动](../../automating/using/segmentation.md)
* [电子邮件发送](../../automating/using/email-delivery.md)
