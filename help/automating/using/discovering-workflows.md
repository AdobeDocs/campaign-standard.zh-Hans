---
title: 了解工作流
description: Adobe Campaign提供了一个全面的图形环境，使您能够设计和自动化流程。
page-status-flag: 从未激活
uuid: 7c1e8cea-90d0-491f-ab8f-6cd69f8a6c3b
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: about-workflows-and-data-management
discoiquuid: 40503917-7a53-4d99-96a4-57aa9e98ec87
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 了解工作流{#discovering-workflows}

Adobe Campaign提供了一个全面 [的图形环境](../../automating/using/workflow-interface.md) ，允许您设计 [包括细分、营销活动执行](../../automating/using/workflow-operating-principles.md) 、文件处理、批准等复杂流程。 本节将介绍原则和最 [佳实践](../../automating/using/building-a-workflow.md)。

例如，您可以使用工作流从服务器下载文件，对其解压缩，然后将其记录导入Adobe Campaign数据库。

通过为用户分配任务或让他们批准已执行的任务，工作流也可能涉及到用户。 这意味着您可以向一个或多个用户分配任务，以便处理内容或指定目标，并在发送消息之前批准校样。

工作流可用于不 **同的上下文**，例如：

* 定位以管理受众或发送消息。 有关详细信息，请参阅渠 [道活动](../../automating/using/about-channel-activities.md) 和定 [位活动](../../automating/using/about-targeting-activities.md)。
* 数据管理(ETL)以操作数据。 有关详细信息，请参阅数 [据管理活动](../../automating/using/about-data-management-activities.md)。
* 将数据导入Campaign数据库。 有关详细信息，请参阅导 [入和导出数据](../../automating/using/about-data-import-and-export.md)。
* 诸如数据库清理、恢复跟踪信息等技术流程。 在本节中进一步了解技术工 [作流程](../../administration/using/technical-workflows.md)。

工作流也可从Adobe Campaign Standard API访问。 有关详细信息，请参阅专 [用文档](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#managing-workflows)。

**相关主题：**

* [工作流操作原则](../../automating/using/workflow-operating-principles.md)
* [关于数据导入和导出](../../automating/using/about-data-import-and-export.md)
* [用例：创建每周一次的电子邮件发送](../../automating/using/workflow-weekly-offer.md)
* [用例：创建按位置分段的交付](../../automating/using/workflow-segmentation-location.md)
* [用例：使用补充创建交付](../../automating/using/workflow-created-query-with-complement.md)
* [用例：重定向工作流向非打开者发送新分发](../../automating/using/workflow-cross-channel-retargeting.md)
