---
solution: Campaign Standard
product: campaign
title: Microsoft Dynamics 365集成护栏
description: 带Campaign Standard集成护栏的Microsoft Dynamics 365
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---


# 集成护栏和边界

## 集成护栏

在计划使用这一集成时，应考虑以下护栏。 如果您认为超过这些护栏，请咨询Adobe技术代表。

* 您需要许可正确的活动包以支持集成生成的ACS引擎调用量。 超过授权的引擎调用量可能导致活动性能降低。

   使用以下内容帮助评估集成中的引擎调用量：

   * 记录插入（即，新记录）:1个引擎调用
   * 记录删除：1个引擎调用
   * 记录更新：2个引擎调用（如果目标记录与源记录相同，即，如果ACS记录没有更改，则仅有1个调用）

   在估计整个ACS引擎调用量时，必须考虑其他引擎调用来源，包括登陆页、WebApps、JSSP、API、移动应用程序注册等。

   视图活动包信息：https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html

* 该集成最多支持3000万个联系人。

* 标准集成产品包括对最多五个自定义实体的支持

* 超过50万条记录的自定义实体需要额外的咨询时间才能通过活动工作流执行一次性（每个自定义实体）基于文件的初始导入（这会产生额外成本）

* 标准集成产品包括对最多50列的自定义实体的支持。

* 在实施集成之前，您需要创建并发布自定义资源。

* 链接表时最大表深度为两个（即表1->表2->表3）

* 对Dynamic 365数据类型的支持有限。 如果您的数据模型包含简单数据类型以外的数据类型（例如字符串、整数、小数等），则可能需要在使用集成之前更新您的数据模型。

* 在活动自定义实体中保留现有数据可能会产生额外的咨询成本，以准备用于集成的数据。

* Adobe和客户之间可能需要建立入门维护窗口，因为初始摄取可能导致活动速度减慢。

* 我们鼓励您交流集成使用率显着增加或“高峰”的已知实例（例如，新记录或更新记录的急剧增加），因为这可能会导致数据同步速度变慢。

* 作为集成的一部分，您应完成Microsoft Azure和Dynamics 365中的预集成配置步骤。 请参阅此页上的配置步骤[](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)

* 您应将Dynamics 365和活动数据模型集成并加以维护。

## 集成边界

该集成旨在解决Dynamics 365与活动之间常见数据移动的一般用例，但它并非旨在解决每个客户特有的每个用例：

* 该集成不会发布任何隐私（例如GDPR）删除。 满足最终用户隐私要求的责任由客户承担；这些请求应在活动(通过Adobe Experience Platform Privacy Service)和Dynamics 365中独立提出。 如果需要，该集成会发出定期删除，以帮助进行数据同步。

* 用户档案或自定义实体数据不会从活动同步到Dynamics 365，但选择退出信息除外（如果客户配置）。

* 活动订阅管理（即订阅／取消订阅）本机不受支持。

* 不支持在Dynamics 365中编写和触发活动电子邮件活动。

* 该集成将不支持在Dynamics 365和活动数据模型之间重构数据。 预计集成将将一个Dynamics 365表同步到一个活动表。

* 集成的当前版本不提供自助UI。
