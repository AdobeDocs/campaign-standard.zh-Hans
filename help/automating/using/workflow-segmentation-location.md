---
title: 位置分段”
description: 此用例说明如何对位置执行分段。
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,segmentation,delivery
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 1%

---


# 位置细分 {#segmentation-on-location}

您可以向在当地商店拥有优惠的客户发送定位电子邮件。

1. 在中 **[!UICONTROL Marketing Activities]**，单击 **[!UICONTROL Create]** 并选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]** 为工作流类型并单击 **[!UICONTROL Next]**。
1. 输入工作流的属性并单击 **[!UICONTROL Create]**。

## 通过电子邮件选择可联系的收件人{#selecting-recipients-contactable-via-email}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**&#x200B;中，拖放一个 [查询](../../automating/using/query.md) 活动 ![](assets/query.png)。
1. 多次单击活动。
1. 在 **[!UICONTROL Shortcuts]**&#x200B;中，拖放并 **[!UICONTROL Profiles]** 使用运算符 **[!UICONTROL email]** 选择字段 **[!UICONTROL is not empty]**。
1. 在 **[!UICONTROL Shortcuts]**&#x200B;中，拖放并 **[!UICONTROL Profiles]** 选择包含值 **[!UICONTROL no longer contact by email]** 的字段 **[!UICONTROL no]**。
1. 单击 **[!UICONTROL Confirm]** 两次。

![](assets/wf-complement-query.png)

## 创建分段活动{#creating-a-segmentation-activity}

1. 拖放分段 [活动](../../automating/using/segmentation.md) ，然后多次单击它。
1. 单击区段，然后打开过渡以目标第一个城市的人。 波士顿。
1. 拖放并 **[!UICONTROL Location]** 使用运 **[!UICONTROL City]** 算符和值 **[!UICONTROL equals to]** 进行选择 **[!UICONTROL Boston]**。
注意： 要联系所有进入波士顿的人员，请取消选中区分大小写选项。
1. 单击 **[!UICONTROL Confirm]**.
1. 在中 **[!UICONTROL List of outbound segments]**，单 **[!UICONTROL Add an element]** 击并单击以 ![](assets/edit_darkgrey-24px.png) 创建一个区段，定位第二个城市的人群。 芝加哥。
1. 拖放并 **[!UICONTROL Location]** 使用运 **[!UICONTROL City]** 算符进行选 **[!UICONTROL equals to]** 择，然 **[!UICONTROL Chicago]** 后输入值。
1. 要联系进入芝加哥的所有人员，请取消选中区分大小写选项。
1. 单击 **[!UICONTROL Confirm]**.

## 创建电子邮件投放{#creating-an-email-delivery}

1. 在> **[!UICONTROL Activities]** 中 **[!UICONTROL Channels]**，将电子邮件投放 [](../../automating/using/email-delivery.md) 活动拖放到每个区段之后。
1. 单击活动，然 ![](assets/edit_darkgrey-24px.png) 后选择编辑。
1. 选择 **[!UICONTROL Simple email]** 并单击 **[!UICONTROL Next]**。
1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件的布局，请单击 **[!UICONTROL Email Designer]**。
1. 插入元素或选择现有模板。
1. 使用特定于每个位置的优惠个性化您的电子邮件。

   有关详细信息，请参阅 [设计电子邮件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。

1. 单击 **[!UICONTROL Preview]** 以检查布局。
1. 单击 **[!UICONTROL Save]**.

![](assets/wf-segmentation-location.png)

