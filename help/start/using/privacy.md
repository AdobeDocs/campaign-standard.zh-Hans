---
title: Adobe Campaign标准中的隐私和同意
description: 本节概述了Adobe Campaign标准中的隐私、个人数据和同意管理，以及可用的工具。
page-status-flag: never-activated
uuid: ed9e631c-5ad1-49f1-be1e-b710bc64dc91
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 5227ca05-3856-4e54-aec6-14444d6534e3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 26760a118f87676afe3d359c8db3513c1a190d35
workflow-type: tm+mt
source-wordcount: '1479'
ht-degree: 0%

---


# 隐私和同意{#privacy-and-consent}

## 一般性建议 {#general-recommendations}

Adobe Campaign是收集和处理大量数据（包括个人信息和敏感数据）的强大工具。 这就是为什么隐私需要谨慎管理的原因。

* 始终以负责任和道德的方式使用个人信息。

* 避免发送未经请求的电子邮件、推送通知和SMS消息（“垃圾邮件”）。 Adobe坚信许可营销原则能够培养客户终身价值和忠诚度，因此严格禁止在发送未经请求的消息时使用Adobe Campaign。

### 隐私法规 {#privacy-regulations}

要正确处理隐私和管理个人数据，请在适用于您所在地区的法规范围内开展工作。 这些规定包括：
* [GDPR](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en) （欧洲一般数据保护规定）
* [DPA](https://www.gov.uk/data-protection) （英国实施GDPR）
* [欧洲隐私和电子通信指令](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:02002L0058-20091219)
* [CAN-SPAM Act](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business) （美国法律为商业电子邮件制定规则和要求）
* [CCPA](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.标题(&amp;T)=1.81.5。&amp;part=4。&amp;chapter=&amp;article=) (California Consumer Privacy Act)
* [PDPA](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/) （泰国个人数据保护法）

>[!NOTE]
>
>有关GDPR、CCPA和PDPA如何应用于Adobe Campaign的更多信息，请参 [阅本页](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html#whatisgdpr)。

### Adobe Experience Cloud隐私 {#experience-cloud-privacy}

Adobe Campaign是Adobe Experience Cloud解决方案的一部分。 在活动中处理隐私的方式遵循Adobe Experience Cloud的一般原则，如：

* **使用Adobe Experience Cloud时收集哪些信息**

   作为使用Adobe Experience Cloud解决方案的公司，您可以选择要收集哪些信息并将其发送到您的Adobe Experience Cloud帐户。 可能收集的信息类型示例包括Web浏览活动、IP地址、移动设备的位置信息、活动成功率、购买或放入购物车的物品等。

   >[!NOTE]
   >
   >对于所有Adobe产品，活动会收集有关应用程序和网站用户的信息。 有关此方面的详细信息，请参 [阅Adobe隐私政策](https://www.adobe.com/privacy/policy.html)。

* **如何使用Adobe Experience Cloud收集信息**

   * Adobe Experience Cloud解决方案使用cookies及类似技术(如网络信标（也称为标签或像素）)来收集信息。 有关使用Adobe Campaign的cookie和跟踪功能的更多信息，请参 [阅此部分](#tracking-capabilities)。
   * 您还可以在您的移动应用程序中使用Adobe Experience Cloud技术。 有关使用活动发送移动投放的详细信息，请 [参阅此页](https://helpx.adobe.com/campaign/kb/acs-mobile.html)。

* **您用户对您使用Adobe Experience Cloud的隐私权选择**

   Adobe要求您提供客户隐私政策，其中描述：

   * 您与Adobe Experience Cloud相关的隐私权惯例
   * 用户如何为收集或使用与Adobe Experience Cloud相关的信息设置首选项
   >[!NOTE]
   >
   >至于所有Adobe产品，活动用户可以选择不共享通过应用程序和网站收集到的有关它们的信息。 有关此方面的更多信息，请参 [阅Adobe Experience Cloud使用信息常见问题解答](https://www.adobe.com/privacy/experience-cloud-usage-info-faq.html)。

有关Adobe Experience Cloud隐私的更多详细信息，请参 [阅此页](https://www.adobe.com/privacy/marketing-cloud.html)。

## 个人数据和角色 {#personal-data}

在管理隐私时，必须明确应当谨慎处理哪些数据以及由谁处理哪些数据。
* **个人数据** ，是指可以直接或间接识别活人的信息。
* **敏感个人数据** 是与个人的种族、政治视图、宗教信仰、犯罪背景、遗传信息、健康数据、性偏好、生物识别信息以及贸易合并会员资格相关的信息。

主 [要法规](#privacy-regulations) ，是指管理数据的不同实体，具体如下：
* 数 **据控制** 器是决定收集、使用和共享个人数据的手段和目的的权威。
* 数 **据处理者** ，是指按照数据管理者的指示收集、使用或共享个人数据的任何个人或一方。
* 数 **据主体** ，是指收集、使用或共享个人数据，并可以直接或间接地参照该个人数据识别的任何活人。

因此，作为收集和共享个人数据的公司，您是数据管理者，您的客户是数据主体，Adobe Campaign在按照您的指示处理其个人数据时充当数据处理者。 请注意，您作为数据管理者有责任处理与数据主体的关系，例如管理隐私 [请求](#privacy-requests)。

当将活动与其他Experience Cloud解决方案集成时，您需要支付额外的个人护理费以保护数据 [，例如，](../../audiences/using/aep-about-audience-destinations-service.md)Adobe Analytics [、](../../integrating/using/about-campaign-analytics-integration.md)受众经理或People core service [，或与其他解决方案(如](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)[](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)Microsoft Dynamics 365)进行集成。

## 数据采集 {#data-acquisition}

Adobe Campaign使您能够收集数据，包括个人和敏感信息。 因此，您必须获得并监控收件人的同意。

* 始终让收件人同意接收通信。 为此，请继续尽快遵守退出请求并通过多次选择加入流程验证同意。 有关此内容的详 [细信息，请参阅管理活动中的加入和退出](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md)[和设置多次选择加入流程](../../channels/using/setting-up-a-double-opt-in-process.md)。
* 请勿导入欺诈性列表并使用陷阱检查您的客户文件是否未被欺骗性使用。 有关此方面的详细信息，请参 [阅使用陷印](../../sending/using/using-traps.md)。
* 通过同意和权限管理，您可以跟踪收件人的偏好，并管理组织内谁可以访问哪些数据。 For more on this, see [this section](#consent).
* 方便和管理收件人的隐私请求。 For more on this, see [this section](#privacy-requests).

## 隐私管理 {#privacy-management}

隐私管理是指可帮助您遵守隐私法规（GDPR、CCPA等）的所有流程和工具。 获取本页隐私管理概 [述](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html)。

Adobe Campaign为您提供了专门用于隐私管理的各种功能：
* 同意管理、数据保留和用户角色。 请参 [阅此部分](#consent)。
* 隐私请求（访问权和被遗忘权）。 请参 [阅此部分](#privacy-requests)。
* 选择退出销售个人信息(CCPA-specific)。 请参 [阅此部分](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa)。

本节介绍活动中的主要隐私功能以及相关角色 [的示例](https://helpx.adobe.com/campaign/kb/campaign-privacy-more.html#gdprpersonasandflow)。


### 同意、保留和角色 {#consent}

Adobe Campaign优惠最初包含对隐私至关重要的重要功能：

* **同意管理**: 通过订阅管理流程，您可以管理收件人偏好并跟踪哪些收件人已选择了哪类订阅。 有关此内容的详细信息，请参 [阅订阅](../../audiences/using/about-subscriptions.md) 和 [登陆页](../../channels/using/getting-started-with-landing-pages.md)。
* **数据保留**: 所有内置的标准日志表都具有预设的保留期，通常将其数据存储限制在6个月或更短。 可以通过工作流设置额外的保留期。 要了解更多信息，请联系Adobe顾问或技术管理员。
* **权限管理**: Adobe Campaign允许您通过不同的预建或自定义角色管理分配给各种活动操作符的权限。 这允许您管理公司内可以访问、修改或导出不同类型数据的人员。 有关此方面的详细信息，请参 [阅关于访问管理](../../administration/using/about-access-management.md)。

有关这些功能以及如何在Adobe Campaign中管理这些功能的更多信息，请参 [阅本页](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html#consent)。

### 隐私请求 {#privacy-requests}

Adobe Campaign提供了其他功能，帮助您作为数据管理者，为特定隐私请求做好准备：

* 访问 **权是** ，数据主体有权从数据管理者那里获得关于是否正在处理与其有关的个人数据的确认，其地点和原因。

* 被 **遗忘权** （删除请求）赋予数据主体让数据管理者擦除其个人数据的权利。

>[!NOTE]
>
>这套工具可帮助您遵守GDPR、CCPA和PDPA的隐私权。 有关这些不同法规的更多信息，请 [参阅本页](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html#whatisgdpr)。

<!--* **GDPR** (General Data Protection Regulation) is the European Union’s (EU) privacy law that harmonizes and modernizes data protection requirements. GDPR applies to Adobe Campaign customers who hold data for Data Subjects residing in the EU.

* **CCPA** (California Consumer Privacy Act) provides California residents new rights in regards to their personal information and imposes data protection responsibilities on certain entities whom conduct business in California.

* **Thailand's PDPA** (Personal Data Protection Act) is the new privacy law that harmonizes and modernizes data protection requirements for Thailand. This regulation applies to Adobe Campaign customers who hold data for Data Subjects residing in this country.-->

访问 **和** 删除请 **求将显示在** 此页上 [](https://helpx.adobe.com/campaign/kb/acs-privacy.html#righttoaccess)。 创建这些请求的实施步骤详见 [本页](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)。 此处还提供教 [程](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/privacy/privacy-overview.html)。

## 跟踪功能 {#tracking-capabilities}

凭借其跟踪功能，Adobe Campaign使您能够使用会话cookie和永久cookie跟踪投放收件人的行为。 有关跟踪的详细信息，请 [参阅此页](../../sending/using/tracking-messages.md)。

>[!NOTE]
>
>《一般数据保护规定》(GDPR)等法规规定，公司在安装任何Cookie之前必须获得网站用户的同意。 您必须通过授权请求告知用户您的站点已配备Web跟踪工具。

您还可以在邮 [件中添加](../../designing/using/links.md#about-tracked-urls) “跟踪链接”，以便在“跟踪指示器”内置报表中衡量投放和 [收件人行为的影响](../../reporting/using/tracking-indicators.md) ，或创建您自己的专 [用报表](../../reporting/using/about-dynamic-reports.md)。
