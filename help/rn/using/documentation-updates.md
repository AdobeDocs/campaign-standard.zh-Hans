---
title: 文档更新
description: 了解有关 Adobe Campaign Standard 文档的所有最新更新内容
feature: Overview
role: User
level: Beginner
exl-id: 3f77825e-cb98-4cb1-9775-a8b6995e9da1
source-git-commit: 8702a07c50afa82a24b79cf768ab079f6384cf3f
workflow-type: ht
source-wordcount: '7258'
ht-degree: 100%

---

# 文档更新{#documentation-updates}

除了 Adobe Campaign [发行说明](../../rn/using/release-notes.md)，本页还列出了 Adobe Campaign Standard 文档的所有新更新内容。

## 24.1 版 - 2024 年冬季版 {#release-24-1}

2024 年冬季版 Campaign Standard 24.1 的发行说明已发布。[了解更多信息](release-notes.md)

## 2023 年 12 月 {#doc-updates-dec-2023}

Android Firebase Cloud Messaging (FCM) 服务的一些重要更改将于 2024 年发布，并将影响您的 Adobe Campaign 实施。请参阅[此技术说明](../../administration/using/push-technote.md)以了解详情。

## 23.2 版 - 2023 年秋季 {#release-23-2}

* Campaign Standard 23.2 2023 年秋/冬版的发行说明已发布。[了解更多信息](release-notes.md)

* JWT（JSON Web 令牌）目前正在被逐步停用，它将被 OAuth 取代。此项转换工作将在 Campaign 的后续版本中逐步执行，会对文档进行更新以反映这些变化。

## 2023 年 10 月 {#doc-updates-oct-2023}

* Experience Cloud Triggers 的新用户界面现已可用。它提供了一种直观的体验，用于管理消费者行为并个性化用户体验。 [了解更多信息](https://experienceleague.adobe.com/docs/experience-cloud/triggers/overview.html?lang=zh_Hans){target="_blank"}。

* 已添加有关将陷阱测试用户档案与筛选或疲劳规则结合使用的注释。[了解更多信息](../../sending/using/using-traps.md)

## 23.1 版 - 2023 年春/夏版 {#release-23-1}

Campaign Standard 23.1 2023 年春/夏版的发行说明已发布。[了解更多信息](release-notes.md)

## 2022 年 11 月 {#doc-updates-november-2022}

添加了建议避免投放的 ID 字段中存在空格的注释。[了解更多信息](../../channels/using/creating-an-email.md)

在 **[!UICONTROL Extract file]** 工作流活动页面上添加了有关将数据提取至具有特定编码的 CSV 文件中的信息。[了解更多信息](../../automating/using/extract-file.md)

## 22.3 版 - 2022 年秋冬版 {#release-22-3}

Campaign Standard 22.3 2022 年秋/冬版的发行说明已发布。[了解更多信息](release-notes.md)

<!--Data retention periods have been updated to reflect changes coming with 22.3 release. [Read more](../../administration/using/data-retention.md)-->


## 22.2 版 - 2022 年 6 月 {#release-22-2}

**该版本中包含的改进**

**Adobe 通知服务** - Campaign 附带“Adobe 通知服务”，此服务允许 Experience Cloud 解决方案提醒 Experience Cloud 的用户注意对他们而言非常重要的活动。[阅读更多](../../administration/using/sending-internal-notifications.md)。

**其他变更**

现已弃用与 Adobe Experience Platform Data Connector 和 Audience Destinations 服务的集成。[了解更多信息](deprecated-features.md)

详细说明了 SMTP 测试模式的用法。[了解更多信息](../../administration/using/configuring-email-channel.md#smtp-test-mode)

## 2022 年 3 月 {#doc-updates-march-2022}

请注意，使用用户档案替换发送校样将向所选用户档案的日志中添加记录。[了解更多信息](../../sending/using/testing-messages-using-target.md)

## 22.1 版 - 2022 年 2 月 {#release-22-1}

**版本中包含的改进**

改进了包括从 URL 导入的内容的投放的重试机制。[了解更多信息](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time)

更新了控制审核的选项的访问级别：以前的启用/禁用[审核记录](../../administration/using/audit.md)选项对于[功能管理员](../../administration/using/users-management.md#functional-administrators)来说是无法访问的。进行此次更改后，将修改审核的访问级别，从而向功能管理员提供控制权限。[了解更多信息](../../administration/using/audit.md#enable-disable-audit)

新的 **Job history** 下拉列表已添加至消息仪表板。[了解更多信息](../../sending/using/monitoring-a-delivery.md)

**其他变更**

添加了有关触发自动短信回复的关键词的警告说明：它们必须只包含字母数字字符。[了解更多信息](../../channels/using/managing-incoming-sms.md)

在 A/B 测试电子邮件部分添加了注释：如果总人群数少于 5 万，则每种变体需要至少代表总人群的 10%。否则，日志将显示警告。[了解更多信息](../../channels/using/designing-an-a-b-test-email.md)

更新了&#x200B;**传输文件**&#x200B;活动中 **[!UICONTROL Delete the source files after transfer]** 选项的描述，包括对在未选择该选项的情况下手动监控 SFTP 目录中存档内容大小的提醒。[了解更多信息](../../automating/using/transfer-file.md)

更新了&#x200B;**隐私**&#x200B;部分中所有过期的链接。[了解更多信息](../../start/using/privacy.md)

在 Campaign Standard 文档目录中添加了指向 Campaign 控制面板文档的直接链接。

## 21.3 版 - 2021 年 9 月 {#release-21-3---september-2021}

**此版本中包含的新增功能**

改进后的统一 Experience Cloud 界面 - [阅读更多](../../start/using/interface-description.md#top-bar)

全新审核记录功能 - [阅读更多](../../administration/using/audit.md)

工作流诊断模式 - [阅读更多](../../automating/using/managing-execution-options.md)

**随版本提供的其他文档更新**

新增了关于如何从隔离列表中删除地址的新章节。[阅读更多](../../sending/using/understanding-quarantine-management.md#removing-a-quarantined-address)

**隔离与阻止列表**&#x200B;一节经过了修订。[阅读更多](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)

## 2021 年 7 月 {#doc-updates-july-2021}

添加了介绍如何允许用户从单个登陆页面订阅或取消订阅多项服务的新章节。[阅读更多](../../channels/using/managing-landing-page-form-data.md#multiple-subscriptions)

已更新并阐明&#x200B;**管理登陆页面表单数据**&#x200B;部分。[阅读更多](../../channels/using/managing-landing-page-form-data.md)

## 21.2 版 - 2021 年 6 月 {#release-21-2---june-2021}

**此版本中包含的新增功能**

登陆页面验证 - 您现在可以向登陆页面添加强制协议选项。[阅读更多](../../channels/using/managing-landing-page-form-data.md#agreement-checkbox)

**电子邮件大小**&#x200B;部分更新了有关电子邮件最大大小的信息，最大大小现在默认设置为 100 MB。[阅读更多](../../sending/using/design-and-personalize.md#email-size)

**随版本提供的其他文档更新**

添加了有关如何更改事务推送通知中的目标映射的信息。[了解更多信息](../../channels/using/transactional-push-notifications.md#change-target-mapping)

## 2021 年 5 月 {#doc-updates-may-2021}

**活动用户档案**&#x200B;报告部分已更新。[阅读更多](../../audiences/using/active-profiles.md)

**发行计划**&#x200B;页面已更新了新日期。 [阅读更多](../../rn/using/release-planning.md)


## 2021 年 4 月 {#doc-updates-april-2021}

添加了新的章节，介绍如何使用 Adobe Experience Platform Sources 与 Destinations 在 Campaign Standard 和 Adobe Real-time Customer Data Platform (RTCDP) 之间共享数据。[阅读更多](../../integrating/using/get-started-sources-destinations.md)

## 2021 年 3 月 {#doc-updates-march-2021}

新的&#x200B;**帮助和支持选项**&#x200B;页面。 [阅读更多](../../support.md)

在列出发送消息的关键步骤的部分，增加了其他信息和参考内容。[阅读更多](../../channels/using/key-steps-to-send-a-message.md)

已新增信息来说明在查询中选择 au 受众时，其定义将被复制而不被引用。[阅读更多](../../audiences/using/selecting-an-audience-in-a-message.md)

与 Audience Destinations Service（受众目标服务）和 Adobe Experience Platform Data Connector 相关的信息已重新归纳为一个新的小节。

**Declared ID** 数据源现在还可以与 People 核心服务集成一起使用。Campaign-Audience Manager 或 People 核心服务集成文档中添加了信息。[阅读更多](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

添加了有关如何为移动设备应用程序实施本地跟踪的信息。[阅读更多](../../administration/using/local-tracking.md)

[可投放性](../../sending/using/about-deliverability.md)部分已更新，现包括指向新的 [Adobe 可投放性最佳实践指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=zh-Hans)的链接。所有与适用于各种 Adobe 解决方案的可投放性相关的一般信息均已移至[最佳实践指南附录](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=zh-Hans#additional-resources)。

## 21.1 版 - 2021 年 2 月 {#release-21-1---february-2021}

**此版本中包含的新增功能**

电子邮件反馈服务 - [阅读更多](../../sending/using/confirming-the-send.md#message-indicators)

Adobe Experience Manager 集成改进 - [阅读更多](../../integrating/using/creating-multilingual-email-aem.md)

统一 Experience Cloud 界面 - [阅读更多](../../start/using/interface-description.md#top-bar)

**随版本提供的其他文档更新**

已添加有关如何根据电子邮件、名字、姓氏或任何自定义字段搜索用户档案的信息。[阅读更多](../../audiences/using/integrated-customer-profile.md)

已添加有关新 GetOption 函数的信息，通过该函数可在使用外部参数调用工作流时返回指定函数的值。[阅读更多](../../automating/using/customizing-workflow-external-parameters.md#using-events-variables)

已添加有关在使用 **[!UICONTROL Transfer file]** 活动后可用的新 **[!UICONTROL filesCount]** 输出变量的信息。[阅读更多](../../automating/using/transfer-file.md#output-variables)

**配置电子邮件渠道**&#x200B;部分已更新，以明确最新的适用电子邮件设置。页面底部列出了某些客户仍在使用的一些旧参数。[阅读更多](../../administration/using/configuring-email-channel.md)

添加了相关信息以说明如何确保只有在先前执行的一个或多个任务仍未完成时才会重新安排预定的工作流。[阅读更多](../../automating/using/scheduled-workflows-execution.md)

## 2020 年 12 月 {#doc-updates-december-2020}

现已弃用&#x200B;**预测主题行**。[阅读更多](../../rn/using/deprecated-features.md)

**开始使用事务性消息**&#x200B;部分现在包括[增强的模式](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)，以便更好地了解该过程。

现提供一个用于说明事务性消息传递实施过程的端到端用例。[阅读更多](../../channels/using/transactional-messaging-use-case.md)

**隐私**&#x200B;部分已移至[此处](../../start/using/privacy.md)。

提供新的&#x200B;**辅助功能**&#x200B;页面：其中详细介绍 Adobe Campaign Standard 工作区中的辅助功能支持。[阅读更多](../../start/using/accessibility.md)

添加了警告说明，为获得最佳性能，已发布的事务性消息数应保持在 100 以下。[阅读更多](../../channels/using/transactional-messaging-limitations.md#transactional-message-number)

“短信连接器协议和设置”页面已移至[此处](../../administration/using/sms-protocol.md)。

**在事务性消息中使用产品列表**&#x200B;部分已移至[此处](../../designing/using/using-product-listings.md)。

## 2020 年 11 月 {#doc-updates-november-2020}

**个人数据和角色**&#x200B;部分已使用用例场景进行更新，以说明不同角色在隐私方面如何进行交互。[阅读更多](../../start/using/privacy.md#use-case-scenario)

新增了一个部分，其中列出有关隐私的常见问题解答。[阅读更多](../../start/using/privacy-faq.md)

**隐私**&#x200B;部分已移动并新增两个页面：[隐私管理](../../start/using/privacy-management.md)和[管理隐私请求](../../start/using/privacy-requests.md)。

**事务性消息**&#x200B;部分已重新组织并汇集到一处，以改进导航。[阅读更多](../../channels/using/getting-started-with-transactional-msg.md)

在“Adobe Experience Platform Data Connector”部分中添加了有关与隐私管理相关的数据映射验证错误以及如何对其进行疑难解答的信息。

## 20.4 版 - 2020 年 10 月 {#release-20-4---october-2020}

**此版本中包含的新增功能**

控制 - [阅读更多](../../sending/using/control-group.md)

外部 API（OAuth 支持）- [阅读更多](../../automating/using/external-api.md)

Journey AI 集成 - [阅读更多](../../sending/using/predictive.md)

**随版本提供的其他文档更新**

有关如何使用外部参数调用工作流的部分已通过表达式编辑器中提供的新功能进行了扩充。[阅读更多](../../automating/using/customizing-workflow-external-parameters.md)

已向工作流最佳实践中添加了关于每个工作流要使用的活动数的建议。[阅读更多](../../automating/using/best-practices-workflows.md#number-activities)

已新增关于“投放最佳实践”的部分。[阅读更多](../../sending/using/delivery-best-practices.md)

已添加一个部分来描述新过滤器，这些新过滤器支持根据其状态和上次收到事件的时间来搜索事件配置。[阅读更多](../../channels/using/configuring-transactional-event.md#searching-transactional-events)

## 2020 年 9 月 {#doc-updates-september-2020}

已重新组织并阐明&#x200B;**事件事务性消息**&#x200B;部分。[阅读更多](../../channels/using/editing-transactional-message.md)

添加了警告说明，以警告用户与日志访问权有关的权限限制。[阅读更多](../../administration/using/users-management.md)

添加了新部分以详细说明创建新品牌的过程。[阅读更多](../../administration/using/branding.md#creating-a-brand)

现在提供新的 Campaign Standard - Microsoft Dynamics 365 集成。[阅读更多](../../integrating/using/d365-acs-get-started.md)

已在活动用户档案报告中添加了有关匿名源的信息。[阅读更多](../../audiences/using/active-profiles.md)

## 2020 年 8 月 {#doc-updates-august-2020}

提供有关事务性消息传递入门的新更新部分。[阅读更多](../../channels/using/getting-started-with-transactional-msg.md)

**事务性消息传递限制**&#x200B;部分已移至[此处](../../channels/using/transactional-messaging-limitations.md)。

**准备发送**&#x200B;部分已移至[此处](../../sending/using/preparing-the-send.md)。

## 2020 年 7 月 {#doc-updates-july-2020}

添加了新部分，其中包含与 Campaign Standard 监控相关的准则。[阅读更多](../../administration/using/monitoring-guidelines.md)

外部 API 护栏和限制部分已更新。[了解更多信息](../../automating/using/external-api.md#guardrails)

“隐私管理概述”页面已更新，包含有关泰国的个人数据保护法 (PDPA) 和巴西的 Lei Geral de Proteção de Dados (LGPD) 的信息。[了解更多信息](https://helpx.adobe.com/cn/campaign/kb/campaign-privacy-overview.html#whatisgdpr)

已重组和改进移动渠道指南。添加了新的移动渠道配置指南，其中包含有关移动配置的技术文档。[阅读更多](../../administration/using/push-tracking.md)

Campaign Standard 页面中的“隐私管理”已更新，包括阐明如何通过隐私核心服务集成来管理隐私请求。[阅读更多](https://helpx.adobe.com/cn/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)

AI 支持的新电子邮件功能：发送时间优化和用户档案评分。[阅读更多](../../sending/using/predictive.md)

## 2020 年 6 月 {#doc-updates-june-2020}

工作流用例已更新并重新组织为主题部分。[阅读更多](../../automating/using/about-workflow-use-cases.md)

在如何使用控制面板和活动工作流[加密](../../automating/using/managing-encrypted-data.md#use-case-gpg-encrypt)和[解密](../../automating/using/managing-encrypted-data.md#use-case-gpg-decrypt)数据方面添加了用例。

对旧版支持网站的引用已替换为新 URL。[了解详情](../../support.md)

已从收件箱呈现功能中删除自定义 Litmus 帐户配置。[阅读更多](../../sending/using/email-rendering.md)

Campaign Standard - Microsoft Dynamics 365 集成当前不可用。正在开发新的连接器，并将在将来推出。已删除相关帮助页面。[阅读更多](../../integrating/using/d365-acs-get-started.md)

## 2020 年 5 月 {#doc-updates-may-2020}

Campaign Standard 概述页面进行了扩充，并重组到了专门的主题中。[了解更多](../../start/using/about-campaign-standard.md)

进一步阐明了“电子邮件渠道参数”一节，添加了关于授权掩码字段和投放报告 ID 的更多信息。[了解更多](../../administration/using/configuring-email-channel.md)

现在，核心文档中提供了使用 Adobe Experience Platform SDK 配置移动应用程序的内容，添加了关于通过 Launch 技术工作流程同步移动应用程序 AEPSDK 的更多信息。[阅读更多](../../administration/using/configuring-a-mobile-application.md)

## 20.3 版 - 2020 年 5 月 {#release-20-3---may-2020}

**此版本中包含的新增功能**

泰国个人数据保护法 (PDPA) - [了解更多](https://helpx.adobe.com/cn/campaign/kb/acs-privacy.html)

External API 活动 (GA) - [了解更多](../../automating/using/external-api.md)

**随版本提供的其他文档更新**

在工作流属性的 **[!UICONTROL History in days]** 字段中添加了信息，现在其中包含了通过 **[!UICONTROL Transfer file]** 活动下载的文件。[了解更多](../../automating/using/managing-execution-options.md)

在用户档案替换一节中，添加了有关主题行前缀 500 个字符限制的信息。[了解更多](../../sending/using/testing-messages-using-target.md)

核心文档中添加了有关隐私和同意的专述章节。[了解更多](../../start/using/privacy.md)

添加了一个使用案例，用于将旧版编辑器电子邮件转换为 Email Designer。[了解更多](../../designing/using/converting-emails-from-legacy-editor.md)

添加了有关 Email Designer 的常见问题章节。[阅读更多](../../designing/using/faq-email-designer.md)

## 2020 年 4 月 {#doc-updates-april-2020}

核心文档中现在提供了关于 Microsoft Dynamics 365 与 Adobe Campaign Standard 集成的文档。[了解更多](../../integrating/using/d365-acs-get-started.md)

文档主页添加了其他资源。[了解更多](../../campaign-standard-home.md)

Adobe Experience Platform Data Connector 文档中增加了与 Experience Cloud ID Service (ECID) 相关的信息。

改进了“事务性消息传递”部分，包含有关如何访问最新事务性事件和已更新的屏幕截图的信息。[了解更多](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)

对“类型和类型规则”章节进行了修改，并更新了关于内置类型规则的更多信息。[了解更多](../../sending/using/about-typology-rules.md)

添加了关于 **[!UICONTROL Transfer file]** 活动的 **[!UICONTROL File listing]** 操作的信息。[了解更多](../../automating/using/transfer-file.md)

更新了关于投放临时失败后重试的文档，提供了有关升级到 Enhanced MTA 后如何管理重试的更多详细信息。[了解更多](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)

增强并阐明了“删除事务型消息”章节。[了解更多](../../channels/using/publishing-transactional-message.md#deleting-a-transactional-message)

更新了&#x200B;**预览投放**&#x200B;章节，添加了移动投放示例。[了解更多](../../sending/using/previewing-messages.md)

添加了有关事务型消息传递和删除未使用实时事件的最佳做法。[了解更多](../../channels/using/configuring-transactional-event.md#creating-an-event)

更新了“配置电子邮件渠道”章节，明确了现在由 Adobe Campaign Enhanced MTA 管理的所有电子邮件设置。[了解更多](../../administration/using/configuring-email-channel.md)

更新了“事务性消息传递”部分，包含有关编辑事件配置所需的权限以及如何扩充事务性消息中的集合的更多信息。[阅读更多](../../channels/using/configuring-transactional-event.md)。

## 20.2 版 - 2020 年 4 月 {#release-20-2---april-2020}

**此版本中包含的新增功能**

Azure Blob 集成 - [了解更多](../../administration/using/external-accounts.md#microsoft-azure-external-account)

使用定向的用户档案测试电子邮件 - [了解更多](../../sending/using/testing-messages-using-target.md)

**随版本提供的其他文档更新**

对应用程序内消息渲染添加了限制。[了解更多](../../channels/using/customizing-an-in-app-message.md)

添加了有关如何在 **[!UICONTROL Query]** 活动中使用聚合的信息。[了解更多](../../automating/using/query.md#adding-an-aggregate)

添加了配置移动应用程序时的 MCPNS 限制。[了解更多](https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdk.html)

《管理指南》中新增了“配置准则”一节。关于兼容浏览器和操作系统的章节已从快速入门指南移到了此章节。此章节还添加了关于 Campaign Standard 网络端点的技术说明。[了解更多](../../administration/using/about-configuration-guidelines.md)

添加了新的章节，描述如何删除事件配置。[了解更多](../../channels/using/publishing-transactional-event.md#deleting-an-event)

更新了“事务型消息传递”一节，以反映多个用户界面的轻微更新和改进。[了解更多](../../channels/using/getting-started-with-transactional-msg.md)

更新了与 External API 活动防护相关的信息。[了解更多](../../automating/using/external-api.md)

## 2020 年 3 月 {#doc-updates-march-2020}

核心文档中添加了关于 Enhanced MTA 的更多详细信息，特别是关于电子邮件处理规则和退回邮件鉴别的信息。[了解更多](../../administration/using/configuring-email-channel.md#email-processing-rules)

移动并更新了“通过电子邮件密送进行归档”的专述章节。[了解更多](../../sending/using/archiving.md)

更新了“配置移动应用程序”的文档和相关页面，以反映 SDK V4 已被弃用。[了解更多](https://experienceleague.adobe.com/docs/discontinued/using/mobile-services.html?lang=zh-Hans)

更新并修正了 Adobe Campaign Standard/Adobe Experience Manager 集成文档。[了解更多](../../integrating/using/configure-experience-manager.md)

更新了 Campaign Email Designer 文档和相关页面，以反映 [!DNL Adobe Creative SDK] 弃用。[了解更多](../../rn/using/deprecated-features.md)

新增了专门介绍 Campaign Standard 数据模型最佳做法的新章节。[了解更多](../../developing/using/data-model-best-practices.md)

添加了关于 **[!UICONTROL Workflow]** 内置权限的信息。[了解更多](../../administration/using/list-of-roles.md)

添加了关于工作流属性中可用 **[!UICONTROL History in days field]** 的信息。[了解更多](../../automating/using/about-workflow-execution.md)

## 20.1 版 - 2020 年 2 月 {#release-20-1---february-2020}

**此版本中包含的新增功能**

Adobe Experience Platform Data Connector（Beta 版）

Audience Destinations（Beta 版）

**随版本提供的其他文档更新**

更新了隐私管理文档中关于如何为自定义用户档案资源创建 CCPA 选择退出字段的信息。[了解更多](https://helpx.adobe.com/cn/campaign/kb/acs-privacy.html)

重组并改进了发行说明。[了解更多](../../rn/using/release-notes.md)

添加了与管理员安全组相关的信息，指定将 **[!UICONTROL All (all)]** 组织单元分配给管理员安全组，且不能修改。[了解更多](../../administration/using/managing-groups-and-users.md)

添加了有关如何定义工作流中默认时区的信息。[了解更多](../../automating/using/building-a-workflow.md)

在“使用 API”指南中添加了有关 **_forcePagination=true** 新参数的信息，以便对较大的表格执行分页。[了解更多](../../api/using/pagination.md)

添加了新章节，以介绍可在消息仪表板中显示的警告。[了解更多](../../channels/using/message-dashboard.md#warnings)

新增了 Adobe Campaign Enhanced MTA 文档，其中描述了升级后的发送架构如何改进可投放性、吞吐量和退件处理。[了解更多](https://helpx.adobe.com/cn/campaign/kb/campaign-enhanced-mta.html)

添加了注释，指明应用程序服务器和镜像页面服务器 URL 必须是安全的，才能从 Campaign 用户界面显示登录页和镜像页面的预览。[了解更多](../../administration/using/branding.md#configuring-and-using-brands)

更新了“导出日志”一节，以反映投放日志和跟踪日志资源中的投放日志 ID 的可用性，利用该 ID 可导出各个日志的唯一标识符。[了解更多](../../automating/using/exporting-logs.md)

## 2020 年 1 月 {#doc-updates-january-2020}

更新了“可投放性”文档，新增了“IP 认证”一节。<!--[Read more](../../sending/using/ip-certification.md)-->

新增了描述如何创建跨渠道投放工作流的章节。[了解更多](../../automating/using/workflow-cross-channel-delivery.md)

更新了关于动态报告的指标计算章节。[了解更多](../../reporting/using/indicator-calculation.md)

新增了关于 Adobe Campaign Standard 中移动投放一般准则的页面。[了解更多](https://helpx.adobe.com/cn/campaign/kb/acs-mobile.html)

更新了“使用 Campaign 和 Experience Manager”文档，新增了名为&#x200B;**如何使用 Campaign-Experience Manager 集成的提示**&#x200B;的新章节。[了解更多](../../integrating/using/integrating-with-experience-manager.md#tips-aem)

改进了 API 文档的主页，重新指向不同的主题。[了解更多](../../api/using/get-started-apis.md)

## 2019 年 11 月至 12 月 {#doc-updates-december-2019}

更新了“配置 S3 外部帐户”文档。[了解更多](../../administration/using/external-accounts.md#amazon-s3-external-account)

重组了“设计电子邮件内容”章节。[了解更多](../../designing/using/designing-content-in-adobe-campaign.md)

将“可投放性”快速入门指南集成到了核心文档中并进行了更新。[了解更多](../../sending/using/about-deliverability.md)

将有关如何导出/导入自定义资源的快速入门指南集成到了核心文档中。[了解更多](../../automating/using/exporting-importing-custom-resources.md)

新增了一个使用案例，描述如何使用 Campaign Standard 中的工作流构建对照组。

与登陆页面属性有关的信息已移入专述章节。[阅读更多](../../channels/using/configuring-landing-page.md)

控制面板文档已集成到新的协作文档集中。[了解更多](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hans)

更新了&#x200B;**指标计算**&#x200B;表格。[了解更多](../../reporting/using/indicator-calculation.md)

将 API 文档集集成到了 Campaign Standard 文档中。[了解更多](../../api/using/get-started-apis.md)

移动并更新了“创建个性化电子邮件”入门部分。[阅读更多](https://helpx.adobe.com/cn/campaign/kb/acs-get-started-with-emails.html)

投放最佳实践快速入门指南已更新。[了解更多](../../sending/using/delivery-best-practices.md)

将“数据模型”集成到了 Campaign Standard 文档中。[了解更多](../../developing/using/datamodel-audience.md)

向 API 文档添加了新的 API 端点 **/customResources**。[了解更多](../../api/using/interacting-with-custom-resources.md)

## 19.4 版 - 2019 年 10 月 {#release-19-4---october-2019}

**此版本中包含的新功能**

加利福尼亚消费者隐私法 (CCPA) - [了解更多](https://helpx.adobe.com/cn/campaign/kb/acs-privacy.html#ccpa)

Microsoft Dynamics 365 集成 (GA) - [了解更多](../../integrating/using/d365-acs-get-started.md)

**随版本提供的其他文档更新**

Adobe Campaign 的错误消息列表已更新。[阅读更多](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=zh-Hans)

GDPR 入门指南已得到改进和丰富。它现在是包括 GDPR 和 CCPA 在内的隐私管理文档。[了解更多](https://helpx.adobe.com/content/help/cn/campaign/kb/campaign-privacy.html)

添加了用于表示事务型消息传递发布过程的新图表。[了解更多](../../channels/using/publishing-transactional-message.md#transactional-messaging-pub-process)

移动并更新了“投放最佳做法”快速入门指南。[了解更多](../../sending/using/delivery-best-practices.md)

添加了新章节。新的章节提供了扩充 Campaign Standard 数据库的各种方法概述。[了解更多](../../audiences/using/enriching-campaign-database.md)

添加了新章节，其中介绍了如何设置链接 Email Designer 的样式。[了解更多](../../designing/using/styles.md#about-styling-links)

API 文档中添加了与隐私相关的信息，[单击此处](../../api/using/creating-a-privacy-request.md)

## 2019 年 9 月至 10 月 {#doc-updates-october-2019}

添加了与 Campaign Standard 设置相关的新章节。[了解更多](../../administration/using/about-campaign-standard-settings.md)

添加了新章节，介绍如何向订阅特定服务的用户档案自动发送自定义确认电子邮件。[了解更多](../../audiences/using/confirming-subscription-to-a-service.md)

修改了“事务型消息传递”章节，更新了最新的 UI，包括使用 Email Designer 编辑内容。[了解更多](../../channels/using/editing-transactional-message.md)

重组了登陆页面章节。此外，还增加了一个新章节，详细说明了建立登陆页面的步骤。[了解更多](../../channels/using/getting-started-with-landing-pages.md)

在“推送通知”章节中新增了一节，介绍如何根据移动应用程序的订阅数据创建和更新用户档案信息。[了解更多](../../channels/using/updating-profile-with-mobile-app-data.md)

新增了一个示例，展示如何发送包含（检索自加载文件活动）附加数据的电子邮件。[了解更多](../../automating/using/sending-email-enriched-fields.md)

新增了关于如何使用陷阱的章节。[了解更多](../../sending/using/using-traps.md)。

在关于如何使用 Adobe Experience Platform SDK 配置移动应用程序的页面中，添加了关于 **Launch_URL_Campaign** 选项的说明。[了解更多](https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdk.html)

重组了 Email Designer 指南。[了解更多](../../designing/using/designing-content-in-adobe-campaign.md)

## 2019 年 8 月 {#doc-updates-august-2019}

添加了新章节，介绍了着重于查询的工作流使用案例。[了解更多](../../automating/using/workflow-created-query-with-complement.md)

在工作流疑难解答章节中添加了一个程序，介绍如何在日志选项卡中显示 SQL 查询。[了解更多](../../automating/using/best-practices-workflows.md#troubleshooting-data-management-activities)

新增了一篇帮助文章，提供了与控制面板中的子域和证书管理相关的信息。[了解更多](https://experienceleague.adobe.com/docs/control-panel/using/subdomains-and-certificates/subdomains-branding.html?lang=zh-Hans)

更新了描述内容模板和片段的章节。[了解更多](../../designing/using/using-reusable-content.md#content-templates)

添加了新章节，介绍如何在 Email Designer 中将电子邮件内容另存为模板。[了解更多](../../designing/using/using-reusable-content.md#saving-content-as-template)

## 19.3 版 - 2019 年 7 月 {#release-19-3---july-2019}

**此版本中包含的新增功能**

External API Activity (Public Beta) - [了解更多](../../automating/using/external-api.md)

工作流区段报告 - [了解更多](../../reporting/using/creating-a-report-workflow-segment.md)

**随版本提供的其他文档更新**

Campaign Standard 实施指南现已上线。[了解更多](https://helpx.adobe.com/cn/campaign/kb/campaign-standard-implementation-guide.html)

创建了关于 Microsoft Dynamics 365 连接器实施和用法的一组新帮助文章。请注意，此功能当前处于“有限可用”状态。[了解更多](../../integrating/using/d365-acs-get-started.md)

在[使用参数调用工作流](../../automating/using/calling-a-workflow-with-external-parameters.md)章节中添加了有关投放准备及其聚合期的说明。

添加了有关如何使用在工作流外部信号活动中声明的事件变量对投放标签进行个性化的信息。[了解更多](../../automating/using/external-signal.md)

添加了新章节，详细介绍如何在 Adobe Campaign Standard 中创建用户。[了解更多](../../administration/using/users-management.md)

添加了一篇新文章，其中包含可简化营销策划的提示，包括指向产品文档和教程视频的链接。[了解更多](https://helpx.adobe.com/cn/campaign/kb/simplify-campaign-management.html)

为“动态报告”添加了疑难解答内容。[了解更多](../../reporting/using/troubleshooting.md)

添加了插图，用于说明各种应用程序内模板如何处理个人信息。[了解更多](../../channels/using/preparing-and-sending-an-in-app-message.md)

更新了介绍如何在 Email Designer 中将电子邮件内容另存为片段的章节。[了解更多](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)

添加了一条警告，说明额外的空格对于电子邮件内容布局的影响。[了解更多](../../designing/using/personalization.md#creating-custom-content-blocks)

添加了关于 Email Designer 推荐更新的新章节。[了解更多](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-updates)

<!-- A new section on how to send proofs using real customer data has been added. [Read more](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs-using-additional-data) -->

新增了关于工作流最佳实践的章节。[了解更多](../../automating/using/best-practices-workflows.md)

更新了 Campaign Standard 和 Classic 的错误消息列表。[了解更多](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=zh-Hans)

在自定义资源文档中添加了警告。我们建议为自定义资源 ID 最多使用 30 个字符。这也适用于自定义资源字段、键值、索引和链接。[了解更多](../../developing/using/creating-or-extending-the-resource.md)

## 2019 年 6 月至 7 月 {#doc-updates-2019}

添加了有关登陆页面限制的新页面。[了解更多](../../channels/using/getting-started-with-landing-pages.md#landing-page-limitations)

添加了关于如何使用组合检索表调用用户档案的用例。[了解更多](../../developing/using/uc-calling-resource-id-key.md)

添加了一项关于使用参数调用工作流时使用无聚合期定期投放的建议。[了解更多](../../automating/using/calling-a-workflow-with-external-parameters.md)

更新了 Campaign Standard 和 Classic 的错误消息列表。[了解更多](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=zh-Hans)

在自定义资源文档中添加了警告。我们建议为自定义资源 ID 最多使用 30 个字符。这也适用于自定义资源字段、键值、索引和链接。[了解更多](../../developing/using/creating-or-extending-the-resource.md)

## 19.2 版 - 2019 年 5 月 {#release-19-2---may-2019}

**此版本中包含的新功能**

控制面板 - [了解更多](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hans)

本地通知 - [了解更多](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)

工作流增强 - 向外部信号活动添加有效载荷 - [了解更多增](../../automating/using/calling-a-workflow-with-external-parameters.md)

登陆页面增强 - Google reCAPTCHA - [了解更多](../../channels/using/configuring-landing-page.md#setting-google-recaptcha)

**随版本提供的其他文档更新**

更新了“域名委派”文章。[了解更多](https://helpx.adobe.com/cn/campaign/kb/domain-name-delegation.html)

发布了新的“发布计划”文章以共享即将发布的日期。[了解更多](https://helpx.adobe.com/cn/campaign/kb/acs-release-planning.html)

更新了可直接从 Adobe Campaign 访问的上下文帮助链接。

以下[页面](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/overview.html?lang=zh-Hans)将变为 Adobe Campaign Standard 的官方视频页面。

添加了有关数据保留的章节，其中包括标准表格的默认保留值。[了解更多](../../administration/using/data-retention.md)

添加了有关更新和维护操作的章节。[了解更多](../../administration/using/updates-and-maintenance-operations.md)

添加了关于&#x200B;**传输文件**&#x200B;活动中新排序选项的信息。[了解更多](../../automating/using/transfer-file.md)

更新了 [REST API 文档](../../api/using/get-started-apis.md)：

* 添加了新章节，其中包含关于为何使用 Campaign Standard REST API 的一般信息。
* 提供了预先设计好的 API 请求集合，展示了常用的使用案例。
* 新增了关于如何管理组织单位的章节。
* 添加了关于如何创建服务的信息。
* 添加了关于如何使用参数调用工作流的信息。

添加了关于新&#x200B;**测试**&#x200B;活动的信息。[了解更多](../../automating/using/test.md)

更新了自动化指南，提供了指向相关工作流活动的链接。[了解更多](../../automating/using/workflow-interface.md#palette)

更新了关于动态报告的指标计算章节。[了解更多](../../reporting/using/indicator-calculation.md)

添加了动态报告兼容性表格，以更好地理解维度和指标之间的兼容性。[了解更多](https://experienceleague.adobe.com/docs/campaign-standard/assets/dynamic_report_compatibility.pdf)

更新了工作流的功能列表。[了解更多](../../automating/using/list-of-functions.md)

重组并改进了“设计内容”章节，添加了新章节，明确描述了通过 Email Designer 使用现有内容设计电子邮件的各种方法。[了解更多](../../designing/using/using-existing-content.md)

添加了新章节，介绍如何在 Email Designer 中将电子邮件内容另存为片段。[了解更多](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)

更新了“管理链接”章节，提供了关于如何在 Email Designer 中管理跟踪 URL 的附加信息。[了解更多](../../designing/using/links.md#inserting-a-link)

添加了新章节，介绍特定事务型消息的重试过程。[了解更多](../../channels/using/transactional-message-execution.md#transactional-message-retry-process)

阐明并更新了“发布带 API 扩展的资源”章节，改用了最新的 UI。[了解更多](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension)

重命名并重组了“归档电子邮件”章节。[了解更多](../../sending/using/archiving.md)

更新了“创建电子邮件”章节，以反映最新的界面更改。[了解更多](../../channels/using/creating-an-email.md)

更新了[短信连接器协议和设置](https://helpx.adobe.com/cn/campaign/kb/sms-connector-protocol-and-settings.html)知识库文章，介绍了如何向短信外部帐户添加新选项，以限制允许连接到 SMPP 提供商的 MTA 实例数。

扩充并重组了《快速入门指南》。[了解更多](../../start/using/about-campaign-standard.md)

更新了“已弃用和已删除的功能”页面。[了解更多](../../rn/using/deprecated-features.md)

更新并修正了“Dreamweaver 集成”章节。[了解更多](../../designing/using/using-integrations.md#editing-content-in-dreamweaver)

## 19.1 版 - 2019 年 2 月 {#release-19-1---february-2019}

**此版本中包含的新增功能**

推送渠道报告改进 - [了解更多](../../reporting/using/push-notification-report.md)

移动应用的 Launch 集成 - [了解更多](../../administration/using/configuring-a-mobile-application.md#using-adobe-experience-platform-sdk)

移动应用程序内消息传递 - [了解更多](../../channels/using/about-in-app-messaging.md)

工作流增强 - 通过[此处](../../automating/using/workflow-interface.md#duplicating-workflow-activities)和[此处](../../automating/using/load-file.md#configuration)了解更新

**随版本提供的其他文档更新**

在“编辑电子邮件内容”章节中新增了关于创建电子邮件内容以及 Email Designer 其他增强功能的初步体验。[了解更多](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-home-page)

添加了关于事务型消息传递限制的新章节。[了解更多](../../channels/using/transactional-messaging-limitations.md)

添加了对比 Adobe Campaign 中各种电子邮件创作选项的新章节。[了解更多](../../designing/using/using-integrations.md#email-design-options-comparison)

强化了“创建自定义内容块”章节，其详细介绍了关于定向维度的信息。[了解更多](../../designing/using/personalization.md#creating-custom-content-blocks)

添加了指明 Email Designer 不支持 Internet Explorer 11 的警告。[了解更多](../../administration/using/about-configuration-guidelines.md)

向“删除资源”章节中，添加了关于重新起草之影响的警告。[了解更多](../../developing/using/deleting-a-resource.md)

更新了关于如何添加或扩展资源的章节。[了解更多](../../developing/using/creating-or-extending-the-resource.md)

添加了关于如何扩展用户档案自定义资源的使用案例。[了解更多](../../developing/using/extending-the-profile-resource-with-a-new-field.md)

添加了关于如何链接自定义资源的信息。[了解更多](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources)

添加了关于如何从 Adobe Campaign Standard 推送通知显示图像的新技术说明。[了解更多](../../administration/using/image-push-notification.md)

添加了关于推送跟踪实施的新技术说明。[了解更多](../../administration/using/push-tracking.md)

更新了 Campaign Standard 和 Classic 的错误消息列表。[了解更多](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=zh-Hans)

更新了“Triggers - Campaign 集成”文档。[了解更多](../../integrating/using/about-adobe-experience-cloud-triggers.md)

更新了可直接从 Adobe Campaign 访问的上下文帮助链接。

添加了关于为包含“rejects”的文件名添加时间戳的注释。[了解更多](../../automating/using/load-file.md#configuration)

添加了关于导入字段由具有固定长度之列组成时的信息。[了解更多](../../automating/using/load-file.md#configuration)

添加了关于允许在文件中保留 rejects 之选项的信息。现在，可利用此选项，将后处理阶段应用到包含 rejects 的文件。[了解更多](../../automating/using/load-file.md#configuration)

添加了新章节，介绍如何通过复制粘贴操作，复制工作流活动。[了解更多](../../automating/using/workflow-interface.md#duplicating-workflow-activities)

添加了关于查询（[了解更多](../../automating/using/query-samples.md)）和分段（[了解更多](../../automating/using/segmentation.md)）活动中新选项的信息，利用该选项，可在活动后添加叫客过渡（如果未检索到数据）。

在“更新数据活动”章节增加了关于“批次大小”字段的信息，利用该字段可定义上传数据的批次大小上限。[了解更多](../../automating/using/update-data.md#configuration)

在“提取文件活动”章节中增加了有关新选项的信息，利用该选项可在叫客过渡为空时禁用文件生成流程。[了解更多](../../automating/using/extract-file.md#configuration)

## 19.0 版 - 2019 年 1 月 {#release-19-0---january-2019}

**此版本中包含的新增功能**

Email Designer 常规可用性 - [了解更多](../../designing/using/designing-content-in-adobe-campaign.md)

事务型电子邮件中的产品清单 - [了解更多](../../designing/using/using-product-listings.md)

Email Designer 中的移动视图 - [了解更多](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)

应用程序内消息传递测试版改进 - [了解更多](../../channels/using/about-in-app-messaging.md)

**随版本提供的其他文档更新**

更新了设计内容指南，以反映 Email Designer 的常规可用性和旧版电子邮件内容编辑器已被弃用。[了解更多](../../designing/using/designing-content-in-adobe-campaign.md)

更新了[应用程序内](../../channels/using/about-in-app-messaging.md)和[推送通知](../../channels/using/about-push-notifications.md)文档。

添加了关于 Adobe Campaign 中各种类型受众的更多信息。[了解更多](../../audiences/using/about-audiences.md)

更新了“用户和安全”章节，以反映地理单位已被弃用。[了解更多](../../administration/using/organizational-units.md)

添加了关于加载数据活动中新选项的信息，通过该选项可以将后处理阶段应用到包含拒绝记录的文件（例如，Zip 格式压缩）。[了解更多](../../automating/using/load-file.md)

添加了关于更新数据活动中新字段的信息，通过该字段可以配置上传数据的批处理大小上限。[了解更多](../../automating/using/update-data.md)

更新了[从 URL 导入内容](../../designing/using/using-existing-content.md#importing-content-from-a-url)文档，添加了与 Email designer 相关的信息。

向计算机兼容浏览器的列表中添加了 Microsoft Edge（最新版本）。[了解更多](../../administration/using/about-configuration-guidelines.md)

添加了关于提取文件活动新选项的信息，利用该选项可防止在集客过渡为空时生成文件。[了解更多](../../automating/using/extract-file.md)

将“使用 SDK V4 配置移动应用程序”章节移动到了[此处](https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdkv4.html)。

将“使用 Adobe Experience Platform SDK 配置移动应用程序”章节移动到了[此处](https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdk.html)。

将视频更新并移动到了[此处](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/overview.html?lang=zh-Hans)。

更新了“用户类型”章节。[了解更多](../../administration/using/users-management.md)

## 18.9 版 - 2018 年 9 月 {#release-18-9---september-2018}

**此版本中包含的新增功能**

应用程序内消息传递（测试版）- [了解更多](../../channels/using/about-in-app-messaging.md)

适用于移动应用程序的 Adobe Launch 集成（测试版）- [了解更多](../../sending/using/managing-typologies.md)

**随版本提供的其他文档更新**

更新了推送通知指南，更改了界面。[了解更多](../../channels/using/about-push-notifications.md)

添加了有关如何删除受众的信息。[了解更多](../../audiences/using/creating-audiences.md#deleting-audiences)

更新了“推送通知内置报告”章节。[了解更多](../../reporting/using/push-notification-report.md)

## 18.7 版 - 2018 年 7 月 {#release-18-7---july-2018}

**此版本中包含的新增功能**

针对移动应用订阅者的[高优先级标记](../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android)和[类型过滤器](../../sending/using/managing-typologies.md)。

在准备期间，从 URL 自动导入内容。[了解更多](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time)

**随版本提供的其他文档更新**

添加了关于短信连接器协议和设置的新技术说明。[了解更多](https://helpx.adobe.com/cn/campaign/kb/sms-connector-protocol-and-settings.html)

更新了 Experience Manager 与 Adobe Campaign 集成的文档。[了解更多](../../reporting/using/creating-a-custom-profile-dimension.md)

全面重组了“设计内容”指南，特别凸显了可用于设计电子邮件内容的两个编辑器。[了解更多](../../designing/using/designing-content-in-adobe-campaign.md)

了解如何通过 Creative SDK 从现有电子邮件创建片段，使外部内容完全可编辑。[了解更多](../../designing/using/designing-from-scratch.md)

现在，此[章节](../../designing/using/using-existing-content.md#editing-existing-contents-with-the-email-designer)中提供了完全符合 Creative Designer 要求的 HTML 属性的列表。

添加了关于多语言模板默认语言的信息。[了解更多](../../channels/using/multilingual-messages-template.md)

更新了“用户和安全”指南，以明确从 18.7 版开始，新 Campaign Standard 实例和不包含地理单位的现有实例中，已经弃用了地理单位功能。[了解更多](../../rn/using/deprecated-features.md)

## 18.6 版 - 2018 年 6 月 {#release-18-6---june-2018}

**此版本中包含的新增功能**

更新了 API 文档，提供了关于 **History** API 的信息。添加了使用案例，介绍如何检索用于发送给用户档案之投放的镜像页面。[了解更多](../../api/using/interacting-with-marketing-history.md)

**随版本提供的其他文档更新**

更新并重组了“Triggers - Campaign 集成”文档。[了解更多](../../integrating/using/about-adobe-experience-cloud-triggers.md)

添加了关于如何创建自定义用户档案维度的分步使用案例。[了解更多](../../reporting/using/creating-a-custom-profile-dimension.md)

重组了“使用 Campaign 和 Audience Manager 或 People 核心服务”文档。[了解更多](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

更新了准备投放角色定义。[了解更多](../../administration/using/list-of-roles.md)

为“查询活动”章节添加了一个示例，介绍如何定向单击了投放中特定链接的用户档案。[了解更多](../../automating/using/query-samples.md#targeting-profiles-who-clicked-a-specific-link-)

在 API 文档中添加了关于&#x200B;**自定义过滤器**&#x200B;的章节。[了解更多](../../api/using/filtering.md)

## 18.5 版 - 2018 年 5 月 {#release-18-5---may-2018}

**此版本中包含的新增功能**

GDPR：核心服务集成 - [了解更多](../../start/using/privacy-management.md)

推送改进 - 详细的投放反馈- [了解更多](../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification)

投放日志扩展 - [了解更多](../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension)

使用自定义用户档案数据进行动态报告 - [了解更多](../../channels/using/creating-a-multilingual-push-notification.md)

**随版本提供的其他文档更新**

添加了 Analytics 中的一系列 Campaign 指标。[了解更多](../../integrating/using/campaign-dimensions-and-metrics-in-analytics.md)

添加了关于 Administration 菜单中 Licenses 选项的信息。[了解更多](../../administration/using/licenses.md)

添加了关于如何在推送通知中使用自定义字段的信息。[了解更多](../../channels/using/customizing-a-push-notification.md#add-custom-fields)

更新了投放最佳实践分步指南。[了解更多](../../sending/using/delivery-best-practices.md)

添加了关于跟踪日志类型的信息。[了解更多](../../sending/using/tracking-messages.md#tracking-logs)

更新了“查询活动”章节。添加了查询示例。[了解更多](../../automating/using/query.md#query-samples)

专门介绍阻止列表的部分已重命名为“了解选择加入和选择退出流程”。其中更新了关于如何管理特定渠道的选择加入、以及如何设置登陆页面以管理选择加入和选择退出的信息。[了解更多](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

了解使用 Adobe 托管 SFTP 服务器的最佳实践。[了解更多](../../administration/using/external-accounts.md#sftp-external-account)

更新了集成触发器时支持的 Analytics SKU 列表。[了解更多](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services)

合并了内容编辑器文档的部分页面，以便更全面地查看可用的各种操作。[了解更多](../../designing/using/designing-content-in-adobe-campaign.md)

## 18.3 版 - 2018 年 3 月 {#release-18-3---march-2018}

**此版本中包含的新功能**

欧盟通用数据保护条例 (GDPR) - [了解更多](../../start/using/privacy.md)

适用于电子邮件的 Creative Designer - [了解更多](../../designing/using/designing-content-in-adobe-campaign.md)

多语言推送投放 - [了解更多](../../channels/using/creating-a-multilingual-push-notification.md)

在事务型消息传递中使用自定义资源 - [了解更多](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)

**随版本提供的其他文档更新**

GDPR API 重组了各种功能，以便自动处理 GDPR 请求。[了解更多](../../api/using/creating-a-privacy-request.md)

添加了有关如何设置登陆页以使收件人能够列入拒绝列表的信息。[了解更多](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md)

重组了[配置事务型消息传递](../../channels/using/configuring-transactional-event.md)章节，并添加了一个[分步使用案例](../../channels/using/transactional-messaging-use-case.md)。

添加了一项技术说明，介绍如何生成用于推送通知的多语言 CSV 文件。[了解更多](https://helpx.adobe.com/cn/campaign/kb/acs-generate-csv-multilingual-push.html)。

添加了关于&#x200B;**更新直邮隔离和投放日志**&#x200B;导入模板的信息。[了解更多](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)

更新了技术工作流列表。[了解更多](../../administration/using/technical-workflows.md)

更新了调度程序活动章节。[了解更多](../../automating/using/scheduler.md)

更新了关于 Campaign 和 Adobe 解决方案集成的一系列帮助资料。[了解更多](../../integrating/using/get-started-campaign-integrations.md)。

更新了 Campaign Standard 产品内上下文帮助。

## 18.2 版 - 2018 年 2 月 {#release-18-2---february-2018}

**此版本中包含的新增功能**

订阅 - 让一系列用户档案订阅或退订多项服务 - [了解更多](../../automating/using/subscription-services.md)

扩充活动 - 根据过往的过渡扩充数据 - [了解更多](../../automating/using/enrichment.md)

**随版本提供的其他文档更新**

Campaign 和 Adobe 解决方案集成的大多数 URL 都已更改！请检查您的书签！[了解更多](../../integrating/using/get-started-campaign-integrations.md)

datamodel v1 现在可搭配 SQL 结构用于内置资源 - [了解更多](../../developing/using/datamodel-introduction.md)

添加了关于如何在投放中准备消息的信息[了解更多](../../sending/using/preparing-the-send.md)

将发行说明重组到了几个页面中，以便更全面地查看所有版本。

更新了 **[!UICONTROL Working with typologies]** 章节，改善了可见性。[了解更多](../../sending/using/about-typology-rules.md)

现在提供了一个新选项，利用该选项可更方便地定义 **[!UICONTROL Query]** 中的诸多附加数据。[了解更多](../../automating/using/query-samples.md)

更新了用户档案导入示例，提供了一些关于如何让用户档案准备接收直邮的提示。[了解更多](../../automating/using/about-data-import-and-export.md)

工作流中提供了新的活动：**[!UICONTROL Enrichment]** 活动。[了解更多](../../automating/using/enrichment.md)

更新了 **[!UICONTROL Subscription Services]** 活动以支持更多使用案例，包括使用单个文件将订阅更新为多项服务。[了解更多](../../automating/using/subscription-services.md)

添加了关于如何准备投放的分步使用案例。[了解更多](../../sending/using/preparing-the-send.md)

删除了包含授权列表的章节。[了解更多](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf) (PDF)。

添加了关于如何使用短信自动回复的分步使用案例。[了解更多](../../channels/using/managing-incoming-sms.md#managing-stop-sms)

添加了关于如何在定期工作流中根据用户时区发送投放的信息。[了解更多](../../automating/using/recurring-push-notifications.md)

通过分步使用案例，重组了 **[!UICONTROL Customizing a push notification]** 章节。[了解更多](../../channels/using/customizing-a-push-notification.md)

专门介绍拒绝列表管理的新部分。[了解更多](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

更新了有关投放失败和隔离的信息。[了解更多](../../sending/using/monitoring-a-delivery.md)

添加了关于[目标映射](../../administration/using/target-mappings-in-campaign.md)和[定向维度和资源](../../automating/using/query.md#targeting-dimensions-and-resources)的新章节。

## 18.1 版 - 2018 年 1 月 {#release-18-1---january-2018}

**此版本中包含的新增功能**

疲劳管理报告 - [了解更多](../../sending/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report)

报告共享 - [了解更多](../../reporting/using/reporting-interface.md#share-tab)

推送改进 - 通过[此处](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification)和[此处](../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios)了解更多

时区优化投放 - [了解更多](../../automating/using/scheduler.md)

API 信号活动触发 - [了解更多](../../api/using/triggering-a-signal-activity.md)

**随版本提供的其他文档更新**

更新了“服务创建”章节。[了解更多](../../audiences/using/creating-a-service.md)

增加了使用案例，以更好地了解安全组和单位。[了解更多](../../administration/using/organizational-units.md)

改进了动态报告中维度、指标和区段的定义和计算式。[了解更多](../../reporting/using/list-of-components-.md)

添加了关于使用工作流检索传入短信消息的信息。[了解更多](../../administration/using/configuring-sms-channel.md)

添加了关于传输文件活动历史化设置的信息。[了解更多](../../automating/using/transfer-file.md)

更新了使用 Audience Manager 或 People 核心服务集成的说明。[了解更多](../../integrating/using/integration-with-audience-manager-or-people-core-service.md)

## 17.10 版 - 2017 年 10 月 {#release-17-10---october-2017}

**此版本中包含的新增功能**

疲劳管理 - [了解更多](../../sending/using/fatigue-rules.md)

内容创建：从 URL 导入 - [了解更多](../../designing/using/using-existing-content.md#importing-content-from-a-url)

**随版本提供的其他文档更新**

更新了 A/B 测试示例。[了解更多](../../channels/using/designing-an-a-b-test-email.md)

提供了关于当移动应用程序发送“Collect PII”数据时如何创建或更新用户档案数据的新技术说明。[了解更多](https://helpx.adobe.com/cn/campaign/kb/acs-updating-profile-based-on-subscription.html)

新增了有关新导出跟踪功能的章节。[了解更多](../../administration/using/auditing-export-logs.md)

新增了关于内置资源包导出的精确说明。[了解更多](../../automating/using/managing-packages.md)

更新了外部帐户定义和示例。[了解更多](../../administration/using/external-accounts.md)

更新了大量屏幕截图，以反映查询编辑器类别中的变化。

移动并重组了[投放警报](../../sending/using/receiving-alerts-when-failures-happen.md)章节。

对“自定义资源”章节进行了阐明，更详细地介绍了[定义过滤器](../../developing/using/configuring-filter-definition.md)的过程。

更新并阐明了如何将 Adobe Marketing Cloud Mobile SDK 与移动应用程序集成以接收 Adobe Campaign Standard 推送通知的[技术说明](https://helpx.adobe.com/cn/campaign/kb/integrate-mobile-sdk.html)。

添加了一个技术说明，介绍在移动应用程序中接收的有效载荷的结构。[了解更多。](../../administration/using/push-payload.md)

更新了推送渠道配置[章节](https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdkv4.html)，以介绍在 Adobe Mobile Services 界面中定义回传时要添加的、关于操作系统版本的新有效载荷数据。

更新了“短信”文档，为[短信自动回复](../../channels/using/managing-incoming-sms.md#managing-stop-sms)章节添加了一些深入说明。

添加了关于通过 API 进行工作流管理的专述章节。[了解更多](../../api/using/controlling-a-workflow.md)

添加了关于将主密钥和业务 ID 用作 API 密钥的专述章节。[了解更多](../../api/using/get-started-apis.md)

添加了关于 API 中简单筛选和多条件筛选的信息。[了解更多](../../api/using/filtering.md)

## 17.9 版 - 2017 年 9 月 {#release-17-9---september-2017}

**此版本中包含的新增功能**

电子邮件模板库 - [了解更多](../../designing/using/using-reusable-content.md#content-templates)

使用用户档案数据进行动态报告 - [了解更多](../../reporting/using/about-dynamic-reports.md)

批量订阅增强功能 - [了解更多](../../automating/using/subscription-services.md)

**随版本提供的其他文档更新**

详细列出了动态报告中可用的每个组件以及公式中的某些变化。[了解更多](../../reporting/using/list-of-components-.md)

详细列出了与 Adobe Analytics 共享的 KPI 列表。[了解更多](../../integrating/using/campaign-dimensions-and-metrics-in-analytics.md)

新增了“动态报告”视频。

添加了 S3 帐户建议。[了解更多](../../administration/using/external-accounts.md#amazon-s3-account-recommendations)

更新了关于不同类型用户的章节。[了解更多](../../administration/using/users-management.md)

更新了关于图像源个性化的章节。[了解更多](../../designing/using/personalization.md#personalizing-an-image-source)

添加了关于活动用户档案报告的文档。[了解更多](../../audiences/using/active-profiles.md)

更新了[投放警报](../../sending/using/receiving-alerts-when-failures-happen.md#delivery-alerting-reasons)文档，添加了疑难解答章节，提供了关于在收到警报时可以采取哪些操作的一些提示。

提供了新的快速入门指南：其中介绍了一些 Adobe Campaign 应用的最佳实践，从创建和定向到发送和监控。[了解更多](../../sending/using/delivery-best-practices.md)

更新了“跟进消息”文档，提供了经过改进的使用案例。[了解更多](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)

添加了关于 ACS ID 的文档。[了解更多](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)

添加了新加密和哈希函数以及相关示例。[了解更多](../../automating/using/list-of-functions.md)

更新了关于传输文件工作流活动的章节。[了解更多](../../automating/using/transfer-file.md)

添加了关于电子邮件投放工作流活动中“发送邮件前请求确认”选项的信息。[了解更多](../../automating/using/email-delivery.md)

## 17.7 版 - 2017 年 7 月 {#release-17-7---july-2017}

**此版本中包含的新增功能**

多语言投放（电子邮件和短信）- [了解更多](../../channels/using/creating-a-multilingual-email.md)

Adobe Campaign 通知 - [了解更多](../../administration/using/sending-internal-notifications.md)

投放警报 - [了解更多](../../sending/using/receiving-alerts-when-failures-happen.md)

数据源中加密的已声明 ID - [了解更多](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

从 Campaign 到 Analytics 的 KPI 共享 - [了解更多](../../integrating/using/about-campaign-analytics-integration.md)

直邮渠道 - 退回发件人，[了解更多](../../channels/using/return-to-sender.md)

**随版本提供的其他文档更新**

将快速入门指南和操作方法视频重组到了专述章节。

更新了电子邮件渲染文档。[了解更多](../../sending/using/email-rendering.md)

更新了报告指标计算表格。[了解更多](../../reporting/using/indicator-calculation.md)

更新了报告文档，提供了四个新指标。[了解更多](../../reporting/using/list-of-components-.md)

添加了关于为用户档案生成唯一 ID 的文档。[了解更多](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)

新增了关于两次选择加入机制的分步过程文档。[了解更多](../../channels/using/setting-up-a-double-opt-in-process.md)

更新了“角色列表”章节。[了解更多](../../administration/using/list-of-roles.md)

## 17.5 版 - 2017 年 5 月 {#release-17-5---may-2017}

**此版本中包含的新增功能**

直邮 - [了解更多](../../channels/using/about-direct-mail.md)

电子邮件密送 - [了解更多](../../sending/using/archiving.md)

**随版本提供的其他文档更新**

重组了“投放”指南，并将其更名为“渠道”。[了解更多](../../channels/using/get-started-communication-channels.md)

更新了多张屏幕截图，以反映界面的更改。

提供了新的技术说明：“将 Adobe Mobile SDK 与您的移动应用程序集成”。[了解更多](https://helpx.adobe.com/cn/campaign/kb/integrate-mobile-sdk.html)

添加了对于使用 Adobe Campaign 配置 People 核心服务或 Audience Manager 集成的说明。[阅读更多](../../integrating/using/integration-with-audience-manager-or-people-core-service.md)

修改了授权表，使某些角色的职能更加清晰。[了解更多](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf)

更新了可直接从 Adobe Campaign 访问的上下文帮助链接。

## 17.4 版 - 2017 年 4 月 {#release-17-4---april-2017}

**此版本中包含的新增功能**

利用 Creative SDK 增强图像编辑功能 - [了解更多](../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk)

事务型推送通知 - [了解更多](../../channels/using/transactional-push-notifications.md)

定期推送通知 - [了解更多](../../automating/using/push-notification-delivery.md)

Amazon Simple Storage Service (S3) 连接器 - [了解更多](../../administration/using/external-accounts.md)

Dreamweaver 集成上线 - [了解更多](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=zh-Hans)

**随版本提供的其他文档更新**

添加了关于不同类型 Adobe Campaign 用户的章节。[了解更多](../../administration/using/users-management.md)

重新组织并扩展了工作流指南。轻松了解如何[构建](../../automating/using/building-a-workflow.md)和[执行](../../automating/using/about-workflow-execution.md)工作流，如何[设定目标](../../automating/using/about-targeting-activities.md)和[管理](../../automating/using/about-targeting-activities.md#enriching-data)数据，如何[导入和导出](../../automating/using/about-data-import-and-export.md)数据，以及如何使用工作流数据更新数据库或发送投放。

现在为动态报告提供了报告指标计算功能，其中包括完整说明和计算公式。[了解更多](../../reporting/using/indicator-calculation.md)

新增了关于在 Adobe Campaign 中配置 Adobe Mobile Services 以使用推送通知和兴趣点数据的专述章节。[了解更多](https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdkv4.html)

更新了移动应用程序配置和实施章节，其中更加详细地说明了设置和发送推送通知的步骤。[了解更多](https://helpx.adobe.com/cn/campaign/kb/configuring-app-sdkv4.html)

更新了关于如何在 Campaign 中处理图像的章节。[了解更多](../../designing/using/images.md#setting-up-image-properties)

更新了与 Adobe Analytics for Mobile (Point of Interest) 的集成，包括配置步骤和使用案例。[了解更多](../../integrating/using/about-campaign-points-of-interest-data-integration.md)

## 17.2 版 - 2017 年 3 月 {#release-17-2---march-2017}

**此版本中包含的新增功能**

动态报告 - [了解更多](../../reporting/using/about-dynamic-reports.md)

Dreamweaver 集成（实验室）- [了解更多](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=zh-Hans)

手动发送时间优化 - [了解更多](../../sending/using/optimizing-the-sending-time.md)

推送通知：改进 - [了解更多](../../channels/using/about-push-notifications.md)

工作流：新信号活动 - [了解更多](../../automating/using/external-signal.md)

工作流：新读取受众活动 - [了解更多](../../automating/using/read-audience.md)

兴趣点数据 - [了解更多](../../integrating/using/about-campaign-points-of-interest-data-integration.md)

REST API 中的已链接资源 - [了解更多](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension)

**随版本提供的其他文档更新**

Triggers 集成：添加了两个使用案例。[了解更多](../../integrating/using/abandonment-triggers-use-cases.md)

我们重新设计了开发人员 API 文档，使用了新的信息和代码片段以改善用户体验。[了解更多](../../api/using/get-started-apis.md)

查看新的[读取受众](../../automating/using/read-audience.md)和[外部信号](../../automating/using/external-signal.md)工作流活动的示例。

## 17.1 版 - 2017 年 1 月 {#release-17-1---january-2017}

**此版本中包含的新增功能**

导出日志用于外部报告 - [了解更多](../../automating/using/exporting-logs.md)

事务型消息传递 API - [了解更多](../../api/using/get-started-apis.md)

事务性消息的营销功能 - [了解更多](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities)

**随版本提供的其他文档更新**

增量查询工作流活动：新增量模式 - [了解更多](../../automating/using/incremental-query.md)

调度程序工作流活动更新 - [了解更多](../../automating/using/scheduler.md)

URL 更改：资源核心服务 - [了解更多](../../integrating/using/working-with-campaign-and-assets-core-service.md)

URL 更改：People 核心服务 - [了解更多](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

重组了用户档案和受众指南。[了解更多](../../audiences/using/get-started-profiles-and-audiences.md)
