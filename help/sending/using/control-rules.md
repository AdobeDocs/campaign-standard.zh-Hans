---
title: 控制规则
description: 了解如何使用控制规则加强消息的质量检查。
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
feature: Typology Rules
role: User
level: Intermediate
exl-id: 6461c128-1e42-4685-88f8-507244147e6f
TQID: https://experienceleague.adobe.com/lpPFofV3IPl7zmbaR4TOuyCcVqgjwI3maxr-jKzkd0Q
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 449
ht-degree: 15%

---

# 控制规则 {#control-rules}

利用控制规则，可在发送消息之前检查消息的有效性和质量，如字符显示、短信消息大小、地址格式等。

>[!NOTE]
>
>出于安全原因，控制规则是只读的，无法修改。

## 默认控制规则 {#default-control-rules}

一组默认规则可确保标准控件。 下表提供了有关这些规则的信息，以及它们的相关渠道和[执行阶段](#control-rules-execution-phases)。

| 标签 | 渠道 | 执行阶段 | 说明 |
|---------|----------|---------|---------|
| **[!UICONTROL A/B Test]** | 电子邮件 | 在个性化开始时 | 通过A/B测试提取投放的测试群体。 |
| **[!UICONTROL Check delivery size]** | 全部 | 定位后 | 检查消息的大小。 |
| **[!UICONTROL Check email content is not empty]** | 电子邮件 | 定位后 | 如果消息的内容为空，则生成错误。 |
| **[!UICONTROL Check In-App content for broadcast template]** | 应用程序内 | 在开始进行个性化时 | 检查广播模板的应用程序内内容/触发器是否不为空。 |
| **[!UICONTROL Check In-App content for profile template]** | 应用程序内 | 在个性化开始时 | 检查配置文件模板的应用程序内内容/触发器是否不为空。 |
| **[!UICONTROL Check In-App content for subscriber template]** | 应用程序内 | 在个性化开始时 | 检查订阅者模板的应用程序内内容/触发器是否不为空。 |
| **[!UICONTROL Check proof size]** | 全部 | 定位后 | 如果验证目标群体超过100个收件人，则生成错误消息。 |
| **[!UICONTROL Check social network sharing link]** | 电子邮件 | 在个性化开始时 | 在内容中包含社交网络共享链接（病毒链接）时，检查是否存在指向镜像页面的链接。 |
| **[!UICONTROL Check subject]** | 电子邮件 | 在个性化开始时 | 检查主题和发件人地址是否不包含可能导致某些邮件传输代理出现问题的特殊字符，并检查邮件主题是否已完成。 |
| **[!UICONTROL Check unsubscription link]** | 电子邮件 | 在个性化开始时 | 检查每个内容（HTML和文本）中是否存在至少一个退订（选择退出）URL。 |
| **[!UICONTROL Check URL labels]** | 电子邮件 | 在个性化开始时 | 检查每个跟踪URL是否都有标签。 |
| **[!UICONTROL Check URLs]** | 电子邮件 | 在个性化开始时 | 检查跟踪URL（存在“&amp;”字符）。 |

## 控制规则执行阶段 {#control-rules-execution-phases}

可在投放生命周期的不同阶段应用控制规则：

* **在定位**&#x200B;开始时：可以在此阶段应用控制规则，以便在出错时不执行个性化步骤。

* **定位后**：定位后执行允许您了解目标的卷以应用控制规则。

  例如，**检查校样大小**&#x200B;控制规则在定位阶段后应用：如果校样收件人过多，此规则将阻止准备消息个性化。

* **在个性化开始时**：当检查与邮件个性化审批相关时应用。 在分析阶段执行消息个性化。

* **在分析结束时**：检查要求完成邮件个性化时。
