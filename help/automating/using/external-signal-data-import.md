---
title: 外部信号和数据导入
description: 以下示例说明了与数据导入一起使用的外部信号活动。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: signal,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: e2997cf5-861b-4202-aeb7-3a47c4d55bef
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 79%

---

# 外部信号和数据导入 {#external-signal-data-import}

下方的示例展示了典型使用案例中的 **[!UICONTROL External signal]** 活动。在源工作流中执行数据导入。完成导入并更新数据库后，将触发第二个工作流。第二个工作流用于更新导入数据的聚合。

源工作流如下所示：

* [加载文件](../../automating/using/load-file.md)活动，上传包含新购买数据的文件。请注意，[数据库已扩展](../../developing/using/data-model-concepts.md)，因为默认情况下，数据库中不存在购买数据。

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

* [协调活动](../../automating/using/reconciliation.md)会创建导入数据与数据库之间的链接，以便交易数据能够正确连接到轮廓和产品。
* [更新数据](../../automating/using/update-data.md)活动，使用传入数据插入并更新数据库的交易资源。
* [End](../../automating/using/start-and-end.md)活动会触发用于更新聚合的目标工作流。

![](assets/signal_example_source1.png)

目标工作流如下所示：

* [外部信号](../../automating/using/external-signal.md)活动等待源工作流成功完成。
* [查询](../../automating/using/query.md#enriching-data)活动会定向轮廓，并通过集合集对进行扩充，以检索上次购买日期。
* [更新数据](../../automating/using/update-data.md)活动将附加数据存储在专用的自定义字段中。请注意，轮廓资源已扩展，添加了 **Last purchase date** 字段。

![](assets/signal_example_source2.png)
