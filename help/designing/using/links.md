---
title: 管理链接
description: 了解如何与电子邮件设计人员管理链接。
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1b70e18be29fd48d102313f6d741e9ffe053cc34

---


# 链接 {#links}

## 插入链接 {#inserting-a-link}

编辑器允许您通过将链接插入HTML内容元素，个性化电子邮件或登录页面。

可以向任何页面元素中插入链接：图像、单词、单词组、文本块等。

>[!NOTE]
>
>下图显示了如何使用电子邮件中的电子邮 [件设计器](../../designing/using/designing-content-in-adobe-campaign.md) 插入链接。

1. 选择元素，然后从上下文 **[!UICONTROL Insert link]** 工具栏中单击。

   ![](assets/des_insert_link.png)

1. 选择要创建的链接类型：

   * **外部链接**:插入指向外部URL的链接。

      您可以为URL定义个性化。 请参 [阅个性化URL](../../designing/using/using-reusable-content.md#creating-a-content-fragment)。

   * **登陆页面**:允许访问Adobe Campaign登录页面。
   * **订阅链接**:插入链接以订阅Adobe Campaign服务。
   * **取消订阅链接**:插入一个链接以取消订阅Adobe Campaign服务。
   * **定义操作的链接**:在单击登陆页面中的元素时定义操作。

      >[!NOTE]
      >
      >此类型的链接仅适用于登陆页面。

1. 您可以修改显示给收件人的文本。
1. 您可以在用户单击链接时设置浏览器行为（例如，打开新窗口）。

   >[!NOTE]
   >
   >定义浏览器行为仅适用于登陆页面。

1. 保存更改。

创建链接后，您仍可以从“设置”窗格中修改该链接。 单击铅笔图标以编辑其参数。

![](assets/des_link_edit.png)

使用电子邮件设计器编 [辑电子邮件时](../../designing/using/designing-content-in-adobe-campaign.md)，您可以轻松访问和修改您从列出电子邮件中包含的所有URL的表格中创建的链接。 此列表允许您集中查看并查找电子邮件内容中的每个URL。 要访问它，请参阅关 [于跟踪的URL](#about-tracked-urls)。

![](assets/des_link_list.png)

>[!NOTE]
>
>无法从此列表 **中修改个性化URL** , **如Mirror page URL** 或Unsubscription链接。 所有其他链接都可编辑。

**相关主题**:

* [插入个性化字段](../../designing/using/personalization.md#inserting-a-personalization-field)
* [添加内容块](../../designing/using/personalization.md#adding-a-content-block)
* [定义动态内容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## 关于跟踪的URL {#about-tracked-urls}

Adobe Campaign允许您在收件人单击电子邮件中包含的URL时跟踪其行为。 有关跟踪的详细信息，请参 [阅此部分](../../sending/using/tracking-messages.md#about-tracking)。

操 **[!UICONTROL Links]** 作栏中的图标会自动显示要跟踪的内容的所有URL的列表。

![](assets/des_links.png)

>[!NOTE]
>
>默认情况下，跟踪处于激活状态。 此功能仅适用于在Adobe Campaign中激活了跟踪的电子邮件。 有关跟踪参数的详细信息，请参 [阅本节](../../administration/using/configuring-email-channel.md#tracking-parameters)。

可以从此列表修改每个链接的URL、类别、标签和跟踪类型。 要编辑链接，请单击相应的铅笔图标。

![](assets/des_links_tracking.png)

对于每个跟踪的URL，可以将跟踪模式设置为以下值之一：

* **跟踪**:激活对此URL的跟踪。
* **镜像页面**:将此URL视为镜像页面URL。
* **从不**:从不激活此URL的跟踪。 此信息已保存：如果URL在将来的消息中再次显示，则其跟踪将自动取消激活。
* **选择退出**:将此URL视为选择退出或取消订阅URL。

![](assets/des_link_tracking_type.png)

您还可以取消激活或激活每个URL的跟踪。

>[!NOTE]
>
>默认情况下，Adobe Campaign中跟踪除镜像页面URL和取消订阅链接 **之外的所有内** 容 **URL** 。

您可以通过编辑字段来重新 **[!UICONTROL Category]** 分组您的URL，具体取决于消息中使用的URL。 这些类别可以显示报告，例如在URL中， [单击流](../../reporting/using/urls-and-click-streams.md)。

![](assets/des_link_tracking_category.png)

在生成报告时，从选项卡 **[!UICONTROL Components]** 中选择并 **[!UICONTROL Dimension]** 向下滚动列表以访问跟踪组件。 例如，拖放到工作区 **[!UICONTROL Tracking URL Category]** 中可根据每个单击的URL的跟踪类别显示结果。

![](assets/des_link_tracking_report.png)

有关构建自定义报告的更多信息，请参 [阅此部分](../../reporting/using/about-dynamic-reports.md)。
