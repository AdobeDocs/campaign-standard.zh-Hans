---
solution: Campaign Standard
product: campaign
title: 热门点击
description: 通过热门点击即装即用报告，了解客户点击投放的位置。
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryHotClicksReport,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 0%

---


# 热门点击{#hot-clicks}

此报告可从每个投放 **[!UICONTROL Reports]** 或事务性消息的按钮访问。

![](assets/delivery_reports_hot-clicks_4.png)

它以单击每个链接的百分比显示消息内容（HTML和／或文本）。

![](assets/delivery_reports_10.png)

如果您为投放创建了动态内容，则可以视图您定义的每个条件的百分比。 有关在投放中插入条件内容的详细信息，请参阅 [定义动态内容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)。

例如，想象您创建了具有以下条件的投放:

* 如果收件人是男人或女人，则主图像上的链接会有所不同。
* 您还添加了一个指向特殊优惠的链接，该链接仅对25岁以上的收件人可见。

发送消息后，从投放 **[!UICONTROL Reports]** 仪表板 **[!UICONTROL Hot clicks]** 中选择>。

默认情况下，不选择用户档案。 只显示性别未知的收件人和年龄未满25岁或年龄未知的收件人的点击。

![](assets/delivery_reports_hot-clicks_1.png)

要显示女性的点击次数，请单 **[!UICONTROL Change profile]** 击按钮并选择女性测试用户档案。 要显示男性的点击次数，请按类似方式继续并选择男性测试用户档案。

![](assets/delivery_reports_hot-clicks_2.png)

要显示超过25个收件人的点击次数，请单 **[!UICONTROL Change profile]** 击该按钮并选择出生日期与此条件匹配的测试用户档案。

有关测试用户档案的详细信息，请参 [阅关于测试用户档案](../../audiences/using/managing-test-profiles.md)。

>[!NOTE]
>
>特定链接的点击次数是投放中所有条件内容的总点击量的百分比。 因此，如果您定义了动态内容，则为特定测试用户档案显示的百分比总数可能不等于100。

同样，对于循环投放和事务性消息，您可以选择与要显示的动态内容对应的测试用户档案，但也可以根据选定的执行投放视图单击百分比。

执行投放是在以下情况下创建的不可操作且无功能的技术消息：

* 每次执行或更新循环投放。

   例如，如果每月执行一次管理此投放的工作流，则每月将执行一个执行投放。 此外，每次更新投放的内容时，都会创建额外的执行投放。

   有关循环电子邮件投放的详细信息，请参 [阅电子邮件投放](../../automating/using/email-delivery.md)。

* 默认情况下，每月一次事务性消息，并且每次编辑和发布事务性消息时都是如此。

   有关事务性消息的更多信息，请参 [阅交易消息快速入门](../../channels/using/getting-started-with-transactional-msg.md)。

>[!NOTE]
>
>由于跟踪的URL的ID对于每个执行都不同，因此不能针对给定消息的所有执行投放聚集热点单击数据。 它一次只能显示给一个执行投放。

发送消息后，从投放 **[!UICONTROL Reports]** 仪表板 **[!UICONTROL Hot clicks]** 中选择>。

默认情况下，将选择最后一个执行投放。 单击该 **[!UICONTROL Change execution delivery]** 按钮以选择另一个。

![](assets/delivery_reports_hot-clicks_3.png)

只显示所选投放执行的单击百分比。
