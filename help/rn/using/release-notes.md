---
title: 最新版本
description: 此页面详细描述最新 Campaign Standard 版本的内容
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: a8013bac719a45442e09d710db12df0abe721cc4
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 38%

---


# 最新版本{#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->

## 24.1 版 - 2024 年冬季版 {#winter-24}

### 改进 {#e-rn-improvements}

* **Android推送通知** - Adobe Campaign Standard 24.1使用HTTP v1 API发送Android推送通知消息，以确保与即将发布的FCM更改兼容。 请参阅[此技术说明](../../administration/using/push-technote.md)以了解详情。

* **iOS推送通知** - Adobe Campaign Standard 24.1现在支持iOS推送通知的p8身份验证证书。 必须调整您的实施以激活这些更改。请参阅[此技术说明](../../administration/using/push-technote.md)以了解详情。

* **一键式列表取消订阅**  — 从2024年6月1日开始，Google和Yahoo！ 将要求发件人使用一键式 List-Unsubscribe 功能。Campaign 现已支持此功能。可在[此部分](../../administration/using/configuring-email-channel.md#list-of-email-smtp-parameters)中了解详情。

* **基础架构** - Postgres数据库已从版本11.22升级到版本12.17。

* **CTA跟踪**  — 现在，当用户打开并单击个性化URL时，将跟踪已解析的个性化URL，而不是编码的个性化URL。 默认情况下不启用此更改。 要在您的Campaign实例中启用它，请联系您的Adobe代表。

* **个性化字段下拉列表**  — 在Adobe Experience Manager中创建事务性电子邮件模板时，您现在可以从下拉列表中选择个性化字段。 默认情况下不启用此更改。 要在您的Campaign实例中启用它，请联系您的Adobe代表。

### 修复 {#e-rn-fixes}

* 修复了导致在 30 天后无法从隔离中删除退回电子邮件地址的问题。(CAMP-52977)
* 修复了导致投放警报工作流停止并出现以下错误的问题：`division by zero`。(CAMP-49786)

