---
title: 热门点击
description: 通过热点点击即装即用报告，了解客户点击交付的位置。
page-status-flag: 从未激活
uuid: 7ed49dd3-d7ee-466a-9a7b-d2aa16961667
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 报告
content-type: 参考
topic-tags: 报告列表
discoiquuid: ecbc1ade-63d9-4ac2-9828-380a1aa95094
context-tags: deliveryHotClicksReport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 热门点击{#hot-clicks}

可以从每个传送或交易消 **[!UICONTROL Reports]** 息中的按钮访问此报告。

![](assets/delivery_reports_hot-clicks_4.png)

它显示消息内容（HTML和／或文本），并显示每个链接的点击率百分比。

![](assets/delivery_reports_10.png)

如果您为分发创建了动态内容，则可以查看您定义的每个条件的百分比。 有关在分发中插入条件内容的详细信息，请参阅 [定义动态内容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)。

例如，假设您创建了具有以下条件的交付：

* 如果收件人是男性或女性，则主图像上的链接会有所不同。
* 您还添加了一个指向特价优惠的链接，该链接仅对超过25个的收件人可见。

发送消息后，从传送功能板 **[!UICONTROL Reports]** 中 **[!UICONTROL Hot clicks]** 选择&gt;。

默认情况下，未选择任何配置文件。 只显示性别未知的收件人以及年龄在25岁以下或年龄未知的收件人的单击。

![](assets/delivery_reports_hot-clicks_1.png)

要显示女性的点击次数，请单击按 **[!UICONTROL Change profile]** 钮并选择女性测试配置文件。 要显示男性的点击次数，请以类似方式继续，然后选择男性测试配置文件。

![](assets/delivery_reports_hot-clicks_2.png)

要显示超过25个收件人的单击次数，请单 **[!UICONTROL Change profile]** 击按钮，然后选择出生日期与此条件匹配的测试配置文件。

有关测试配置文件的详细信息，请参 [阅关于测试配置文件](../../sending/using/managing-test-profiles-and-sending-proofs.md#about-test-profiles)。

>[!NOTE]
>
>特定链接的点击次数是分发中所有条件内容的总点击量的百分比。 因此，如果您定义了动态内容，则特定测试配置文件显示的百分比总数可能不等于100。

同样，对于重复发送和事务性消息，您可以选择与要显示的动态内容对应的测试配置文件，但也可以根据选定的执行交付查看单击百分比。

执行交付是在以下情况下创建的不可操作且功能不全的技术消息：

* 每次执行或更新循环交付时。

   例如，如果管理此交付的工作流每月执行一次，则每月将执行一个交付。 此外，每次更新交付的内容时，都会创建额外的执行交付。

   有关重复发送电子邮件的详细信息，请参阅 [电子邮件发送](../../automating/using/email-delivery.md)。

* 默认情况下，每月一次事务消息，并且每次编辑和再次发布事务消息。

   有关事务消息的详细信息，请参 [阅关于事务消息](../../channels/using/about-transactional-messaging.md)。

>[!NOTE]
>
>由于跟踪的URL的ID对于每个执行都不同，因此不能为给定消息的所有执行交付聚合热点点击数据。 一次只能为一个执行交付显示它。

发送消息后，从传送功能板 **[!UICONTROL Reports]** 中 **[!UICONTROL Hot clicks]** 选择&gt;。

默认情况下，将选中最后一个执行交付。 单击该 **[!UICONTROL Change execution delivery]** 按钮以选择另一个。

![](assets/delivery_reports_hot-clicks_3.png)

只显示所选交付执行的单击百分比。
