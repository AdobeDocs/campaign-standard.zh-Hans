---
solution: Campaign Standard
product: campaign
title: 热门点击
description: 通过热门点击开箱即用报表，了解客户在何处点击了您的投放。
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryHotClicksReport,main
feature: Reporting
role: Leader
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '480'
ht-degree: 1%

---


# 热门点击{#hot-clicks}

可以从每个投放或事务性消息的&#x200B;**[!UICONTROL Reports]**&#x200B;按钮访问此报表。

![](assets/delivery_reports_hot-clicks_4.png)

它以每个链接上的点击百分比显示消息内容（HTML和/或文本）。

![](assets/delivery_reports_10.png)

如果您为投放创建了动态内容，则可以视图您定义的每个条件的百分比。 有关在投放中插入条件内容的详细信息，请参阅[定义动态内容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)。

例如，想象一下您创建了一个具有以下条件的投放:

* 如果收件人是男是女，则主图像上的链接会有所不同。
* 您还添加了一个指向特殊优惠的链接，该链接仅对25岁以上的收件人可见。

发送消息后，从投放仪表板中选择&#x200B;**[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]**。

默认情况下，不选择用户档案。 只显示性别未知的收件人和25岁以下或年龄未知的收件人的点击。

![](assets/delivery_reports_hot-clicks_1.png)

要显示女性的点击量，请单击&#x200B;**[!UICONTROL Change profile]**&#x200B;按钮并选择女性测试用户档案。 要显示男性的点击量，请按同样方式继续并选择男性测试用户档案。

![](assets/delivery_reports_hot-clicks_2.png)

要显示超过25的收件人的点击次数，请单击&#x200B;**[!UICONTROL Change profile]**&#x200B;按钮并选择出生日期与此条件匹配的测试用户档案。

有关测试用户档案的详细信息，请参阅[关于测试用户档案](../../audiences/using/managing-test-profiles.md)。

>[!NOTE]
>
>特定链接的点击次数是投放中所有条件内容的总点击量的百分比。 因此，如果您定义了动态内容，则为特定测试用户档案显示的百分比总数可能不等于100。

同样，对于循环投放和事务性消息，您可以选择与要显示的动态内容对应的测试用户档案，但也可以根据选定的执行投放视图单击百分比。

执行投放是在以下情况下创建的不可操作且功能不全的技术消息：

* 每次执行或更新循环投放。

   例如，如果每月执行一次管理此投放的工作流，则每月将执行一个执行投放。 此外，每次更新投放内容时，都会创建额外的执行投放。

   有关循环电子邮件投放的详细信息，请参阅[电子邮件投放](../../automating/using/email-delivery.md)。

* 默认情况下，每月一次事务性消息，每次编辑和发布事务性消息时，都会重新进行。

   有关事务性消息的详细信息，请参阅[事务消息](../../channels/using/getting-started-with-transactional-msg.md)快速入门。

>[!NOTE]
>
>由于跟踪的URL的ID对于每次执行都不同，因此无法针对给定消息的所有执行投放聚合热点单击数据。 一次只能为一个执行投放显示。

发送消息后，从投放仪表板中选择&#x200B;**[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]**。

默认情况下，将选择上次执行投放。 单击&#x200B;**[!UICONTROL Change execution delivery]**&#x200B;按钮以选择另一个按钮。

![](assets/delivery_reports_hot-clicks_3.png)

只显示所选投放执行的单击百分比。
