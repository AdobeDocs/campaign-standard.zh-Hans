---
title: 添加链接
description: 了解如何使用Email Designer管理链接。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: d1714101-bad0-40c1-8d60-90469d033197
source-git-commit: 146dfea38bd456a5d9200b0632d4aa279b10a7b9
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 7%

---

# 添加链接 {#links}

## 插入链接 {#inserting-a-link}

该编辑器允许您通过在HTML内容元素中插入链接来个性化电子邮件或登陆页面。

您可以将链接插入到任意页面元素中：图像、单词、单词组、文本块等。

>[!NOTE]
>
>下图显示如何使用插入链接 [电子邮件设计工具](../../designing/using/designing-content-in-adobe-campaign.md) 在电子邮件中。

1. 选择元素并单击 **[!UICONTROL Insert link]** 从上下文工具栏中。

   ![](assets/des_insert_link.png)

1. 选择要创建的链接类型：

   * **外部链接**：插入指向外部URL的链接。

     您可以为URL定义个性化。 请参阅 [个性化URL](personalization.md#personalizing-urls).

   * **登陆页面**：授予对Adobe Campaign登陆页面的访问权限。
   * **订阅链接**：插入链接以订阅Adobe Campaign服务。
   * **退订链接**：插入链接以取消订阅Adobe Campaign服务。
   * **定义操作的链接**：定义在单击登陆页面中的元素时执行的操作。

     >[!NOTE]
     >
     >此类链接仅适用于登陆页面。

1. 您可以修改向收件人显示的文本。
1. 您可以设置用户单击链接（例如，打开新窗口）时的浏览器行为。

   >[!NOTE]
   >
   >定义浏览器行为仅适用于登陆页面。

1. 保存您的更改。

创建链接后，您仍然可以从设置窗格对其进行修改。 单击铅笔图标以编辑其参数。

![](assets/des_link_edit.png)

使用编辑电子邮件时 [电子邮件设计工具](../../designing/using/designing-content-in-adobe-campaign.md)中，您可以轻松地访问和修改从列出电子邮件中所有URL的表中创建的链接。 此列表提供一个集中式视图，让您能够找到电子邮件内容中的每个 URL。要访问它，请参阅 [关于跟踪的URL](#about-tracked-urls).

![](assets/des_link_list.png)

>[!NOTE]
>
>个性化URL，例如 **镜像页面URL** 或 **退订** 无法从此列表中修改链接。 所有其他链接均可编辑。

**相关主题**：

* [插入个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)
* [添加内容块](../../designing/using/personalization.md#adding-a-content-block)
* [定义动态内容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## 关于跟踪的URL {#about-tracked-urls}

通过Adobe Campaign，您可以跟踪收件人单击电子邮件中包含的URL时的行为。 有关跟踪的更多信息，请参阅[此部分](../../sending/using/tracking-messages.md#about-tracking)。

此 **[!UICONTROL Links]** 操作栏中的图标会自动显示将跟踪的内容的所有URL列表。

![](assets/des_links.png)

>[!NOTE]
>
>默认情况下会激活跟踪。 此功能仅适用于在Adobe Campaign中激活跟踪的电子邮件。 有关跟踪参数的更多信息，请参阅 [本节](../../administration/using/configuring-email-channel.md#tracking-parameters).

可以从此列表中修改每个链接的URL、类别、标签和跟踪类型。 要编辑链接，请单击相应的铅笔图标。

![](assets/des_links_tracking.png)

对于每个跟踪的URL，您可以将跟踪模式设置为以下值之一：

* **已跟踪**：在此URL上激活跟踪。
* **镜像页面**：将此URL视为镜像页面URL。
* **从不**：从不激活此URL的跟踪。 此信息已保存：如果URL再次出现在将来的消息中，则会自动停用其跟踪。
* **选择退出**：将此URL视为选择退出或退订URL。

![](assets/des_link_tracking_type.png)

您还可以停用或激活每个URL的跟踪。

>[!NOTE]
>
>默认情况下，在Adobe Campaign中，将跟踪所有内容URL，但 **镜像页面URL** 和 **退订** 链接。

您可以通过编辑 **[!UICONTROL Category]** 字段，具体取决于消息中使用的URL。 这些类别可以显示报表，例如 [URL和点击流](../../reporting/using/urls-and-click-streams.md).

![](assets/des_link_tracking_category.png)

构建报告时，从 **[!UICONTROL Components]** 选项卡，选择 **[!UICONTROL Dimension]** 并向下滚动列表以访问跟踪组件。 例如，拖放 **[!UICONTROL Tracking URL Category]** ，以根据每个点击的URL的跟踪类别来显示结果。

![](assets/des_link_tracking_report.png)

有关构建自定义报表的更多信息，请参阅 [本节](../../reporting/using/about-dynamic-reports.md).
