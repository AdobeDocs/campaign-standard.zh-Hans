---
title: 计算发送日期
description: 了解如何在特定日期和时间发送消息。
page-status-flag: 从未激活
uuid: fbbb37a0-7257-4407-a4c9-f76bf04460d4
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 发送
content-type: 参考
topic-tags: 调度消息
discoiquuid: 02a87cc6-c40c-44fe-bb4e-b68870a4859b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 计算发送日期{#computing-the-sending-date}

您可以定义一个公式，以在特定日期和时间向每个收件人发送消息。

## 自定义日期公式 {#customizing-date-formula}

例如，您可以在升级过程中使用发送时间优化。

使用新平台发送电子邮件时，Internet服务提供商(ISP)会怀疑无法识别的IP地址。 如果突然发送了大量电子邮件，ISP通常会将其标记为垃圾邮件。

为避免被标记为垃圾邮件，您可以通过在不同时间分发大量电子邮件来逐渐增加发送量。 这应确保启动阶段的顺利开发，并使您能够降低无效地址的总体速率。

例如，您可以随机对目标受众进行细分，以将交货分五批发送。 您将在6月1日上午10:00（24小时后的第二批，15%的受众）发送第一批，其中10%是目标受众，依此类推。

您可以使用工作流计划此操作。

![](assets/send-time_opt_workflow1.png)

1. 访问营销活动列表并创建新的工作流。 请参 [阅创建工作流](../../automating/using/building-a-workflow.md#creating-a-workflow)。
1. 将查询活动拖 **放到工作流** ，然后将其打开。 请参阅 [查询](../../automating/using/query.md) 部分。
1. 选择受众，例如所有金牌客户，然后单击以 **[!UICONTROL Confirm]** 保存查询。
1. 将分段活动拖 **放到您的工作** 流中并将其打开。 请参阅 [分段](../../automating/using/segmentation.md) 。
1. 定义五个区段。 对于每个区段：

   * 填写字 **[!UICONTROL Segment code]** 段：手动输入发送消息所需的日期和时间。

      例如，您希望在6月1日上午10:00 GMT+1发送第一批批。 请使用以下格式： **YYYY-MM-DD hh:mm:ss+tz**。

      ![](assets/send-time_opt_segment_configuration.png)

      要在次日发送下一批，请为第 **二段输入2017-06-02 10:00:00+01** 。

      对于其余区段，请按如下方式定义下一批：

      * **2017-06-03 10:00:00+01**
      * **2017-06-04 10:00:00+01**
      * **2017-06-05 10:00:00+01**
   * 确保选择该选 **[!UICONTROL Limit the population of this segment]** 项。

      在标签 **[!UICONTROL Limitation]** 中，选择 **[!UICONTROL Random sampling]** 并输入每个区段的所需百分比：第一批10，第二批15，依此类推。

      ![](assets/send-time_opt_segment_limitation.png)


1. 定义所有区段后，选择并 **[!UICONTROL Generate all segments in the same transition]** 单击 **[!UICONTROL Confirm]**。

   ![](assets/send-time_opt_segment_dates.png)

1. 将电子邮件分发活 **动拖放到您的工作流** ，然后将其打开。 请参阅电 [子邮件发送](../../automating/using/email-delivery.md) 部分。
1. 单击电子 **[!UICONTROL Schedule]** 邮件功能板中的部分，然后选择 **[!UICONTROL Messages to be sent automatically on the date specified below]**。
1. 在字段 **[!UICONTROL Start sending from]** 中，定义联系人日期。
1. 从发送时间优化下拉菜单中，选择 **[!UICONTROL Send at a custom date defined by a formula]**。
1. 单击字 **[!UICONTROL Edit an expression]** 段的按 **[!UICONTROL Custom date formula]** 钮。

   ![](assets/send-time_opt_formula_define.png)

1. 使用函数和字段创 **[!UICONTROL ToDateTime]** 建以下表 **[!UICONTROL Segment code]** 达式。 您还可以直接键入表达式，但应确保使用正确的语法和拼写。

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   该函 **[!UICONTROL ToDateTime]** 数将段代码从文本字符串转换为日期和时间值。

   确认表达式以返回到上一个屏幕。

   ![](assets/send-time_opt_formula_define_segment.png)

   在窗口 **[!UICONTROL Schedule]** 中，自定义日期公式显示如下：

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   ![](assets/send-time_opt_custom_formula.png)

1. 确认计划、保存交付并执行工作流。

在五天内，将递送内容逐步发送到所有目标收件人。

>[!NOTE]
>
>确保确认发送时所有日期都在将来。 否则，消息将在确认发送后立即发送。

## 使用表达式 {#using-an-expression}

发送时间优化对于涉及呼叫中心的营销活动也很有用。 您可以确保不会同时接收所有消息。 这使您的组织能够根据其容量处理呼叫数。

例如，您希望发送电子邮件，邀请客户与呼叫中心联系以获得促销优惠。 为避免呼叫中心挤占用户，您决定随机对目标受众进行细分，以分四批发送电子邮件。

您可以使用工作流计划此操作。

![](assets/send-time_opt_workflow2.png)

1. 访问营销活动列表并创建新的工作流。 请参 [阅创建工作流](../../automating/using/building-a-workflow.md#creating-a-workflow)。
1. 将查询活动拖 **放到工作流** ，然后将其打开。 请参阅 [查询](../../automating/using/query.md) 部分。
1. 选择受众（例如，超过35个配置文件），然后单击 **[!UICONTROL Confirm]** 以保存查询。
1. 将分段活动拖 **放到您的工作** 流中并将其打开。 请参阅 [分段](../../automating/using/segmentation.md) 。
1. 定义四个区段。 对于每个区段：

   * 定义区段代码，如下所示：

      * 上午8:00 —— 上午10:00: **0**. 消息将在上午8:00（联系日期）发送到目标人群的第一季度。
      * 上午10:00 —— 下午12:00: **2**. 消息将在上午10:00（联系日期+ 2小时）发送到目标人口的第二季度。
      * 下午2:00 —— 下午4:00: **6**. 呼叫中心在下午12:00至2:00之间关闭，消息将在下午2:00（联系日期+ 6小时）发送到目标人群的第三季度。
      * 下午4:00 —— 下午6:00: **8**. 消息将在下午4:00（联系日期+ 8小时）发送到目标人群的最后一个季度。
      >[!NOTE]
      >
      >联系日期将在工作流稍后的电子邮件分发活动中定义。

   * 确保选择该选 **[!UICONTROL Limit the population of this segment]** 项。
   * 在标签 **[!UICONTROL Limitation]** 中，选择 **[!UICONTROL Random sampling]** 并输入每个区段的所需百分比： **25**.


1. 定义所有区段后，选择并 **[!UICONTROL Generate all segments in the same transition]** 单击 **[!UICONTROL Confirm]**。

   ![](assets/send-time_opt_segment.png)

1. 将电子邮件分发活 **动拖放到您的工作流** ，然后将其打开。 请参阅电 [子邮件发送](../../automating/using/email-delivery.md) 部分。
1. 单击电子 **[!UICONTROL Schedule]** 邮件功能板中的部分。
1. Select **[!UICONTROL Messages to be sent automatically on the date specified below]**.
1. 在字段 **[!UICONTROL Start sending from]** 中，定义联系人日期。

   在此示例中，选择5月25日上午8:00。

1. 从发送时间优化下拉菜单中，选择并 **[!UICONTROL Send at a custom date defined by a formula]** 单击该按 **[!UICONTROL Edit an expression]** 钮。

   ![](assets/send-time_opt_formula_expression.png)

1. 在中， **[!UICONTROL Expression editor]**&#x200B;设置日期和区段代码以计算每个客户的数据。

   在函数列表中，选择 **[!UICONTROL AddHours]**。

   ![](assets/send-time_opt_formula_expression_addhours.png)

   在可用字段中，选择 **[!UICONTROL Current delivery]** &gt; **[!UICONTROL Delivery scheduling]** &gt; **[!UICONTROL Contact date]**。

   ![](assets/send-time_opt_formula_expression_contact_date.png)

   这使您能够检索在字段中指定的日期和时间 **[!UICONTROL Start sending from]** 。

   在函数列表中，选择 **[!UICONTROL ToInteger]**。 在可用字段中，选择 **[!UICONTROL Additional data]** &gt; **[!UICONTROL Segment code]**。

   ![](assets/send-time_opt_formula_expression_segment_code.png)

   这使您能够检索您在区段代码中指定的数字。

   您应该得到以下公式：

   ```
   AddHours([currentDelivery/scheduling/@contactDate], ToInteger([targetData/@segmentCode]))
   ```

1. 确认保存表达式。 确认计划、保存交付并执行工作流。

* 第一部分将在联系日期（5月25日上午8点）收到邮件。
* 第二段将在两小时后（5月25日上午10:00）收到消息。
* 第三部分将在六小时后（5月25日下午2点）收到消息。
* 第四节将在八小时后（5月25日下午4点）收到消息。

