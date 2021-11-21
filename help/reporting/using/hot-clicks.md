---
title: 热门点击
description: 通过现成的“热门点击”报表，了解客户点击投放的位置。
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryHotClicksReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 5af37156-e93b-4ae9-9856-053364f211ef
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 0%

---

# 热门点击{#hot-clicks}

此报表可从 **[!UICONTROL Reports]** 按钮。

![](assets/delivery_reports_hot-clicks_4.png)

它显示消息内容(HTML和/或文本)以及每个链接的点击百分比。

![](assets/delivery_reports_10.png)

如果您为投放创建了动态内容，则可以查看您定义的每个条件的百分比。 有关在投放中插入条件内容的更多信息，请参阅 [定义动态内容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

例如，假定您创建了具有以下条件的投放：

* 如果收件人是男性或女性，则主图像上的链接会有所不同。
* 此外，您还添加了一个指向特殊选件的链接，该特殊选件仅对超过25个的收件人可见。

发送消息后，选择 **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** 从投放仪表板。

默认情况下，未选择任何用户档案。 只显示性别未知的收件人和年龄未满25岁或年龄未知的收件人的点击次数。

![](assets/delivery_reports_hot-clicks_1.png)

要显示女性的点击量，请单击 **[!UICONTROL Change profile]** 按钮，然后选择女性测试用户档案。 要显示男性的点击量，请以类似方式继续并选择男性测试用户档案。

![](assets/delivery_reports_hot-clicks_2.png)

要显示超过25位收件人的点击次数，请单击 **[!UICONTROL Change profile]** 按钮，然后选择出生日期与此条件匹配的测试用户档案。

有关测试用户档案的更多信息，请参阅 [关于测试用户档案](../../audiences/using/managing-test-profiles.md).

>[!NOTE]
>
>特定链接的点击次数是投放中所有条件内容的总点击次数的百分比。 因此，如果您定义了动态内容，则特定测试用户档案显示的百分比总数可能不等于100。

同样，对于定期投放和事务型消息，您可以选择与要显示的动态内容对应的测试用户档案，但您也可以根据所选执行投放查看点击百分比。

执行投放是在以下情况下创建的不可操作且无法正常工作的技术消息：

* 每次执行或更新定期投放时。

   例如，如果管理此投放的工作流每月执行一次，则每月将执行一次投放。 此外，每次更新投放内容时，都会创建一个额外的执行投放。

   有关定期电子邮件投放的更多信息，请参阅 [电子邮件投放](../../automating/using/email-delivery.md).

* 默认情况下，事务型消息每月一次，并且每次编辑并再次发布事务型消息时。

   有关事务型消息的更多信息，请参阅 [事务型消息传递入门](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>由于跟踪的URL ID在每次执行时各不相同，因此无法为给定消息的所有执行投放聚合热点点击数据。 一次只能为一个执行投放显示。

发送消息后，选择 **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** 从投放仪表板。

默认情况下，会选中上次执行投放。 单击 **[!UICONTROL Change execution delivery]** 按钮以选择其他选项。

![](assets/delivery_reports_hot-clicks_3.png)

只显示选定投放执行的点击百分比。
