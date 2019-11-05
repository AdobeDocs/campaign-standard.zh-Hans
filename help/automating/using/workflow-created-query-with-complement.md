---
title: “工作流用例：使用补充创建交付”
description: “工作流用例：使用补充创建交付”
page-status-flag: 从未激活
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 执行活动
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: 工作流，用例，分段
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 工作流用例：使用补充创建交付 {#deliveries-with-complement}

您可以向客户发送电子邮件：一个是为不到一年前创造的客户，一个是为一年多前创造的客户创建的。

1. 在中， **[!UICONTROL Marketing Activities]**&#x200B;单击并 **[!UICONTROL Create]** 选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]** 为工作流类型，然后单击 **[!UICONTROL Next]**。
1. 输入工作流的属性，然后单击 **[!UICONTROL Create]**。

## 创建查询活动 {#create-a-query-activity}

1. 在 **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**&#x200B;中，拖放 **[!UICONTROL Query activity]**![](assets/query.png)。
1. 双击活动。
1. 在 **[!UICONTROL Shortcuts]**&#x200B;中，拖放并 **[!UICONTROL Profiles]** 使用运 **[!UICONTROL email]** 算符进行选择 **[!UICONTROL is not empty]**。
1. 在 **[!UICONTROL Shortcuts]**&#x200B;中，拖放并 **[!UICONTROL Profiles]** 使用值 **[!UICONTROL no longer contact by email]** 进行选择 **[!UICONTROL no]**。
1. Click **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## 创建分段活动 {#create-a-segmentation-activity}

1. 在 **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**&#x200B;中，拖放一个活 **[!UICONTROL Segmentation]** 动并双击它。
1. 将鼠标悬停在区段上，然后单 ![](assets/edit_darkgrey-24px.png) 击以定位今年在数据库中添加的客户。
1. 拖放并 **[!UICONTROL Profiles]** 选择 **[!UICONTROL Created]** 滤镜类型 **[!UICONTROL Relative]**。
1. 将更改 **[!UICONTROL Level of precision]** 为并 **[!UICONTROL Year]** 选择 **[!UICONTROL This year]**。
1. 单击 **[!UICONTROL Confirm]** 两次。
1. 在中 **[!UICONTROL Advanced Options]**，选中 **[!UICONTROL Generate complement]** 以创建定位其余收件人的区段。
1. Click **[!UICONTROL Confirm]**.
1. Click **[!UICONTROL Save]**.

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>要观察规则的结构，请单击 **[!UICONTROL Advanced Mode]**。

## 创建电子邮件分发 {#create-an-email-delivery}

1. 在 **[!UICONTROL Activities]** &gt; **[!UICONTROL Channels]**&#x200B;中，将电子邮件分发拖放到每个区段之后。
1. 单击活动，然后选择 ![](assets/edit_darkgrey-24px.png) 进行编辑。
1. 选择 **[!UICONTROL Single send email]** 并单击 **[!UICONTROL Next]**。
1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件布局，请单击 **[!UICONTROL Email Designer]**。
1. 插入元素或选择现有模板。
1. 使用每个分发的特定优惠个性化您的电子邮件。
1. 单击 **[!UICONTROL Preview]** 以检查您的布局。
1. Click **[!UICONTROL Save]**.

有关详细信息，请参阅 [设计电子邮件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。

![](assets/wf-deliveries-with-a-complement.png)

**相关主题：**

* [查询](../../automating/using/query.md)
* [细分活动](../../automating/using/segmentation.md)
* [电子邮件投放](../../automating/using/email-delivery.md)
