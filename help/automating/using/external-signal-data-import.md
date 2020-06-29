---
title: 外部信号和数据导入
description: 以下示例说明了与数据导入一起使用的外部信号活动。
page-status-flag: never-activated
uuid: 884b6daf-bfd9-440b-8336-004b80c76def
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 911c71b5-da8b-4916-b645-13bba6d21715
context-tags: signal,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 0%

---


# 外部信号和数据导入 {#external-signal-data-import}

以下示例说明 **[!UICONTROL External signal]** 了典型用例中的活动。 在源工作流中执行数据导入。 完成导入并更新数据库后，将触发另一个工作流。 第二个工作流用于更新导入数据的聚合。

源工作流如下所示：

* 加载 [文件活动](../../automating/using/load-file.md) ，上传包含新购买数据的文件。 请注意，数 [据库已相应扩展](../../developing/using/data-model-concepts.md) ，因为默认情况下，数据库中不存在购买数据。

   例如：

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2015;dannymars@example.com;A2;799
   aze124;28/05/2015;dannymars@example.com;A7;8
   aze125;31/07/2015;john.smith@example.com;A7;8
   aze126;14/12/2015;john.smith@example.com;A10;4
   aze127;02/01/2016;dannymars@example.com;A3;79
   aze128;04/03/2016;clara.smith@example.com;A8;149
   ```

* 对帐 [活动](../../automating/using/reconciliation.md) 会创建导入数据与数据库之间的链接，以便事务数据能够正确连接到用户档案和产品。
* “更 [新”活动](../../automating/using/update-data.md) ，用传入数据插入并更新数据库的“事务”资源。
* 结束 [活动](../../automating/using/start-and-end.md) 会触发目标工作流，该工作流用于更新聚合。

![](assets/signal_example_source1.png)

目标工作流如下所示：

* 外部 [信号活动](../../automating/using/external-signal.md) ，会等待源工作流成功完成。
* 查询 [活动](../../automating/using/query.md#enriching-data) 目标用户档案，并通过集合集对进行丰富，以检索上次购买日期。
* 更 [新活动](../../automating/using/update-data.md) ，将附加数据存储在专用自定义字段中。 请注意，用户档案资源已扩展，可添加“上 **次购买日期** ”字段。

![](assets/signal_example_source2.png)
