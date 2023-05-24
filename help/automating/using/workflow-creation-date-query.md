---
title: 在設定檔建立日期建立傳送
description: 此使用案例顯示如何在設定檔建立日期建立傳送。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: f611e023-f74c-476e-83b9-aff451f68c81
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 38%

---

# 在用户档案的创建日期创建投放 {#creation-date-query}

您可以在客戶建立設定檔的週年紀念日透過電子郵件傳送優惠方案。

1. 在 **[!UICONTROL Marketing Activities]** 中，单击 **[!UICONTROL Create]** 并选择 **[!UICONTROL Workflow]**。
1. 选择 **[!UICONTROL New Workflow]** 作为工作流类型并单击 **[!UICONTROL Next]**。
1. 输入工作流的属性并单击 **[!UICONTROL Create]**。

## 创建调度程序活动 {#creating-a-scheduler-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Execution]**，拖放 [排程器](../../automating/using/scheduler.md) 活動。
1. 双击该活动。
1. 配置投放的执行方式。
1. 在 **[!UICONTROL Execution frequency]** 中，选择 **[!UICONTROL Daily]**。
1. 選取 **[!UICONTROL Time]** 和 **[!UICONTROL Repetition frequency]** 工作流程的執行階段。
1. 選取 **[!UICONTROL Start]** 日期和 **[!UICONTROL Expiration]** 用於工作流程。
1. 确认您的活动并保存工作流。

>[!NOTE]
>
>若要在特定時區啟動工作流程，請在 **[!UICONTROL Execution options]** 索引標籤中，為排程器設定時區 **[!UICONTROL Time zone]** 欄位。 默认情况下，所选时区就是在工作流属性中定义的时区（请参阅[构建工作流](../../automating/using/building-a-workflow.md)）。

![](assets/time_zone.png)

## 创建查询活动 {#creating-a-query-activity}

1. 若要選取收件者，請拖放 [查詢](../../automating/using/query.md) 活動並連按兩下。
1. 新增 **[!UICONTROL Profiles]** 並選取 **[!UICONTROL no longer contact by email]** 包含值 **[!UICONTROL no]**.

### 擷取在執行當天的同一天建立的設定檔 {#retrieving-profiles-created-on-the-same-day}

1. 在 **[!UICONTROL Profile]**，拖放 **[!UICONTROL Created]** 欄位。 並按一下 **[!UICONTROL Advanced Mode]**.
   ![](assets/advanced_mode.png)
1. 在 **[!UICONTROL list of functions]**，按兩下 **[!UICONTROL Day]** 從 **[!UICONTROL Date]** 節點。
1. 然後，插入欄位 **[!UICONTROL Created]** 作為引數。
1. 選取 **[!UICONTROL equals to (=)]** 作為運運算元。
1. 對於值，選取 **[!UICONTROL Day]** 從 **[!UICONTROL Date]** 中的節點 **[!UICONTROL List of functions]**.
1. 插入 **[!UICONTROL GetDate()]** 函式為引數。

您已擷取建立日期等於當天的設定檔。

您最後應該會得到：

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

单击 **[!UICONTROL Confirm]**。

### 擷取在執行月份的同一個月建立的設定檔{#retrieving-profiles-created-on-the-same-month}

1. 於 **[!UICONTROL Query]** 編輯器中，選取第一個查詢並複製它。
1. 開啟副本。
1. Replace **[!UICONTROL Day]** 作者： **[!UICONTROL Month]** 在查詢中。
1. 单击 **[!UICONTROL Confirm]**。

![](assets/month_rule.png)

您最後應該會遇到以下問題：

``` Month(@created) = Month(GetDate()) ```

最終查詢隨即顯示：

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## 创建电子邮件投放{#creating-an-email-delivery}

1. 拖放 [電子郵件傳遞](../../automating/using/email-delivery.md) 活動。
1. 单击活动，然后选择 ![](assets/edit_darkgrey-24px.png) 以进行编辑。
1. 选择 **[!UICONTROL Recurring email]** 并单击 **[!UICONTROL Next]**。
1. 选择电子邮件模板，然后单击 **[!UICONTROL Next]**。
1. 输入电子邮件属性，然后单击 **[!UICONTROL Next]**。
1. 要创建电子邮件的布局，请单击 **[!UICONTROL Email Designer]**。
1. 插入元素或选择现有模板。
1. 使用字段和链接将电子邮件个性化。有关更多信息，请参阅[设计电子邮件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。
1. 单击 **[!UICONTROL Preview]** 以检查布局。
1. 单击 **[!UICONTROL Save]**。

**相关主题：**

* [电子邮件渠道](../../channels/using/creating-an-email.md)
