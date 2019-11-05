---
title: 控制规则
description: 了解如何使用控制规则加强消息的质量检查。
page-status-flag: 从未激活
uuid: 33a1c90c-534e-4fe1-982c-f4e1858d4d2d
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 管理
content-type: 参考
topic-tags: 排版规则
discoiquuid: 305cade-6424-4c6f-b11b-1e8bdbad6ef1
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 控制规则{#control-rules}

控制规则允许用户在发送消息之前检查消息的有效性和质量，如字符显示、SMS消息大小、地址格式等。

Adobe Campaign中提供的一组默认规则可确保标准控件：

* **[!UICONTROL Check subject]** （电子邮件）:检查主题和发送者地址是否不包含可能导致某些邮件传输代理出现问题的特殊字符，并检查邮件主题是否已完成。
* **[!UICONTROL Check URL labels]** （电子邮件）:检查每个跟踪URL是否都有标签。
* **[!UICONTROL Check URLs]** （电子邮件）:检查跟踪URL（存在“&amp;”字符）。
* **[!UICONTROL Check proof size]** （所有渠道）:如果证明目标数量超过100个接收者，则生成错误消息。
* **选中取消订阅链接** （电子邮件）:检查每个内容（HTML和文本）中是否存在至少一个取消订阅（退出）URL。
* **[!UICONTROL Check delivery size]** （所有渠道）:检查消息的大小。
* **[!UICONTROL Check social network sharing link]** （电子邮件）:在内容中包含社交网络共享链接(ViralLinks)时，检查指向镜像页面的链接是否存在。
* **[!UICONTROL A/B Test]**:提取测试群体以通过A/B测试进行递送。

您可以从交付生命周期的某一阶段选择应用规则的时间。 从排版规则字段的下拉列表中选择要应 **[!UICONTROL Phase]** 用的值。

![](assets/typology_phase.png)

可能的值包括：

* **定位开始时**

   该控制规则可在此阶段应用，以便在出错时不执行个性化步骤。

* **定位后**

   如果您需要了解目标的音量以应用控制规则，请选择此阶段。

   例如，检查校样 **大小控制规则在定位阶段** 之后适用：如果证明收件人太多，此规则将阻止准备消息个性化。

* **个性化开始时**

   如果检查涉及批准消息个性化，则必须选择此阶段。 消息个性化在分析阶段执行。

* **分析结束时**

   当检查要求消息个性化完成时，请选择此阶段。

>[!NOTE]
>
>出于安全原因，无法修改控制规则的内容。 该 **[!UICONTROL Code]** 字段为只读字段。
