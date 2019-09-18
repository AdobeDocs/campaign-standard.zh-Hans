---
title: “工作流用例：位置细分”
seo-title: “工作流用例：位置细分”
description: “工作流用例：位置细分”
seo-description: “工作流用例：位置细分”
page-status-flag: 从未激活
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 执行活动
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: '工作流，用例，查询，分段，交付 '
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7e56dcb4c2bbdc802c9d271d4a44d9a72b239ed

---


# 工作流用例：位置细分 {#segmentation-on-location}

您可以向客户发送定位电子邮件，并在其当地商店提供推广信息。

1. 在中， **[!UICONTROL Marketing Activities]**&#x200B;单击并 **[!UICONTROL Create]** 选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]** 为工作流类型，然后单击 **[!UICONTROL Next]**。
1. 输入工作流的属性，然后单击 **[!UICONTROL Create]**。

## 通过电子邮件选择可联系的收件人{#selecting-recipients-contactable-via-email}

1. 在 **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**&#x200B;中，拖放 **[!UICONTROL Query activity]**![](assets/query.png)。
1. 双击活动。
1. 在 **[!UICONTROL Shortcuts]**&#x200B;中，拖放并 **[!UICONTROL Profiles]** 使用运算符选 **[!UICONTROL email]** 择字段 **[!UICONTROL is not empty]**。
1. 在 **[!UICONTROL Shortcuts]**&#x200B;中，拖放并 **[!UICONTROL Profiles]** 选择包含值 **[!UICONTROL no longer contact by email]** 的字段 **[!UICONTROL no]**。
1. 单击 **[!UICONTROL Confirm]** 两次。

![](assets/wf-complement-query.png)

## 创建分段活动{#creating-a-segmentation-activity}

1. 拖放活动 **[!UICONTROL Segmentation]** 并双击它。
1. 单击区段，然后打开过渡以定位第一个城市中的人群。 波士顿。
1. 拖放并 **[!UICONTROL Location]** 使用运 **[!UICONTROL City]** 算符和值 **[!UICONTROL equals to]** 进行选择 **[!UICONTROL Boston]**。
注意：要联系所有进入波士顿的人员，请取消选中区分大小写的选项。
1. Click **[!UICONTROL Confirm]**.
1. 在中 **[!UICONTROL List of outbound segments]**，单 **[!UICONTROL Add an element]** 击并单击以 ![](assets/edit_darkgrey-24px.png) 创建一个针对第二个城市人群的细分。 芝加哥。
1. 拖放并 **[!UICONTROL Location]** 使用运 **[!UICONTROL City]** 算符进行选 **[!UICONTROL equals to]** 择，然后输 **[!UICONTROL Chicago]** 入值。
1. 要联系所有进入芝加哥的人员，请取消选中区分大小写的选项。
1. Click **[!UICONTROL Confirm]**.

## 创建电子邮件分发{#creating-an-email-delivery}

1. 在 **[!UICONTROL Activities]** &gt; **[!UICONTROL Channels]**&#x200B;中，将每个区段的 **[!UICONTROL Email Delivery]** 后面拖放一个。
1. 单击活动，然后选择 ![](assets/edit_darkgrey-24px.png) 进行编辑。
1. 选择 **[!UICONTROL Simple email]** 并单击 **[!UICONTROL Next]**。
1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件布局，请单击 **[!UICONTROL Email Designer]**。
1. 插入元素或选择现有模板。
1. 使用特定于每个位置的优惠信息个性化您的电子邮件。

有关详细信息，请参阅 [设计电子邮件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。

1. 单击 **[!UICONTROL Preview]** 以检查您的布局。
1. Click **[!UICONTROL Save]**.

![](assets/wf-segmentation-location.png)

**相关主题：**

* [查询活动](../../automating/using/query.md)
* [细分活动](../../automating/using/segmentation.md)
* [电子邮件发送](../../automating/using/email-delivery.md)
