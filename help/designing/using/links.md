---
solution: Campaign Standard
product: campaign
title: 添加链接
description: 了解如何通过电子邮件设计器管理链接。
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 2%

---


# 添加链接{#links}

## 插入链接{#inserting-a-link}

编辑器允许您通过在HTML内容元素中插入链接来个性化电子邮件或登陆页。

可以向任何页面元素中插入链接：图像、单词、单词组、文本块等。

>[!NOTE]
>
>下图显示了如何使用电子邮件中的[电子邮件设计器](../../designing/using/designing-content-in-adobe-campaign.md)插入链接。

1. 选择一个元素，然后单击上下文工具栏中的&#x200B;**[!UICONTROL Insert link]**。

   ![](assets/des_insert_link.png)

1. 选择要创建的链接类型：

   * **外部链接**:插入指向外部URL的链接。

      您可以为URL定义个性化。 请参阅[个性化URL](../../designing/using/using-reusable-content.md#creating-a-content-fragment)。

   * **登陆页**:允许访问Adobe Campaign登陆页。
   * **订阅链接**:插入链接以订阅Adobe Campaign服务。
   * **退订链接**:插入一个链接以取消订阅Adobe Campaign服务。
   * **定义动作的链接**:在单击登陆页中的元素时定义操作。

      >[!NOTE]
      >
      >此类链接仅适用于登陆页。

1. 您可以修改显示给收件人的文本。
1. 您可以在用户单击链接时设置浏览器行为（例如，打开新窗口）。

   >[!NOTE]
   >
   >定义浏览器行为仅适用于登陆页。

1. 保存更改。

创建链接后，您仍可以从“设置”窗格中修改它。 单击铅笔图标以编辑其参数。

![](assets/des_link_edit.png)

在使用[电子邮件设计器](../../designing/using/designing-content-in-adobe-campaign.md)编辑电子邮件时，您可以轻松访问和修改从列表电子邮件中包含的所有URL的表中创建的链接。 此列表使您能够集中视图并在电子邮件内容中找到每个URL。 要访问它，请参阅[关于跟踪的URL](#about-tracked-urls)。

![](assets/des_link_list.png)

>[!NOTE]
>
>无法从此列表修改个性化URL，如&#x200B;**镜像页面URL**&#x200B;或&#x200B;**退订**&#x200B;链接。 所有其他链接都可编辑。

**相关主题**：

* [插入个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)
* [添加内容块](../../designing/using/personalization.md#adding-a-content-block)
* [定义动态内容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## 关于跟踪的URL {#about-tracked-urls}

Adobe Campaign使您能够跟踪收件人单击电子邮件中包含的URL时的行为。 有关跟踪的更多信息，请参阅[此部分](../../sending/using/tracking-messages.md#about-tracking)。

操作栏中的&#x200B;**[!UICONTROL Links]**&#x200B;图标会自动显示要跟踪的内容的所有URL的列表。

![](assets/des_links.png)

>[!NOTE]
>
>默认情况下，跟踪处于激活状态。 仅当在Adobe Campaign中激活了跟踪时，此功能才可用于电子邮件。 有关跟踪参数的详细信息，请参阅[本节](../../administration/using/configuring-email-channel.md#tracking-parameters)。

可以从此列表修改每个链接的URL、类别、标签和跟踪类型。 要编辑链接，请单击相应的铅笔图标。

![](assets/des_links_tracking.png)

对于每个跟踪的URL，可以将跟踪模式设置为以下值之一：

* **跟踪**:在此URL上激活跟踪。
* **镜像页面**:认为此URL是镜像页面URL。
* **从不**:绝不激活此URL的跟踪。此信息已保存：如果URL在将来的消息中再次显示，其跟踪将自动停用。
* **选择退出**:将此URL视为退出或退订URL。

![](assets/des_link_tracking_type.png)

您还可以取消激活或激活每个URL的跟踪。

>[!NOTE]
>
>默认情况下，在Adobe Campaign中，跟踪除&#x200B;**镜像页面URL**&#x200B;和&#x200B;**退订**&#x200B;链接之外的所有内容URL。

您可以通过编辑&#x200B;**[!UICONTROL Category]**&#x200B;字段来重新组合您的URL，具体取决于消息中使用的URL。 这些类别可以显示报表，例如，在[URL中，单击streams](../../reporting/using/urls-and-click-streams.md)。

![](assets/des_link_tracking_category.png)

在生成报告时，从&#x200B;**[!UICONTROL Components]**&#x200B;选项卡中，选择&#x200B;**[!UICONTROL Dimension]**&#x200B;并向下滚动列表以访问跟踪组件。 例如，将&#x200B;**[!UICONTROL Tracking URL Category]**&#x200B;拖放到工作区中，以根据每个单击的URL的跟踪类别显示结果。

![](assets/des_link_tracking_report.png)

有关构建自定义报告的详细信息，请参阅[此部分](../../reporting/using/about-dynamic-reports.md)。
