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
ht-degree: 1%

---


# 添加链接 {#links}

## Inserting a link {#inserting-a-link}

编辑器允许您通过在HTML内容元素中插入链接来个性化电子邮件或登陆页。

您可以向任何页面元素中插入链接：图像、单词、单词组、文本块等。

>[!NOTE]
>
>下图显示了如何在电子邮件中使用电子邮 [件设计器](../../designing/using/designing-content-in-adobe-campaign.md) 插入链接。

1. 选择元素，然后从上 **[!UICONTROL Insert link]** 下文工具栏中单击。

   ![](assets/des_insert_link.png)

1. 选择要创建的链接类型：

   * **外部链接**:插入指向外部URL的链接。

      您可以为URL定义个性化。 请参 [阅个性化URL](../../designing/using/using-reusable-content.md#creating-a-content-fragment)。

   * **登陆页**:允许访问Adobe Campaign登陆页。
   * **订阅链接**:插入链接以订阅Adobe Campaign服务。
   * **退订链接**:插入一个链接以取消订阅Adobe Campaign服务。
   * **定义操作的链接**:在单击登陆页中的元素时定义操作。

      >[!NOTE]
      >
      >此类型的链接仅对登陆页可用。

1. 您可以修改显示给收件人的文本。
1. 当用户单击链接时，可以设置浏览器行为（例如，打开新窗口）。

   >[!NOTE]
   >
   >定义浏览器行为仅适用于登陆页。

1. 保存更改。

创建链接后，您仍可以从“设置”窗格中修改该链接。 单击铅笔图标以编辑其参数。

![](assets/des_link_edit.png)

使用电子邮件设计器编 [辑电子邮件](../../designing/using/designing-content-in-adobe-campaign.md)，您可以轻松访问和修改从表格创建的链接，该表格列出了电子邮件中包含的所有URL。 此列表允许您具有集中式视图并在电子邮件内容中查找每个URL。 要访问它，请参 [阅关于跟踪的URL](#about-tracked-urls)。

![](assets/des_link_list.png)

>[!NOTE]
>
>无法从此 **镜像页面中修** 改个 **性化URL** ，如列表URL或退订链接。 所有其他链接都可编辑。

**相关主题**：

* [插入个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)
* [添加内容块](../../designing/using/personalization.md#adding-a-content-block)
* [定义动态内容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## 关于跟踪的URL {#about-tracked-urls}

Adobe Campaign允许您在收件人单击电子邮件中包含的URL时跟踪其行为。 For more on tracking, see [this section](../../sending/using/tracking-messages.md#about-tracking).

操 **[!UICONTROL Links]** 作栏中的图标会自动显示要跟踪的内容的所有URL的列表。

![](assets/des_links.png)

>[!NOTE]
>
>默认情况下，跟踪处于激活状态。 此功能仅在Adobe Campaign中激活了跟踪后才可用于电子邮件。 For more on the tracking parameters, refer to [this section](../../administration/using/configuring-email-channel.md#tracking-parameters).

可以从此列表修改每个链接的URL、类别、标签和跟踪类型。 要编辑链接，请单击相应的铅笔图标。

![](assets/des_links_tracking.png)

对于每个跟踪的URL，可以将跟踪模式设置为以下值之一：

* **跟踪**:在此URL上激活跟踪。
* **镜像页面**:将此URL视为镜像页面URL。
* **从不**:从不激活此URL的跟踪。 此信息已保存：如果URL在将来的消息中再次显示，其跟踪将自动停用。
* **选择退出**:将此URL视为退出或退订URL。

![](assets/des_link_tracking_type.png)

您还可以取消激活或激活每个URL的跟踪。

>[!NOTE]
>
>默认情况下，在Adobe Campaign中跟踪除退订URL和 **镜像页面链接** 外 **的所有内** 容URL。

您可以通过编辑字段来重 **[!UICONTROL Category]** 新分组URL，具体取决于消息中使用的URL。 这些类别可以显示报告，例如在URL中 [并单击流](../../reporting/using/urls-and-click-streams.md)。

![](assets/des_link_tracking_category.png)

在生成报告时，从选 **[!UICONTROL Components]** 项卡中选 **[!UICONTROL Dimension]** 择列表并向下滚动以访问跟踪组件。 例如，拖放到工 **[!UICONTROL Tracking URL Category]** 作区中可根据每个单击的URL的跟踪类别显示结果。

![](assets/des_link_tracking_report.png)

有关构建自定义报告的更多信息，请 [参阅此部分](../../reporting/using/about-dynamic-reports.md)。
