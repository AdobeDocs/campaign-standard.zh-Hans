---
title: 计算发送日期
description: 了解如何在特定的日期和时间发送消息。
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

您可以定义一个公式，以在特定日期和时间将消息发送给每个收件人。

## 自定义日期公式 {#customizing-date-formula}

例如，可以在启动过程中使用发送时间优化。

使用新平台发送电子邮件时，Internet服务提供商(ISP)会怀疑无法识别的IP地址。 如果突然发送大量电子邮件，ISP通常会将其标记为垃圾邮件。

为了避免被标记为垃圾邮件，您可以通过在不同时间分发大量电子邮件来逐步增加发送量。 这应该可以确保启动阶段的顺利发展，并帮助您降低地址无效的总比率。

例如，您可以随机细分目标受众，以分五批发送投放。 您将在6月1日上午10:00发送第一批占目标受众10%的邮件，在24小时后发送第二批占目标受众15%的邮件，依此类推。

您可以使用工作流计划此操作。

![](assets/send-time_opt_workflow1.png)

1. 访问营销活动列表并创建新工作流。 请参阅 [创建工作流](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. 拖放 **查询** 活动并将其打开。 请参阅 [查询](../../automating/using/query.md) 部分。
1. 选择一个受众，例如您的所有Gold客户，然后单击 **[!UICONTROL Confirm]** 以保存查询。
1. 拖放 **分段** 活动并将其打开。 请参阅 [分段](../../automating/using/segmentation.md) 部分。
1. 定义五个区段。 对于每个区段：

   * 填写 **[!UICONTROL Segment code]** 字段：手动输入发送消息的所需日期和时间。

     例如，您希望在6月1日上午10:00 GMT+1发送第一批。 使用以下格式： **YYYY-MM-DD hh:mm:ss+tz**.

     ![](assets/send-time_opt_segment_configuration.png)

     要在发送后的第二天发送下一个批次，请输入 **2017-06-02 10:00:00+01** 用于第二个区段。

     对于剩余的段，按以下方式定义后续的批：

      * **2017-06-03 10:00:00+01**
      * **2017-06-04 10:00:00+01**
      * **2017-06-05 10:00:00+01**

   * 确保选择 **[!UICONTROL Limit the population of this segment]** 选项。

     在 **[!UICONTROL Limitation]** 选项卡，选择 **[!UICONTROL Random sampling]** 并为每个区段输入所需的百分比：第一个批为10，第二个批为15，依此类推。

     ![](assets/send-time_opt_segment_limitation.png)

1. 定义所有区段后，选择 **[!UICONTROL Generate all segments in the same transition]** 并单击 **[!UICONTROL Confirm]**.

   ![](assets/send-time_opt_segment_dates.png)

1. 拖放 **电子邮件投放** 活动并将其打开。 请参阅 [电子邮件投放](../../automating/using/email-delivery.md) 部分。
1. 单击 **[!UICONTROL Schedule]** 区域，然后选择 **[!UICONTROL Messages to be sent automatically on the date specified below]**.
1. 在 **[!UICONTROL Start sending from]** 字段，定义联系日期。
1. 从发送时间优化下拉菜单中，选择 **[!UICONTROL Send at a custom date defined by a formula]**.
1. 单击 **[!UICONTROL Edit an expression]** 的按钮 **[!UICONTROL Custom date formula]** 字段。

   ![](assets/send-time_opt_formula_define.png)

1. 使用以下表达式创建 **[!UICONTROL ToDateTime]** 函数和 **[!UICONTROL Segment code]** 字段。 您也可以直接在表达式中键入，但请确保使用正确的语法和拼写。

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   此 **[!UICONTROL ToDateTime]** 函数将段代码从文本字符串转换为日期和时间值。

   确认表达式以返回到上一个屏幕。

   ![](assets/send-time_opt_formula_define_segment.png)

   在 **[!UICONTROL Schedule]** 窗口中，自定义日期公式显示如下：

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   ![](assets/send-time_opt_custom_formula.png)

1. 确认计划，保存投放并执行工作流。

该投放将在5天内逐步发送给所有定向的收件人。

>[!NOTE]
>
>确认发送时，请确保所有日期都是未来的日期。 否则，一旦确认发送，将立即发送消息。

## 使用表达式 {#using-an-expression}

发送时间优化对于涉及呼叫中心的营销活动也很有用。 您可以确保所有消息不会同时收到。 这样，您的组织就可以根据其容量处理呼叫数。

例如，您想要发送一封电子邮件，邀请客户联系呼叫中心以获取促销优惠。 为避免让呼叫中心不堪重负，您决定随机细分目标受众，以分四批发送电子邮件。

您可以使用工作流计划此操作。

![](assets/send-time_opt_workflow2.png)

1. 访问营销活动列表并创建新工作流。 请参阅 [创建工作流](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. 拖放 **查询** 活动并将其打开。 请参阅 [查询](../../automating/using/query.md) 部分。
1. 选择一个受众，例如超过35个配置文件，然后单击 **[!UICONTROL Confirm]** 以保存查询。
1. 拖放 **分段** 活动并将其打开。 请参阅 [分段](../../automating/using/segmentation.md) 部分。
1. 定义四个区段。 对于每个区段：

   * 按以下方式定义区段代码：

      * 上午8:00 — 上午10:00： **0**. 该消息将于上午8:00（联系日期）发送给目标群体的第一季度。
      * 上午10:00 — 中午12:00： **2**. 该消息将于上午10:00（联系日期+ 2小时）发送到目标群体的第二季度。
      * 下午2:00 — 下午4:00： **6**. 呼叫中心在下午12:00到下午2:00之间关闭，则消息将在下午2:00（联系日期+ 6个小时）发送到目标人口的第三季度。
      * 下午4:00 — 下午6:00： **8**. 该消息将在下午4:00（联系日期+ 8小时）发送给目标群体的最后一个季度。

     >[!NOTE]
     >
     >联系人日期稍后将在工作流中的电子邮件投放活动中定义。

   * 确保选择 **[!UICONTROL Limit the population of this segment]** 选项。
   * 在 **[!UICONTROL Limitation]** 选项卡，选择 **[!UICONTROL Random sampling]** 并为每个区段输入所需的百分比： **25**.

1. 定义所有区段后，选择 **[!UICONTROL Generate all segments in the same transition]** 并单击 **[!UICONTROL Confirm]**.

   ![](assets/send-time_opt_segment.png)

1. 拖放 **电子邮件投放** 活动并将其打开。 请参阅 [电子邮件投放](../../automating/using/email-delivery.md) 部分。
1. 单击 **[!UICONTROL Schedule]** 区域。
1. 选择 **[!UICONTROL Messages to be sent automatically on the date specified below]**。
1. 在 **[!UICONTROL Start sending from]** 字段，定义联系日期。

   在此示例中，选择5月25日上午8:00。

1. 从发送时间优化下拉菜单中，选择 **[!UICONTROL Send at a custom date defined by a formula]** 然后单击 **[!UICONTROL Edit an expression]** 按钮。

   ![](assets/send-time_opt_formula_expression.png)

1. 在 **[!UICONTROL Expression editor]**，设置日期和区段代码以计算每个客户的数据。

   在函数列表中，选择 **[!UICONTROL AddHours]**.

   ![](assets/send-time_opt_formula_expression_addhours.png)

   在可用字段中，选择 **[!UICONTROL Current delivery]** > **[!UICONTROL Delivery scheduling]** > **[!UICONTROL Contact date]**.

   ![](assets/send-time_opt_formula_expression_contact_date.png)

   这使您能够检索 **[!UICONTROL Start sending from]** 字段。

   在函数列表中，选择 **[!UICONTROL ToInteger]**. 在可用字段中，选择 **[!UICONTROL Additional data]** > **[!UICONTROL Segment code]**.

   ![](assets/send-time_opt_formula_expression_segment_code.png)

   这使您可以检索您在区段代码中指定的编号。

   您应获得以下公式：

   ```
   AddHours([currentDelivery/scheduling/@contactDate], ToInteger([targetData/@segmentCode]))
   ```

1. 确认以保存表达式。 确认计划，保存投放并执行工作流。

* 第一部分将在联系日期（5月25日上午8:00）收到消息。
* 第二个区段将在两小时后（5月25日上午10:00）收到消息。
* 第三部分将在6小时后（5月25日下午2:00）收到消息。
* 第四个区段将在八小时后（5月25日下午4点）收到消息。
