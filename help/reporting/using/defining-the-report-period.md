---
title: 定义报告周期
description: 报告的时段允许您根据选定的日期过滤数据。
audience: reporting
content-type: reference
topic-tags: list-of-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: 1fa05187-0488-4649-b903-079bfa4628f1
TQID: 'https://experienceleague.adobe.com/1ubxoguqhz9JzUE2T-H1wXGLDOCnSVaU1Tfo4dzex9w'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c309ee4e-82e4-4f7e-b608-ef345678c34e
    internal-label: Dynamic reporting
subfeature_v2:
  - id: b3a4149f-2b3a-44d1-894e-e3ac4c77fb47
    internal-label: Reporting interface
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 3%
---
# 定义报告周期{#defining-the-report-period}

>[!NOTE]
>
>数据报表仅可用于最近三年。 有关数据保留期的更多信息，请联系Adobe顾问或您的技术管理员。

在启动或访问报表之前，必须应用时间段。 可以在报告的右上角访问给定的时间段。

默认情况下，对于营销策划或营销策划，过滤期限设置为营销策划或营销策划的开始和结束日期。 对于投放，开始日期对应于发送日期，结束日期对应于发送日期加7天。

要修改过滤器，请选择开始日期和时间段，或使用预设时间段，如上周、两个月前等。

当应用或修改过滤器时，报表会自动更新。 所选报告时段将管理该时段内发生的事件，而不是在间隔内创建的投放的整个数据集，例如，如果投放从1月1日至5日运行且报告时段是1月1日至2日，则您可能会看到部分数据。 这会影响打开/点击计数，因为即使在发送投放一个月后，也可能会发生打开或点击。

![](assets/campaign_reports_5.png)
