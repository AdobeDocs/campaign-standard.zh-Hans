---
solution: Campaign Standard
product: campaign
title: 控制规则
description: 了解如何使用控制规则加强消息的质量检查。
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
feature: 类型规则
role: Business Practitioner
level: Intermediate
exl-id: 6461c128-1e42-4685-88f8-507244147e6f
source-git-commit: c41d51538b8a8376a034c7d2db77b66b21256fd8
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 4%

---

# 控制规则 {#control-rules}

利用控制规则，可在发送消息之前检查消息的有效性和质量，如字符显示、短信消息大小、地址格式等。

>[!NOTE]
>
>出于安全原因，控制规则为只读，无法修改。

## 默认控制规则 {#default-control-rules}

一组默认规则可确保标准控件。 下表提供了有关这些规则及其相关渠道和[执行阶段](#control-rules-execution-phases)的信息。

| 标签 | 渠道 | 执行阶段 | 说明 |
|---------|----------|---------|---------
| **[!UICONTROL A/B Test]** | 电子邮件 | 开始个性化时 | 提取带有A/B测试的投放的测试群体。 |
| **[!UICONTROL Check delivery size]** | 所有 | 定位后 | 检查消息的大小。 |
| **[!UICONTROL Check email content is not empty]** | 电子邮件 | 定位后 | 如果消息的内容为空，则会生成错误。 |
| **[!UICONTROL Check In-App content for broadcast template]** | 应用程序内 | 开始个性化时 | 检查广播模板的应用程序内内容/触发器是否不为空。 |
| **[!UICONTROL Check In-App content for profile template]** | 应用程序内 | 开始个性化时 | 检查配置文件模板的应用程序内内容/触发器是否不为空。 |
| **[!UICONTROL Check In-App content for subscriber template]** | 应用程序内 | 开始个性化时 | 检查订阅者模板的应用程序内内容/触发器是否不为空。 |
| **[!UICONTROL Check proof size]** | 所有 | 定位后 | 如果校样目标群体超过100个收件人，则会生成错误消息。 |
| **[!UICONTROL Check social network sharing link]** | 电子邮件 | 开始个性化时 | 在内容中包含社交网络共享链接(ViralLinks)时，检查指向镜像页面的链接是否存在。 |
| **[!UICONTROL Check subject]** | 电子邮件 | 开始个性化时 | 检查主题和发件人地址是否不包含可能导致某些邮件传输代理出现问题的特殊字符，并检查邮件主题是否已完成。 |
| **[!UICONTROL Check unsubscription link]** | 电子邮件 | 开始个性化时 | 检查每个内容（HTML和文本）中是否至少有一个退订（选择退订）URL。 |
| **[!UICONTROL Check URL labels]** | 电子邮件 | 开始个性化时 | 检查每个跟踪URL是否都有标签。 |
| **[!UICONTROL Check URLs]** | 电子邮件 | 开始个性化时 | 检查跟踪URL（存在“&amp;”字符）。 |

## 控制规则执行阶段 {#control-rules-execution-phases}

控制规则可以在投放生命周期的不同阶段应用：

* **定位开始时**:可在此阶段应用控制规则，以便在发生错误时不执行个性化步骤。

* **定位后**:通过在定位后执行，您可以了解目标的卷以应用控制规则。

   例如，**Check校样大小**&#x200B;控制规则在定位阶段之后应用：如果校样收件人过多，此规则将阻止准备消息个性化。

* **开始个性化时**:当检查与消息个性化批准相关时应用。在分析阶段期间执行消息个性化。

* **分析结束时**:需要完成邮件个性化检查时。
