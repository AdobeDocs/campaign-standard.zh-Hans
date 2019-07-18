---
title: 计算发送日期
seo-title: 计算发送日期
description: 计算发送日期
seo-description: 了解如何在特定日期和时间发送消息。
page-status-flag: 从未激活
uuid: fbbb37a0-7257-4407-a4 c9-f76 ff04460 d4
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 发送
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 02a87cc6-c40 c-44fe-bb4 e-b68870 a4859 b
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 28abc1e8aa31f3e0c7f09926f34a977d4c491fd8

---


# Computing the sending date{#computing-the-sending-date}

您可以定义一个公式，以在特定日期和时间向每个收件人发送消息。

## Customizing date formula {#customizing-date-formula}

例如，您可以在渐变过程中使用发送时间优化。

通过使用新平台发送电子邮件时，Internet服务提供商(ISP)对IP地址不被识别的问题存有怀疑。如果突然发送大量电子邮件，ISP通常会将它们标记为垃圾邮件。

为避免被标记为垃圾邮件，您可以逐步增加通过不同时间分发大量电子邮件发送的卷。这应确保顺利开发启动阶段，使您能够降低无效地址的总体速率。

例如，您可以随机细分目标受众，以五批次发送您的交付。您将在月日上午10：00发送第一批代表目标受众的第一批电话，在24小时后再次分批发送，其中有15%的受众，依此类推。

您可以使用工作流来安排此操作。

![](assets/send-time_opt_workflow1.png)

1. 访问营销活动列表并创建新工作流程。See [Creating a workflow](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Drag and drop a **Query** activity into your workflow and open it. See the [Query](../../automating/using/query.md) section.
1. Select an audience, for example all your Gold customers and click **[!UICONTROL Confirm]** to save the query.
1. Drag and drop a **Segmentation** activity into your workflow and open it. See the [Segmentation](../../automating/using/segmentation.md) section.
1. 定义五个细分。对于每个区段：

   * Fill in the **[!UICONTROL Segment code]** field: manually enter the desired date and time for sending the message.

      例如，您希望在月日晚上10：00发送第一批批次。Use the following format: **YYYY-MM-DD hh:mm:ss+tz**.

      ![](assets/send-time_opt_segment_configuration.png)

      To send the next batch the day after, enter **2017-06-02 10:00:00+01** for the second segment.

      对于其余区段，按如下方式定义下一批次：

      * **2017-06-03 10:00:00+01**
      * **2017-06-04 10:00:00+01**
      * **2017-06-05 10:00:00+01**
   * Make sure you select the **[!UICONTROL Limit the population of this segment]** option.

      In the **[!UICONTROL Limitation]** tab, select **[!UICONTROL Random sampling]** and enter the desired percentage for each segment: 10 for the first batch, 15 for the second, and so on.

      ![](assets/send-time_opt_segment_limitation.png)


1. Once all segments are defined, select **[!UICONTROL Generate all segments in the same transition]** and click **[!UICONTROL Confirm]**.

   ![](assets/send-time_opt_segment_dates.png)

1. Drag and drop an **Email delivery** activity into your workflow and open it. See the [Email delivery](../../automating/using/email-delivery.md) section.
1. Click the **[!UICONTROL Schedule]** section in the email dashboard and select **[!UICONTROL Messages to be sent automatically on the date specified below]**.
1. In the **[!UICONTROL Start sending from]** field, define a contact date.
1. From the send time optimization drop-down menu, choose **[!UICONTROL Send at a custom date defined by a formula]**.
1. Click the **[!UICONTROL Edit an expression]** button of the **[!UICONTROL Custom date formula]** field.

   ![](assets/send-time_opt_formula_define.png)

1. Create the following expression using the **[!UICONTROL ToDateTime]** function and the **[!UICONTROL Segment code]** field. 您还可以直接键入表达式，但确保使用正确的语法和拼写。

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   **[!UICONTROL ToDateTime]** 该函数将区段代码从文本字符串转换为日期和时间值。

   确认表达式返回到上一屏幕。

   ![](assets/send-time_opt_formula_define_segment.png)

   **[!UICONTROL Schedule]** 在窗口中，自定义日期公式将按如下方式显示：

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   ![](assets/send-time_opt_custom_formula.png)

1. 确认计划，保存交付并执行工作流。

将在天内以渐进方式向所有目标收件人发送分发。

>[!NOTE]
>
>确认发送时，确保所有日期都是将来的日期。否则，发送确认消息后将发送消息。

## Using an expression {#using-an-expression}

发送时间优化也适用于涉及呼叫中心的营销活动。您可以确保不会同时接收所有消息。这使您的组织能够根据其容量处理调用数。

例如，您希望发送一封电子邮件邀请客户联系呼叫中心，获取促销优惠。为避免超出呼叫中心，您决定将目标受众随机细分，以通过四批发送您的电子邮件。

您可以使用工作流来安排此操作。

![](assets/send-time_opt_workflow2.png)

1. 访问营销活动列表并创建新工作流程。See [Creating a workflow](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Drag and drop a **Query** activity into your workflow and open it. See the [Query](../../automating/using/query.md) section.
1. Select an audience, for example over 35 profiles and click **[!UICONTROL Confirm]** to save the query.
1. Drag and drop a **Segmentation** activity into your workflow and open it. See the [Segmentation](../../automating/using/segmentation.md) section.
1. 定义四个细分。对于每个区段：

   * 定义区段代码，如下所示：

      * 8:00 AM - 10:00 AM: **0**. 邮件将发送至目标人群的第一季度(联系日期)。
      * 10:00 AM - 12:00 PM: **2**. 邮件将在目标人群的第二季度发送至10：00AM(联系日期+小时)。
      * 2:00 PM - 4:00 PM: **6**. 呼叫中心在12：00PM和2：00PM之间关闭，邮件将发送至目标人群的第三季度(联系日期+小时)。
      * 4:00 PM - 6:00 PM: **8**. 邮件将发送至目标人群的最后1/4(联系日期+小时)。
      >[!NOTE]
      >
      >稍后将在工作流中的电子邮件分发活动中定义联系日期。

   * Make sure you select the **[!UICONTROL Limit the population of this segment]** option.
   * In the **[!UICONTROL Limitation]** tab, select **[!UICONTROL Random sampling]** and enter the desired percentage for each segment: **25**.


1. Once all segments are defined, select **[!UICONTROL Generate all segments in the same transition]** and click **[!UICONTROL Confirm]**.

   ![](assets/send-time_opt_segment.png)

1. Drag and drop an **Email delivery** activity into your workflow and open it. See the [Email delivery](../../automating/using/email-delivery.md) section.
1. Click the **[!UICONTROL Schedule]** section in the email dashboard.
1. Select **[!UICONTROL Messages to be sent automatically on the date specified below]**.
1. In the **[!UICONTROL Start sending from]** field, define a contact date.

   在此示例中，选择月25日上午8：00。

1. From the send time optimization drop-down menu, choose **[!UICONTROL Send at a custom date defined by a formula]** and click the **[!UICONTROL Edit an expression]** button.

   ![](assets/send-time_opt_formula_expression.png)

1. In the **[!UICONTROL Expression editor]**, set the date and the segment codes to compute the data for each customer.

   In the list of functions, select **[!UICONTROL AddHours]**.

   ![](assets/send-time_opt_formula_expression_addhours.png)

   In the available fields, select **[!UICONTROL Current delivery]** &gt; **[!UICONTROL Delivery scheduling]** &gt; **[!UICONTROL Contact date]**.

   ![](assets/send-time_opt_formula_expression_contact_date.png)

   This enables you to retrieve the date and time specified in the **[!UICONTROL Start sending from]** field.

   In the list of functions, select **[!UICONTROL ToInteger]**. In the available fields, select **[!UICONTROL Additional data]** &gt; **[!UICONTROL Segment code]**.

   ![](assets/send-time_opt_formula_expression_segment_code.png)

   这使您能够检索在区段代码中指定的数字。

   您应获得以下公式：

   ```
   AddHours([currentDelivery/scheduling/@contactDate], ToInteger([targetData/@segmentCode]))
   ```

1. 确认以保存您的表达式。确认计划，保存交付并执行工作流。

* 第一个区段将在联系日期(月25日上午8：00)收到消息。
* 第二个区段将在两小时后(月25日上午10：00)收到消息。
* 第三个区段将在六小时后(月25日下午2：00)收到消息。
* 第四个区段将在八小时后(月25日下午4：00)收到消息。

