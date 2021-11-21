---
title: 计算发送日期
description: 了解如何在特定日期和时间发送消息。
audience: sending
content-type: reference
topic-tags: sheduling-messages
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: 7a0cd10a-24e6-44d1-842c-2067bfbac838
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '998'
ht-degree: 1%

---

# 计算发送日期{#computing-the-sending-date}

您可以定义一个公式，以在特定日期和时间向每个收件人发送消息。

## 自定义日期公式 {#customizing-date-formula}

例如，您可以在启动过程中使用发送时间优化。

使用新平台发送电子邮件时，互联网服务提供商(ISP)会怀疑无法识别的IP地址。 如果突然发送了大量电子邮件，ISP通常会将它们标记为垃圾邮件。

为避免被标记为垃圾邮件，您可以通过在不同时间分发大量电子邮件来逐步增加发送量。 这应该可以确保启动阶段的顺利开发，并使您能够降低无效地址的整体速率。

例如，您可以随机对目标受众进行分段，以便分五批发送投放。 您将在6月1日上午10点发送第一批代表目标受众10%的受众，24小时后再次发送一批代表目标受众15%的受众，依此类推。

您可以使用工作流计划此操作。

![](assets/send-time_opt_workflow1.png)

1. 访问营销活动列表并创建新工作流。 请参阅 [创建工作流](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. 拖放 **查询** 活动并将其打开。 请参阅 [查询](../../automating/using/query.md) 中。
1. 选择一个受众，例如所有金牌客户，然后单击 **[!UICONTROL Confirm]** 来保存查询。
1. 拖放 **分段** 活动并将其打开。 请参阅 [分段](../../automating/using/segmentation.md) 中。
1. 定义五个区段。 对于每个区段：

   * 填写 **[!UICONTROL Segment code]** 字段：手动输入发送消息所需的日期和时间。

      例如，您希望在6月1日上午10:00 GMT+1发送第一批。 使用以下格式： **YYYY-MM-DD hh:mm:ss+tz**.

      ![](assets/send-time_opt_segment_configuration.png)

      要在次日发送下一批，请输入 **2017-06-02 10:00:00+01** 第二段。

      对于其余区段，按如下方式定义下一批：

      * **2017-06-03 10:00:00+01**
      * **2017-06-04 10:00:00+01**
      * **2017-06-05 10:00:00+01**
   * 确保选择 **[!UICONTROL Limit the population of this segment]** 选项。

      在 **[!UICONTROL Limitation]** 选项卡，选择 **[!UICONTROL Random sampling]** 并为每个区段输入所需的百分比：第一批10，第二批15，依此类推。

      ![](assets/send-time_opt_segment_limitation.png)


1. 定义所有区段后，选择 **[!UICONTROL Generate all segments in the same transition]** 单击 **[!UICONTROL Confirm]**.

   ![](assets/send-time_opt_segment_dates.png)

1. 拖放 **电子邮件投放** 活动并将其打开。 请参阅 [电子邮件投放](../../automating/using/email-delivery.md) 中。
1. 单击 **[!UICONTROL Schedule]** ，然后选择 **[!UICONTROL Messages to be sent automatically on the date specified below]**.
1. 在 **[!UICONTROL Start sending from]** 字段中，定义联系日期。
1. 从发送时间优化下拉菜单中，选择 **[!UICONTROL Send at a custom date defined by a formula]**.
1. 单击 **[!UICONTROL Edit an expression]** 按钮 **[!UICONTROL Custom date formula]** 字段。

   ![](assets/send-time_opt_formula_define.png)

1. 使用以下表达式创建 **[!UICONTROL ToDateTime]** 函数和 **[!UICONTROL Segment code]** 字段。 您还可以直接键入表达式，但请确保使用正确的语法和拼写。

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   的 **[!UICONTROL ToDateTime]** 函数会将段码从文本字符串转换为日期和时间值。

   确认表达式以返回到上一屏幕。

   ![](assets/send-time_opt_formula_define_segment.png)

   在 **[!UICONTROL Schedule]** ，则自定义日期公式如下所示：

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   ![](assets/send-time_opt_custom_formula.png)

1. 确认计划、保存投放并执行工作流。

该投放将在五天内逐步发送给所有目标收件人。

>[!NOTE]
>
>确认发送时，请确保所有日期都在将来。 否则，确认发送后将立即发送消息。

## 使用表达式 {#using-an-expression}

发送时间优化对于涉及呼叫中心的促销活动也非常有用。 您可以确保不会同时收到所有消息。 这样，贵组织便可以根据其能力处理呼叫数。

例如，您希望发送一封电子邮件，邀请您的客户联系呼叫中心以获取促销优惠。 为避免呼叫中心人气过大，您决定随机将目标受众分段，以分四批发送电子邮件。

您可以使用工作流计划此操作。

![](assets/send-time_opt_workflow2.png)

1. 访问营销活动列表并创建新工作流。 请参阅 [创建工作流](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. 拖放 **查询** 活动并将其打开。 请参阅 [查询](../../automating/using/query.md) 中。
1. 选择受众，例如超过35个用户档案，然后单击 **[!UICONTROL Confirm]** 来保存查询。
1. 拖放 **分段** 活动并将其打开。 请参阅 [分段](../../automating/using/segmentation.md) 中。
1. 定义四个区段。 对于每个区段：

   * 按如下方式定义区段代码：

      * 上午8:00 — 上午10:00: **0**. 该消息将在上午8:00（联系日期）发送到目标群体的第一季度。
      * 上午10:00 — 中午12:00: **2**. 该消息将在上午10:00（联系日期+ 2小时）发送到目标群体的第二季度。
      * 下午2:00 — 下午4:00: **6**. 呼叫中心在中午12:00至下午2:00之间关闭，消息将在下午2:00（联系日期+ 6小时）发送到目标群体的第三季度。
      * 下午4:00 — 下午6:00: **8**. 该消息将在下午4:00（联系日期+ 8小时）发送到目标群体的最后四分之一。

      >[!NOTE]
      >
      >联系日期将在工作流稍后的电子邮件投放活动中定义。

   * 确保选择 **[!UICONTROL Limit the population of this segment]** 选项。
   * 在 **[!UICONTROL Limitation]** 选项卡，选择 **[!UICONTROL Random sampling]** 并为每个区段输入所需的百分比： **25**.


1. 定义所有区段后，选择 **[!UICONTROL Generate all segments in the same transition]** 单击 **[!UICONTROL Confirm]**.

   ![](assets/send-time_opt_segment.png)

1. 拖放 **电子邮件投放** 活动并将其打开。 请参阅 [电子邮件投放](../../automating/using/email-delivery.md) 中。
1. 单击 **[!UICONTROL Schedule]** 的子菜单。
1. 选择 **[!UICONTROL Messages to be sent automatically on the date specified below]**。
1. 在 **[!UICONTROL Start sending from]** 字段中，定义联系日期。

   在本例中，选择5月25日上午8:00。

1. 从发送时间优化下拉菜单中，选择 **[!UICONTROL Send at a custom date defined by a formula]** ，然后单击 **[!UICONTROL Edit an expression]** 按钮。

   ![](assets/send-time_opt_formula_expression.png)

1. 在 **[!UICONTROL Expression editor]**，设置日期和区段代码以计算每个客户的数据。

   在函数列表中，选择 **[!UICONTROL AddHours]**.

   ![](assets/send-time_opt_formula_expression_addhours.png)

   在可用字段中，选择 **[!UICONTROL Current delivery]** > **[!UICONTROL Delivery scheduling]** > **[!UICONTROL Contact date]**.

   ![](assets/send-time_opt_formula_expression_contact_date.png)

   这样，您便可以检索 **[!UICONTROL Start sending from]** 字段。

   在函数列表中，选择 **[!UICONTROL ToInteger]**. 在可用字段中，选择 **[!UICONTROL Additional data]** > **[!UICONTROL Segment code]**.

   ![](assets/send-time_opt_formula_expression_segment_code.png)

   这样，您就可以检索在段码中指定的数字。

   您应该获得以下公式：

   ```
   AddHours([currentDelivery/scheduling/@contactDate], ToInteger([targetData/@segmentCode]))
   ```

1. 确认保存表达式。 确认计划、保存投放并执行工作流。

* 第一个客户群将在联系日期（5月25日上午8点）收到消息。
* 第二个区段将在两小时后（5月25日上午10:00）收到消息。
* 第三个区段将在六小时后（5月25日下午2:00）收到消息。
* 第四个区段将在八小时后（5月25日下午4:00）收到消息。
