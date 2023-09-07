---
title: Adobe Campaign Standard 隐私和同意
description: 本节概述 Adobe Campaign Standard 隐私、个人数据和同意管理，以及可用于处理这些事项的工具。
page-status-flag: never-activated
uuid: ed9e631c-5ad1-49f1-be1e-b710bc64dc91
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 5227ca05-3856-4e54-aec6-14444d6534e3
feature: Privacy
role: User
level: Intermediate
exl-id: 0fc71c2f-f294-43f7-825c-73ab4d43fcf7
source-git-commit: 9533654ac4476b359da8cf00f9ef2015d9f8ccdf
workflow-type: tm+mt
source-wordcount: '1418'
ht-degree: 96%

---

# 隐私和同意{#privacy-and-consent}

## 一般建议 {#general-recommendations}

Adobe Campaign 是一款用于收集和处理超大量数据（包括个人信息和敏感数据）的强大工具。为此需要谨慎管理隐私。

* 始终以负责任和道德的方式使用个人信息。

* 避免发送未经请求的电子邮件、推送通知和短信（“垃圾邮件”）。为了实现客户终生价值并提高客户忠诚度，Adobe 坚信许可营销原则，并因此严格禁止使用 Adobe Campaign 发送未经请求的消息。

### 隐私法规 {#privacy-regulations}

要正确处理隐私和管理个人数据，请在适用于您运营地区的法规范围内开展工作。这些法规包括：
* [GDPR](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en)（欧洲通用数据保护条例）
* [DPA](https://www.gov.uk/data-protection)（英国的 GDPR 实施）
* [欧洲隐私和电子通信指令](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:02002L0058-20091219)
* [CAN-SPAM Act](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)（规定商业电子邮件规则和要求的美国法律）
* [CCPA](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4.&amp;chapter=&amp;article=)（加州消费者隐私法案）
* [PDPA](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/)（泰国个人数据保护法案）

>[!NOTE]
>
>有关 GDPR、CCPA 和 PDPA 如何应用于 Adobe Campaign 的更多信息，请参阅[此页面](../../start/using/privacy-management.md#privacy-management-regulations)。

### Adobe Experience Cloud 隐私 {#experience-cloud-privacy}

Adobe Campaign 是 Adobe Experience Cloud 解决方案的一部分。Campaign 中处理隐私的方式遵循如下 Adobe Experience Cloud 一般原则：

* **使用 Adobe Experience Cloud 时收集哪些信息**

  作为使用 Adobe Experience Cloud 解决方案的公司，您可以选择要收集哪些信息并将其发送到您的 Adobe Experience Cloud 帐户。可能收集的信息类型示例包括 Web 浏览活动、IP 地址、移动设备的位置信息、活动成功率、购买或放入购物车的商品等。

  >[!NOTE]
  >
  >至于所有 Adobe 产品，Campaign 会收集有关应用程序和网站用户的信息。有关此内容的更多信息，请参阅 [Adobe 隐私策略](https://www.adobe.com/cn/privacy/policy.html)。

* **如何使用 Adobe Experience Cloud 收集信息**

   * Adobe Experience Cloud 解决方案使用 cookie 及网络信标（也称为标记或像素）之类的类似技术使您能够收集信息。有关 Adobe Campaign 的 cookie 和跟踪功能的更多信息，请参阅[此部分](#tracking-capabilities)。
   * 您还可以在移动应用程序中使用 Adobe Experience Cloud 技术。有关使用 Campaign 发送移动投放的更多信息，请参阅[此页面](../../channels/using/mobile-guide.md)。

* **用户对您使用 Adobe Experience Cloud 的隐私选择**

  Adobe 要求您提供客户隐私政策，其中描述：

   * 关于 Adobe Experience Cloud 的隐私条例
   * 用户如何可为收集或使用与 Adobe Experience Cloud 有关的信息设置首选项

  >[!NOTE]
  >
  >至于所有 Adobe 产品，Campaign 用户可以选择不共享通过应用程序和网站收集到的关于它们的信息。有关此内容的更多信息，请参阅 [Adobe Experience Cloud 使用信息常见问题解答](https://www.adobe.com/cn/privacy/experience-cloud-usage-info-faq.html)。

有关A dobe Experience Cloud 隐私的更多详细信息，请参阅[此页面](https://www.adobe.com/cn/privacy/marketing-cloud.html)。

## 个人数据和角色 {#personal-data}

在管理隐私时，必须明确应当谨慎处理哪些数据以及由谁处理。
* **个人数据**&#x200B;是指可以直接或间接识别生命个体的信息。
* **敏感个人数据**&#x200B;是与个人的种族、政治观点、宗教信仰、犯罪背景、遗传信息、健康数据、性取向、生物识别信息以及贸易同盟会员资格相关的信息。

[主要法规](#privacy-regulations)是指管理数据的不同实体，如下所示：
* **数据控制者**&#x200B;是确定收集、使用和共享个人数据的方式和目的权威。
* **数据处理者**&#x200B;是按照数据控制者的指示收集、使用或共享个人数据的任何个人或一方。
* **数据主体**&#x200B;是指对其个人数据进行收集、使用或共享，并可通过参考该个人数据来直接或间接进行识别的任何生命个体。

因此，作为收集和共享个人数据的公司，您是数据控制者，您的客户是数据主体，Adobe Campaign 在按照您的指示处理其个人数据时充当数据处理者。请注意，作为数据控制者，您责任处理与数据主体的关系，例如管理[隐私请求](#privacy-requests)。

将Campaign与其他Experience Cloud解决方案集成时，如果受众可以从一个系统转移到另一个系统， [Adobe Analytics](../../integrating/using/about-campaign-analytics-integration.md)， [Audience Manager或人员核心服务](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)，或其他解决方案，例如 [Microsoft Dynamics 365](../../integrating/using/d365-acs-get-started.md)，您需要格外注意个人数据保护。

## 数据采集 {#data-acquisition}

通过 Adobe Campaign，您可以收集数据，包括个人信息和敏感信息。因此，获得并监控收件人的同意至关重要。

* 始终让收件人同意接收通信。为此，请尽快保持遵守选择退出请求并通过双重选择加入流程来验证同意。有关此内容的更多信息，请参阅[在 Campaign 中管理选择加入和选择退出](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md)和[设置双重选择加入流程](../../channels/using/setting-up-a-double-opt-in-process.md)。
* 请勿导入欺诈性列表，并使用陷阱检查您的客户文件是否未被欺骗性使用。有关此内容的更多信息，请参阅[使用陷阱](../../sending/using/using-traps.md)。
* 通过同意和权限管理，您可以跟踪收件人的偏好，以及管理组织内谁可以访问哪些数据。有关更多信息，请参阅[此章节](#consent)。
* 促进和管理收件人的隐私请求。有关更多信息，请参阅[此章节](#privacy-requests)。

## 隐私管理 {#privacy-management}

隐私管理是指可帮助您遵守隐私法规（GDPR 和 CCPA 等）的所有流程和工具。在[此页面](../../start/using/privacy-management.md#privacy-management-regulations)上获取隐私管理概念的概述。

Adobe Campaign 为您提供专门用于隐私管理的各种功能集：
* 同意管理、数据保留和用户角色。请参阅[此章节](#consent)。
* 隐私请求（访问权和被遗忘权）。请参阅[此章节](#privacy-requests)。
* 选择退出个人信息销售（特定于 CCPA）请参阅[此章节](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa)。

[此部分](#personal-data)中介绍 Campaign 中的主要隐私功能以及所涉及角色的示例。


### 同意、保留和角色 {#consent}

Adobe Campaign 最初提供对隐私至关重要的重要功能：

* **同意管理**：通过订阅管理流程，您可以管理收件人的偏好并跟踪哪些收件人已选择加入哪种类型的订阅。有关此内容的详细信息，请参阅[订阅](../../audiences/using/about-subscriptions.md)和[登陆页](../../channels/using/getting-started-with-landing-pages.md)。
* **数据保留**：所有内置标准日志表都具有预设的保留期，通常将其数据存储限制为 6 个月或更短时间。可以使用工作流设置其他保留期。有关此内容更多信息，请联系 Adobe 顾问或技术管理员。
* **权限管理**：Adobe Campaign 使您能够通过不同的预建或自定义角色来管理分配给各种 Campaign 操作员的权限。这允许您管理公司内可以访问、修改或导出不同类型数据的人员。有关此内容的更多信息，请参阅[关于访问管理](../../administration/using/about-access-management.md)。

有关这些功能以及如何在 Adobe Campaign 中管理这些功能的更多信息，请参阅[此页面](../../start/using/privacy-management.md#consent-retention-roles)。

### 隐私请求 {#privacy-requests}

Adobe Campaign 提供其他功能来促使您作为数据控制者为特定隐私请求做好准备：

* **访问权**&#x200B;是数据主体从数据控制者处就与其有关的个人数据是否正在进行处理、处理位置和处理原因获得确认的权限。

* **被遗忘权**（删除请求）允许数据主体通过数据控制者擦除其个人数据。

>[!NOTE]
>
>这套工具旨在帮助您遵守 GDPR、CCPA 和 PDPA 隐私规定。有关这些不同法规的更多信息，请参阅[此页面](../../start/using/privacy-management.md#privacy-management-regulations)。

**访问**&#x200B;和&#x200B;**删除**&#x200B;请求将显示在[此页面](../../start/using/privacy-management.md#right-access-forgotten)上。[此页面](../../start/using/privacy-requests.md#about-privacy-requests)上详细描述了创建这些请求的实施步骤。[此处](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/privacy-overview.html?lang=zh-Hans)还提供教程。

## 跟踪功能 {#tracking-capabilities}

凭借其跟踪功能，Adobe Campaign 使您能够使用会话 cookie 和永久 cookie 跟踪投放收件人的行为。有关跟踪的更多信息，请参阅[此页面](../../sending/using/tracking-messages.md)。

>[!NOTE]
>
>《通用数据保护条例》(GDPR) 等法规规定，公司在安装任何 cookie 之前必须获得网站用户的同意。您必须通过授权请求告知用户您的站点配备 Web 跟踪工具。

您还可以在消息中添加[跟踪链接](../../designing/using/links.md#about-tracked-urls)，以便在[跟踪指示器](../../reporting/using/tracking-indicators.md)内置报告中衡量投放和收件人行为的影响 ，或者创建您自己的[专用报告](../../reporting/using/about-dynamic-reports.md)。
