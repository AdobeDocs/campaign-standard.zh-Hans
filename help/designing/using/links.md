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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 2%

---

# 添加链接 {#links}

## 插入链接 {#inserting-a-link}

利用编辑器，可通过将链接插入HTML内容元素，以个性化电子邮件或登陆页面。

您可以将链接插入到任何页面元素中：图像、单词、词组、文本块等。

>[!NOTE]
>
>下图显示了如何使用电子邮件中的[Email Designer](../../designing/using/designing-content-in-adobe-campaign.md)插入链接。

1. 选择一个元素，然后单击上下文工具栏中的&#x200B;**[!UICONTROL Insert link]**。

   ![](assets/des_insert_link.png)

1. 选择要创建的链接类型：

   * **外部链接**:插入指向外部URL的链接。

      您可以为URL定义个性化。 请参阅[个性化URL](../../designing/using/using-reusable-content.md#creating-a-content-fragment)。

   * **登陆页面**:授予对Adobe Campaign登陆页面的访问权限。
   * **订阅链接**:插入链接以订阅Adobe Campaign服务。
   * **退订链接**:插入链接以取消订阅Adobe Campaign服务。
   * **用于定义操作的链接**:定义单击登陆页面中的元素时的操作。

      >[!NOTE]
      >
      >此类链接仅可用于登陆页面。

1. 您可以修改向收件人显示的文本。
1. 您可以在用户单击链接时设置浏览器行为（例如，打开一个新窗口）。

   >[!NOTE]
   >
   >定义浏览器行为仅适用于登陆页面。

1. 保存更改。

创建链接后，您仍可以从“设置”窗格中对其进行修改。 单击铅笔图标以编辑其参数。

![](assets/des_link_edit.png)

使用[Email Designer](../../designing/using/designing-content-in-adobe-campaign.md)编辑电子邮件时，您可以轻松地访问和修改从表格创建的链接，该表格列出了电子邮件中包含的所有URL。 利用此列表，可以集中查看并查找电子邮件内容中的每个URL。 要访问该URL，请参阅[关于跟踪的URL](#about-tracked-urls)。

![](assets/des_link_list.png)

>[!NOTE]
>
>无法从此列表修改个性化URL，如&#x200B;**镜像页面URL**&#x200B;或&#x200B;**退订**&#x200B;链接。 所有其他链接均可编辑。

**相关主题**：

* [插入个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)
* [添加内容块](../../designing/using/personalization.md#adding-a-content-block)
* [定义动态内容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## 关于跟踪的URL {#about-tracked-urls}

Adobe Campaign允许您在收件人单击电子邮件中包含的URL时跟踪其行为。 有关跟踪的更多信息，请参阅[此部分](../../sending/using/tracking-messages.md#about-tracking)。

操作栏中的&#x200B;**[!UICONTROL Links]**&#x200B;图标会自动显示要跟踪的内容的所有URL的列表。

![](assets/des_links.png)

>[!NOTE]
>
>默认情况下，会激活跟踪。 仅当已在Adobe Campaign中激活跟踪时，此功能仅适用于电子邮件。 有关跟踪参数的更多信息，请参阅[此部分](../../administration/using/configuring-email-channel.md#tracking-parameters)。

可以从此列表修改每个链接的URL、类别、标签和跟踪类型。 要编辑链接，请单击相应的铅笔图标。

![](assets/des_links_tracking.png)

对于每个跟踪的URL，您可以将跟踪模式设置为以下值之一：

* **跟踪**:在此URL上激活跟踪。
* **镜像页面**:将此URL视为镜像页面URL。
* **从不**:从不激活此URL的跟踪。此信息已保存：如果URL在将来的消息中再次显示，则其跟踪将自动停用。
* **选择退出**:将此URL视为选择退订或退订URL。

![](assets/des_link_tracking_type.png)

您还可以停用或激活每个URL的跟踪。

>[!NOTE]
>
>默认情况下，在Adobe Campaign中，将跟踪除&#x200B;**镜像页面URL**&#x200B;和&#x200B;**退订**&#x200B;链接之外的所有内容URL。

您可以通过编辑&#x200B;**[!UICONTROL Category]**&#x200B;字段来重组您的URL，具体取决于消息中使用的URL。 这些类别可以显示报表，例如在[URL中，然后单击流](../../reporting/using/urls-and-click-streams.md)。

![](assets/des_link_tracking_category.png)

生成报告时，从&#x200B;**[!UICONTROL Components]**&#x200B;选项卡中，选择&#x200B;**[!UICONTROL Dimension]**&#x200B;并向下滚动列表以访问跟踪组件。 例如，将&#x200B;**[!UICONTROL Tracking URL Category]**&#x200B;拖放到工作区中，以根据每个点击的URL的跟踪类别显示结果。

![](assets/des_link_tracking_report.png)

有关构建自定义报表的更多信息，请参阅[此部分](../../reporting/using/about-dynamic-reports.md)。
