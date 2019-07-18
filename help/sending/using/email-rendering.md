---
title: 电子邮件渲染
seo-title: 电子邮件渲染
description: 电子邮件渲染
seo-description: 发现电子邮件渲染功能。
page-status-flag: 从未激活
uuid: c423e237-ad39-4797-ac3 a-4320894a8 f99
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 发送
content-type: reference
topic-tags: 准备和测试消息
discoiquuid: 2b5b13c8-2e51-4985-a161-c1 d7 f0 fc32 b4
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Email rendering{#email-rendering}

Before hitting the **[!UICONTROL Send]** button, make sure that your message will be displayed in an optimal way on a variety of web clients, web mails and devices.

为允许此操作，Adobe Campaign捕获渲染并在专用报告中提供。这样，您就可以在接收消息的不同上下文中预览发送的消息。

The mobile, messaging and webmail clients available for **Email rendering** in Adobe Campaign are listed on the Litmus [website](https://litmus.com/email-testing) (click **View all email clients**).

## Checking the Email rendering report {#checking-the-email-rendering-report}

创建电子邮件分发并定义其内容以及目标人群后，请遵循以下步骤。

1. Click **Audience** to access the **[!UICONTROL Test profiles]** tab.

   ![](assets/email_rendering_05.png)

1. Use the query editor to define the test profiles that you want to use, including the test profiles that are for **Email rendering** use. See [About test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#about-test-profiles).

   ![](assets/email_rendering_06.png)

1. 检查并确认您的查询，然后保存更改。
1. Click the **[!UICONTROL Test]** button in the action bar.

   ![](assets/email_rendering_07.png)

1. Select the **[!UICONTROL Email rendering]** option then click **[!UICONTROL OK]**.

   ![](assets/email_rendering_08.png)

   >[!NOTE]
   >
   >The **[!UICONTROL Proof + Email rendering]** option enables you to send a proof and use the email rendering feature simultaneously. 您可以收到由校样收件人批准的消息，同时还可以测试根据目标收件箱接收消息的方式。在这种情况下，您还需要选择“校样测试配置文件”。See [About test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#about-test-profiles).

   测试交付将发送。

1. 发送消息后几分钟可使用渲染缩略图。To access them, select **[!UICONTROL Proofs]** in the **[!UICONTROL Summary]** drop-down list.

   ![](assets/email_rendering_03.png)

1. From the **[!UICONTROL Proofs]** list, click the **[!UICONTROL Access email rendering]** icon.

   ![](assets/email_rendering_04.png)

此时会显示专用电子邮件渲染报告。See [Email rendering report description](../../sending/using/email-rendering.md#email-rendering-report-description).

**相关主题**：

* [创建电子邮件](../../channels/using/creating-an-email.md)
* [管理测试配置文件和发送校样](../../sending/using/managing-test-profiles-and-sending-proofs.md)
* [查询编辑器](../../automating/using/editing-queries.md#about-query-editor)

## Email rendering report description {#email-rendering-report-description}

此报告显示电子邮件呈现给收件人的呈现形式。电子邮件呈现可能因收件人如何打开电子邮件分发而异：在浏览器中、在移动设备上或通过电子邮件应用程序。

>[!NOTE]
>
>您的许可协议中列出了可用的演绎版数。Each delivery with **Email rendering** enabled decreases your available renderings (known as tokens) by one. 如果您是Litmus客户端，则可以使用自己的Litmus帐户在Adobe Campaign中提供和使用电子邮件渲染。有关此问题的详细信息，请与您的Adobe客户经理联系。

报告摘要显示接收的消息、不需要(垃圾邮件)、未接收或待定的消息数。

![](assets/inbox_rendering_report.png)

The report is divided into three parts: **[!UICONTROL Mobile]**, **[!UICONTROL Messaging clients]**, and **[!UICONTROL Webmails]**. 向下滚动报表以显示分组到这三个类别中的所有呈现。

![](assets/inbox_rendering_report_3.png)

要获取每个报告的详细信息，请单击相应的卡。将为选定的接收方法显示渲染。

![](assets/inbox_rendering_report_2.png)

**[!UICONTROL Technical data]** 选项卡允许您获取更多信息，如接收和捕获日期以及电子邮件的完整标题。
