---
title: 热门点击
seo-title: 热门点击
description: 热门点击
seo-description: 通过热门的现成报告，了解客户点击您的交付的位置。
page-status-flag: 从未激活
uuid: 7ed49dd3-d7 ee-466a-7a7 b-d2 aa16961667
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 报告报告
content-type: reference
topic-tags: 报告列表
discoiquuid: ecc1ade-63d9-4ac2-9828-380a1aa95094
context-tags: DeliyHotclicksReport，main
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 77b0933bcd004cedc6a58f80717a4284b284e0cd

---


# Hot clicks{#hot-clicks}

This report can be accessed from the **[!UICONTROL Reports]** button in each delivery or transactional message.

![](assets/delivery_reports_hot-clicks_4.png)

它以点击每个链接的百分比显示消息内容(HTML和/或文本)。

![](assets/delivery_reports_10.png)

如果您为传送创建了动态内容，则可以查看所定义条件的百分比。For more on inserting conditional content in a delivery, see [Defining dynamic content](../../designing/using/defining-dynamic-content-in-a-landing-page.md).

例如，假设您根据以下条件创建了分发：

* 如果收件人是男性或女性，则主图象上的链接会有所不同。
* 您还添加了一个指向特殊选件的链接，该选件仅对超过25个收件人可见。

Once your message is sent, select **[!UICONTROL Reports]** &gt; **[!UICONTROL Hot clicks]** from the delivery dashboard.

默认情况下，不会选择任何配置文件。只显示性别未知的收件人以及25岁以下或年龄未知的收件人的点击次数。

![](assets/delivery_reports_hot-clicks_1.png)

To display clicks for women, click the **[!UICONTROL Change profile]** button and select a female test profile. 要显示男性的单击次数，请继续执行类似操作并选择男性测试配置文件。

![](assets/delivery_reports_hot-clicks_2.png)

To display clicks for recipients over 25, click the **[!UICONTROL Change profile]** button and select a test profile whose birth date is matching this condition.

For more on test profiles, see [About test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#about-test-profiles).

>[!NOTE]
>
>单击特定链接的次数占交付中所有条件内容的总点击量的百分比。因此，如果您定义了动态内容，则为特定测试配置文件显示的百分比总数可能不等于100。

同样，对于定期传送和事务消息，您可以选择与要显示的动态内容对应的测试配置文件，但还可以根据所选执行交付查看单击百分比。

执行交付是在下列情况下创建的不可操作和非功能的技术消息：

* 每次执行或更新定期分发。

   例如，如果管理此分发的工作流每月执行一次，每月将有一次执行提交。除此之外，每次更新内容内容时，都会创建额外执行交付。

   For more on recurring email deliveries, see [Email delivery](../../automating/using/email-delivery.md).

* 默认情况下，用于传递事务消息的月份，以及每次编辑事务消息并再次发布时。

   For more on transactional messages, see [About transactional messaging](../../channels/using/about-transactional-messaging.md).

>[!NOTE]
>
>由于每个执行的跟踪URL的ID不同，因此热单击数据不能针对给定消息的所有执行交付汇总。一次只能显示一个执行交付。

Once your message is sent, select **[!UICONTROL Reports]** &gt; **[!UICONTROL Hot clicks]** from the delivery dashboard.

默认情况下，将选择上次执行提交。Click the **[!UICONTROL Change execution delivery]** button to select another one.

![](assets/delivery_reports_hot-clicks_3.png)

只显示所选交付执行的单击百分比。
