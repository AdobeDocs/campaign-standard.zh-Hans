---
solution: Campaign Standard
product: campaign
title: 控制规则
description: 了解如何使用控制规则加强消息的质量检查。
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 3%

---


# 控制规则 {#control-rules}

控制规则允许您在发送消息之前检查消息的有效性和质量，如字符显示、SMS消息大小、地址格式等。

>[!NOTE]
>
>出于安全原因，控制规则为只读，无法修改。

## 默认控制规则{#default-control-rules}

一组默认规则可确保标准控件。 下表提供了这些规则及其相关渠道和[执行阶段](#control-rules-execution-phases)的相关信息。

| 标签 | 渠道 | 执行阶段 | 说明 |
---------|----------|---------|---------
| **[!UICONTROL A/B Test]** | 电子邮件 | 在个性化开始 | 通过A/B测试提取投放的测试群体。 |
| **[!UICONTROL Check delivery size]** | 所有 | 定位后 | 检查消息的大小。 |
| **[!UICONTROL Check email content is not empty]** | 电子邮件 | 定位后 | 如果消息的内容为空，则生成错误。 |
| **[!UICONTROL Check In-App content for broadcast template]** | 应用程序内 | 开始个性化 | 检查广播模板的应用程序内内容／触发器是否不为空。 |
| **[!UICONTROL Check In-App content for profile template]** | 应用程序内 | 在个性化开始 | 检查应用程序内内容／触发器是否对用户档案模板不为空。 |
| **[!UICONTROL Check In-App content for subscriber template]** | 应用程序内 | 在个性化开始 | 检查订阅者模板的应用程序内内容／触发器是否不为空。 |
| **[!UICONTROL Check proof size]** | 所有 | 定位后 | 如果验证目标总数超过100个收件人，则生成错误消息。 |
| **[!UICONTROL Check social network sharing link]** | 电子邮件 | 在个性化开始 | 当在内容中包含社交网络共享链接(ViralLinks)时，检查指向镜像页面的链接是否存在。 |
| **[!UICONTROL Check subject]** | 电子邮件 | 在个性化开始 | 检查主题和发件人地址是否不包含可能导致某些邮件传输代理出现问题的特殊字符，并检查邮件主题是否已完成。 |
| **[!UICONTROL Check unsubscription link]** | 电子邮件 | 在个性化开始 | 检查每个内容（HTML和文本）中是否存在至少一个退订（选择退出）URL。 |
| **[!UICONTROL Check URL labels]** | 电子邮件 | 在个性化开始 | 检查每个跟踪URL是否都有标签。 |
| **[!UICONTROL Check URLs]** | 电子邮件 | 在个性化开始 | 检查跟踪URL（存在“&amp;”字符）。 |

## 控制规则执行阶段{#control-rules-execution-phases}

控制规则可在投放生命周期的不同阶段应用：

* **在定位开始**:该控制规则可在此阶段应用，以便在错误事件中不执行个性化步骤。

* **定位后**:定位后执行允许您了解目标的卷以应用控制规则。

   例如，**检查验证大小**&#x200B;控制规则在定位阶段之后应用：如果验证收件人过多，此规则将阻止准备消息个性化。

* **在个性化开始**:在支票与邮件个性化审批相关时应用。消息个性化在分析阶段执行。

* **分析结束时**:当检查需要完成消息个性化时。
