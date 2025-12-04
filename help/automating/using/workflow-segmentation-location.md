---
title: 按位置分段”
description: 此用例展示了如何对位置执行分段。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query,segmentation,delivery
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: feedc2f5-63da-44a5-b8f0-15afdfd47daa
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 79%

---

# 按位置分段 {#segmentation-on-location}

您可以向客户发送定向电子邮件，并提供当地商店的产品建议。

1. 在 **[!UICONTROL Marketing Activities]** 中，单击 **[!UICONTROL Create]** 并选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]** 作为工作流类型并单击 **[!UICONTROL Next]**。
1. 输入工作流的属性并单击 **[!UICONTROL Create]**。

## 通过电子邮件选择可联系的收件人{#selecting-recipients-contactable-via-email}

1. 在&#x200B;**[!UICONTROL Activities]** > **[!UICONTROL Targeting]**&#x200B;中，拖放[查询](../../automating/using/query.md)活动![](assets/query.png)。
1. 双击该活动。
1. 在 **[!UICONTROL Shortcuts]** 中，拖放 **[!UICONTROL Profiles]** 并选择字段 **[!UICONTROL email]** 和运算符 **[!UICONTROL is not empty]**。
1. 在 **[!UICONTROL Shortcuts]** 中，拖放 **[!UICONTROL Profiles]** 并选择字段 **[!UICONTROL no longer contact by email]** 和值 **[!UICONTROL no]**。
1. 单击 **[!UICONTROL Confirm]** 两次。

![](assets/wf-complement-query.png)

## 创建分段活动{#creating-a-segmentation-activity}

1. 拖放[分段](../../automating/using/segmentation.md)活动并双击该活动。
1. 单击区段，然后打开过渡以定向第一个城市的人群。在本例中，为“Boston”。
1. 拖放 **[!UICONTROL Location]** 并选择 **[!UICONTROL City]** 和运算符 **[!UICONTROL equals to]**，同时选择值 **[!UICONTROL Boston]**。
注意：要联系所有进入波士顿的人员，请取消选中“区分大小写”选项。
1. 单击 **[!UICONTROL Confirm]**。
1. 在 **[!UICONTROL List of outbound segments]** 中，单击 **[!UICONTROL Add an element]** 并单击 ![](assets/edit_darkgrey-24px.png) 创建用于定向第二个城市人群的区段。在本例中，为“Chicago”。
1. 拖放 **[!UICONTROL Location]** 并选择 **[!UICONTROL City]** 和运算符 **[!UICONTROL equals to]**，然后输入 **[!UICONTROL Chicago]** 值。
1. 要联系所有进入芝加哥的人员，请取消选中“区分大小写”选项。
1. 单击 **[!UICONTROL Confirm]**。

## 创建电子邮件投放{#creating-an-email-delivery}

1. 在&#x200B;**[!UICONTROL Activities]** > **[!UICONTROL Channels]**&#x200B;中，将[电子邮件投放](../../automating/using/email-delivery.md)活动拖放到每个区段之后。
1. 单击活动，然后选择 ![](assets/edit_darkgrey-24px.png) 以进行编辑。
1. 选择 **[!UICONTROL Simple email]** 并单击 **[!UICONTROL Next]**。
1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件的布局，请单击 **[!UICONTROL Email Designer]**。
1. 插入元素或选择现有模板。
1. 使用特定于各个地理位置的产品建议，将电子邮件个性化。

   有关更多信息，请参阅[设计电子邮件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。

1. 单击 **[!UICONTROL Preview]** 以检查布局。
1. 单击 **[!UICONTROL Save]**。

![](assets/wf-segmentation-location.png)
