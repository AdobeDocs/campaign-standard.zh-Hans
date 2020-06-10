---
title: 电子邮件渲染
description: 了解电子邮件渲染功能。
page-status-flag: never-activated
uuid: c423e237-ad39-4797-ac3a-4320894a8f99
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 2b5b13c8-2e51-4985-a161-c1d7f0fc32b4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b43e6be265ff2d8ce357ef44672a755028e2e5af
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 2%

---


# 电子邮件渲染{#email-rendering}

在点击按 **[!UICONTROL Send]** 钮之前，请确保以最佳方式在各种Web客户端、Web邮件和设备上显示您的消息。

为了实现此功能，Adobe Campaign捕获渲染并在专用报告中提供。 这样，您就可以在接收消息的不同上下文预览已发送的消息。

可用于Adobe Campaign中电子邮件呈现的移 **动设备** 、消息和Web邮件客户端列在 [Litmus网站上](https://litmus.com/email-testing) (单击“ **视图所有电子邮**&#x200B;件客户端”)。

## 检查电子邮件呈现报告 {#checking-the-email-rendering-report}

创建电子邮件投放并定义其内容以及目标用户群后，请按照以下步骤操作。

1. 单击 **受众** ，以访问 **[!UICONTROL Test profiles]** 选项卡。

   ![](assets/email_rendering_05.png)

1. 使用查询编辑器定义要使用的测试用户档案，包括用于电子邮件渲染的 **测试用户档案** 。 请参 [阅关于测试用户档案](../../audiences/using/managing-test-profiles.md)。

   ![](assets/email_rendering_06.png)

1. 检查并确认查询，然后保存更改。
1. 单击操 **[!UICONTROL Test]** 作栏中的按钮。

   ![](assets/email_rendering_07.png)

1. 选择选 **[!UICONTROL Email rendering]** 项，然后单击 **[!UICONTROL OK]**。

   ![](assets/email_rendering_08.png)

   >[!NOTE]
   >
   >该选 **[!UICONTROL Proof + Email rendering]** 项允许您发送验证并同时使用电子邮件渲染功能。 您可以让验证收件人批准您的邮件，同时可以根据目标收件箱测试接收邮件的方式。 在这种情况下，您还需要选择验证测试用户档案。 请参 [阅关于测试用户档案](../../audiences/using/managing-test-profiles.md)。

   测试投放已发送。

1. 在发送消息后几分钟内即可使用渲染缩略图。 要访问它们， **[!UICONTROL Proofs]** 请在下 **[!UICONTROL Summary]** 拉列表中选择。

   ![](assets/email_rendering_03.png)

1. 在列表 **[!UICONTROL Proofs]** 中，单击该 **[!UICONTROL Access email rendering]** 图标。

   ![](assets/email_rendering_04.png)

此时将显示专用的电子邮件呈现报告。 请参阅 [电子邮件呈现报告说明](#email-rendering-report-description)。

**相关主题**:

* [创建电子邮件](../../channels/using/creating-an-email.md)
* [发送校样](../../sending/using/sending-proofs.md)
* [查询编辑器](../../automating/using/editing-queries.md#about-query-editor)

## 电子邮件呈现报告说明 {#email-rendering-report-description}

此报告在收件人中显示电子邮件呈现。 根据收件人打开电子邮件投放的方式，电子邮件呈现方式可能会有所不同： 或通过电子邮件应用程序。

>[!NOTE]
>
>许可协议中列出了可用的渲染数量。 启用电子邮件 **渲染的投放** ，每个将您的可用渲染（称为令牌）减少一个。

报告摘要显示接收的邮件数、无用的（垃圾邮件）、未接收的邮件数或待接收邮件数。

![](assets/inbox_rendering_report.png)

报告分为三部分： **[!UICONTROL Mobile]**、 **[!UICONTROL Messaging clients]**&#x200B;和 **[!UICONTROL Webmails]**。 向下滚动报表可显示分组到这三个类别中的所有渲染。

![](assets/inbox_rendering_report_3.png)

要获取每个报告的详细信息，请单击相应的信息卡。 为所选接收方法显示呈现。

![](assets/inbox_rendering_report_2.png)

该 **[!UICONTROL Technical data]** 选项卡允许您获取更多信息，如接收和捕获日期以及电子邮件的完整标题。
